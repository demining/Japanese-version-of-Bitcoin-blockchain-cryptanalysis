# 準同型でsecp256k1を高速化

<!-- wp:embed {"url":"https://www.youtube.com/embed/DH6FyNY-Gh0","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/DH6FyNY-Gh0
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;この記事では、 Bitcoin 暗号通貨の検証を最適化するのに役立つ<code>secp256k1</code>&nbsp;自己同形&nbsp;加速関数&nbsp;を見ていきますが、最初に少し歴史を紹介します。<code>ECDSA</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>12 января 2009 года</code>&nbsp;<a href="https://ru.wikipedia.org/wiki/%D0%A1%D0%B0%D1%82%D0%BE%D1%81%D0%B8_%D0%9D%D0%B0%D0%BA%D0%B0%D0%BC%D0%BE%D1%82%D0%BE" target="_blank" rel="noreferrer noopener">サトシ・ナカモトは、</a>&nbsp;初期のビットコイン取引で&nbsp;<a href="https://ru.wikipedia.org/wiki/%D0%93%D0%B0%D1%80%D0%BE%D0%BB%D1%8C%D0%B4_%D0%A2%D0%BE%D0%BC%D0%B0%D1%81_%D0%A4%D0%B8%D0%BD%D0%BD%D0%B8_II" target="_blank" rel="noreferrer noopener">ハル・フィニー</a>&nbsp;<code>10 BTC</code>を送りました。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>サトシ・ナカモトがビットコインの最初の受取人としてハルを選んだという事実は驚くべきことではありません。<a href="https://ru.wikipedia.org/wiki/PGP" target="_blank" rel="noreferrer noopener">サトシは、 PGP</a>暗号化システムを開発することにより、世界で最も優秀なプログラマーおよび暗号学者の 1 人としての地位を確立したハルに大きな敬意を払っていました&nbsp;。Hal はまた、Satoshi が Bitcoin の開発に使用する再利用可能なプルーフ オブ ワークの重要な基盤を築きました。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>世界最高の暗号学者の 1 人である Hal は、Bitcoin に出くわした直後に、Bitcoin が大きなブレークスルーであることに気付きました。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>彼はまた&nbsp;<code>2008 году</code>&nbsp;、ビットコインを&nbsp;<strong><em>「非常に有望なアイデア」</em></strong>と呼びました。</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w780/getpro/habr/upload_files/e90/c19/48e/e90c1948ecdd67427ca6fd6eb0fe7b24.jpg" alt="準同型でsecp256k1を高速化"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>によって公開された&nbsp;この&nbsp;<em>ツイートは</em><code>11 января 2009 года</code>、Hal が&nbsp;ビットコインが&nbsp;何であるかを知る前から、<em><u>ビットコインの成功を予測していたことを十分に証明しています。</u></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>2 年が経過し、&nbsp;<code>2011 году</code>&nbsp;開発者でありビットコイン愛好家である Hal Finney は、&nbsp;&nbsp;<em><u>secp256k1 準同形関数を使用して ECDSA 署名検証を高速化できると</u></em>Bitcointalk&nbsp;<a href="https://bitcointalk.org/index.php?topic=3238.msg45565#msg45565" target="_blank" rel="noreferrer noopener"><strong>フォーラムに書いています。</strong></a><em><u></u></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>LAMBDA と BETA は、secp256k1 曲線上の値です。</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/9a4/ce6/3af/9a4ce63afa2c39ded280bea637d2ba70.svg" alt="λ^3 (mod n) = 1  "/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/df4/4d7/5ce/df44d75ceb126764e40606ad336f26e3.svg" alt="b ^ 3 (mod p) = 1"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>secp256k1 は、x 座標と y 座標に次の素数を使用します。</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>p = 0xffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffc2f</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>および曲線の順序:</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>n = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>LAMBDA</code>&nbsp;最初のステップは、と の&nbsp;値を計算することです&nbsp;<code>BETA</code>。これにより、曲線上の任意の点について&nbsp;<code>Q = (x, y)</code>:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>LAMBDA * Q = (BETA*х mod р, у)</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>これは、いわゆる効果的に計算可能な&nbsp;<em><u>自己</u></em>同相であり、単一の乗算を実行することで&nbsp;、曲線上の任意の点<code>secp256k1</code>&nbsp;にこの特別な値を&nbsp;非常に迅速に乗算できることを意味します&nbsp;。<code>LAMBDA</code><code>mod p</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>Hal Finney によって発見され、公開された意味:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>LAMBDA = 0x5363ad4cc05c30e0a5261c028812645a122e22ea20816678df02967c1b23bd72

BETA = 0x7ae96a2b657c07106e64479eac3434e99cf0497512f58995c1396c28719501ee</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>すばやく乗算できることを考えると、&nbsp;<code>LAMBDA,</code>&nbsp;秘訣は を計算することです&nbsp;<code>kQ</code><em>。&nbsp;</em>まずは計算してみましょう。次に、&nbsp;&nbsp;と の&nbsp;&nbsp;2 つの部分に分割する必要があります&nbsp;。それぞれが の約半分の幅になる&nbsp;ため、次のようになります。<em>&nbsp;</em><code>Q' = lambdaQ</code><code>k</code><code>k1</code><code>k2</code><code>n</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>k = k1 + k2*LAMBDA  mod  n</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>それから</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>k*Q = (k1 + k2*LAMBDA)*Q = k1*Q + k2*LAMBDA*Q = k1*Q + k2*Q'</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>この最後の式は、二重乗算アルゴリズムを使用して効率的に計算できます。 と は長さが半分であるため&nbsp;<code>k1</code>&nbsp;、&nbsp;<code>k2</code>&nbsp;高速化されます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>欠けている部分&nbsp;&nbsp;は と&nbsp;<code>k</code>&nbsp;に&nbsp;分かれています。これには、&nbsp;次の<em><u>4 つの値</u></em>が使用されます。<code>k1</code><code>k2</code><em><u></u></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>а1 = 0x3086d221a7d46bcde86c90e49284eb15
b1 = -0xe4437ed6010e88286f547fa90abfe4c3
а2 = 0x114ca50f7a8e2f3f657c1108d9d44cfd8
b2 = 0x3086d221a7d46bcde86c90e49284eb15</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>(a1=b2でもいいです)</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>これらを次のように使用して k を分割します。</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>c1 = RoundToNearestInteger(b2*k/n)
c2 = RoundToNearestInteger(-b1*k/n)

k1 = k - c1*a1 - c2*a2
k2 = -c1*b1 - c2*b2</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>20%-е</code>&nbsp;2 倍の回数が半分になるため、おおよその速度向上が得られます&nbsp;。これにより、複数のポイントでグループ化できる多くのアルゴリズムに、2 倍の数の公開鍵を使用した場合のパフォーマンスが得られます。<br><em>同等の最適化レベルでのこの高速化により、&nbsp;</em><code>secp256k1</code><em>&nbsp;一般的に使用されるすべての曲線の中で最も速くテストできます。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3>開発者であり研究者でもある Jean Luc Pons 氏によるリポジトリのより詳細な調査で、自己同形の存在について学びました。</h3>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/53a/a41/46a/53aa4146a4d43ac9279e96b8e403216d.png" alt="準同型でsecp256k1を高速化"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>以前に記事を公開しました:&nbsp;&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"><strong><em>「ポラードのカンガルーは、secp256k1 PRIVATE KEY + NONCES の離散対数の解を既知の範囲で見つけます」</em></strong></a><strong><em>&nbsp;では、&nbsp;</em></strong><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">ジャン リュック ポンズ</a>&nbsp;による&nbsp;ソース コードを使用して&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">カンガルー</a>を構築しました。<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>ジャン・リュック・ポンスが指摘した加速メカニズムに基づくバニティサーチ</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L255" target="_blank" rel="noreferrer noopener"><strong>main.cpp</strong></a>を開く&nbsp;<a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L255" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/605/fca/301/605fca301a5eef1f215250562ff4e039.png" alt="main.cpp" title="main.cpp"/><figcaption class="wp-element-caption">main.cpp</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L255" target="_blank" rel="noreferrer noopener">255 行</a>目&nbsp;と&nbsp;<a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L256" target="_blank" rel="noreferrer noopener">256 行目</a>で、&nbsp;&nbsp;&nbsp;Jean Luc Pons が&nbsp;<em><u>endomorphism</u></em><code>secp256k1</code>&nbsp;を使用して&nbsp;楕円曲線の加速関数を適用したことがわかります。<em><u></u></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>  lambda.SetBase16("5363ad4cc05c30e0a5261c028812645a122e22ea20816678df02967c1b23bd72");
  lambda2.SetBase16("ac9c52b33fa3cf1f5ad9e3fd77ed9ba4a880b9fc8ec739c2e0cfc810b51283ce");</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>実験的な部分に移りましょう:</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/7df/255/c08/7df255c08ea1fb0e498b76bf4a431873.png" alt="準同型でsecp256k1を高速化"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">記事</a>から覚えているように&nbsp;、<a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong>ビットコイン リッチ リストのビットコイン アドレス</strong></a><a href="https://www.blockchain.com/ru/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong>14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</strong></a>の&nbsp;&nbsp;合計&nbsp;<a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong>1,000 万米ドル</strong></a>以上&nbsp;のトランザクションを分析しました&nbsp;。このビットコイン アドレスを例として取り上げます。<a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong></strong></a><a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>ターミナルでGoogle Colab&nbsp;&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]</strong></a>を開き&nbsp;、リポジトリ&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/07EndomorphismSecp256k1" target="_blank" rel="noreferrer noopener">「07EndomorphismSecp256k1」を使用します。</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/07EndomorphismSecp256k1/

pip3 install base58</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/928/66f/34b/92866f34b1dcfbce80b23fd56a913744.png" alt="準同型でsecp256k1を高速化"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/9dfd594126117e07fc51a77a7c613180eb662f18/07EndomorphismSecp256k1/endomorphism.py#L145" target="_blank" rel="noreferrer noopener">145</a><em>行</em>&nbsp;目&nbsp;<em>の</em>コード&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/9dfd594126117e07fc51a77a7c613180eb662f18/07EndomorphismSecp256k1/endomorphism.py#L145" target="_blank" rel="noreferrer noopener">endomorphism.py</a>&nbsp;&nbsp;を&nbsp;開く<em></em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/9dfd594126117e07fc51a77a7c613180eb662f18/07EndomorphismSecp256k1/endomorphism.py#L145" target="_blank" rel="noreferrer noopener"></a><code>secp256k1</code><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>def</strong> <strong>split_scalar_endo</strong>(k):
    n = N
    a1 = 0x3086d221a7d46bcde86c90e49284eb15
    b1 = -0xe4437ed6010e88286f547fa90abfe4c3
    a2 = 0x114ca50f7a8e2f3f657c1108d9d44cfd8
    b2 = a1
    c1 = div_nearest(b2 * k, n)
    c2 = div_nearest(-b1 * k, n)
    k1 = mod(k - c1 * a1 - c2 * a2, n)
    k2 = mod(-c1 * b1 - c2 * b2, n)
    k1neg = k1 &gt; POW_2_128
    k2neg = k2 &gt; POW_2_128
    <strong>if</strong> k1neg:
        k1 = n - k1
    <strong>if</strong> k2neg:
        k2 = n - k2
    <strong>return</strong> (k1neg, k1, k2neg, k2)</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">記事</a><code>HEX</code>で公開した形式の&nbsp;秘密鍵をコピーします&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>HEX:  23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":4} -->
<h4>秘密鍵を指定して Python スクリプト endomorphism.py を実行してみましょう。</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 endomorphism.py 23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b &gt; pubkey.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/3c5/6f1/3d7/3c56f13d77ef80024a8cfb16f80943fc.png" alt="準同型でsecp256k1を高速化"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>公開鍵の結果は次のファイルに保存されます: pubkey.txt</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Откроем файл: pubkey.txt и проверим:

cat pubkey.txt

04ca5606a1e820e7a2f6bb3ab090e8ade7b04a7e0b5909a68dda2744ae3b8ecbfa280a47639c811134d648e8ee8096c33b41611be509ebca837fbda10baaa1eb15
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/448/529/511/4485295113ba74f334a01f4ed2b54bd4.png" alt="準同型でsecp256k1を高速化"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>次に、Python スクリプト pubtoaddr.py を実行してビットコイン アドレスを取得します。</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 pubtoaddr.py

Откроем файл: BitcoinAddress.txt и проверим:

cat BitcoinAddress.txt

14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/1a4/805/542/1a480554216e020e1c53a9370661274a.png" alt="準同型でsecp256k1を高速化"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE
WIF:  5J64pq77XjeacCezwmAr2V1s7snvvJkuAz8sENxw7xCkikceV6e
HEX:  23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d8c/78d/8eb/d8c78d8eb14e5246b495e09f59631e44.png" alt="bitaddress の Web サイトで秘密鍵を確認する" title="bitaddress の Web サイトで秘密鍵を確認する"/><figcaption class="wp-element-caption">bitaddress の Web サイトで秘密鍵を確認する</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>ブロックチェーン:</h3>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ed9/7da/c1d/ed97dac1dc07e2bce09fe0951d9f64de.png" alt="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" title="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE"/><figcaption class="wp-element-caption">www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>このトピックについては、文献を読むことができます。</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>Gallant、Robert P.、Robert J. Lambert、および Scott A. Wanston。&nbsp;</em><strong><em>「効果的な内部同相を持つ楕円曲線での点乗算の高速化」</em></strong><em>&nbsp;.&nbsp;年次国際暗号会議、pp. 190–200。スプリンガー、ベルリン、ハイデルベルク、(2001)</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>Hankerson、Darrell、Alfred J. Menezes、および Scott Wanston。&nbsp;</em><strong><em>「楕円曲線暗号のガイド」</em></strong><em>&nbsp;.&nbsp;コンピューター レビュー 46、いいえ。1 (2005)</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>ハル・フィニー。bitcointalk -&nbsp;&nbsp;</em><strong><em>「署名検証の高速化」</em></strong><em>&nbsp;.&nbsp;(2011)&nbsp;</em>&nbsp;<a href="https://bitcointalk.org/index.php?topic=3238.0" target="_blank" rel="noreferrer noopener">https://bitcointalk.org/index.php?topic=3238.0</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>Blahut、Richard E.&nbsp;&nbsp;</em><strong><em>「暗号化と安全な通信」</em></strong><em>。ケンブリッジ大学出版局、(2014)</em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>このビデオは、 CRYPTO DEEP TECH</strong></a>ポータル向けに作成されたもので、&nbsp;&nbsp;暗号通貨&nbsp;<code>secp256k1</code>&nbsp;の弱い署名に対して&nbsp;&nbsp;楕円曲線上でデータと暗号の財務的セキュリティを確保します。&nbsp;<code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/07EndomorphismSecp256k1" target="_blank" rel="noreferrer noopener"><strong><u>ソース</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong>電報</strong></a><strong>:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong><u>https://t.me/cryptodeeeptech</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/DH6FyNY-Gh0" target="_blank" rel="noreferrer noopener"><strong>動画素材</strong></a><strong>：&nbsp; https:&nbsp;<u><a href="https://youtu.be/DH6FyNY-Gh0" target="_blank" rel="noreferrer noopener">//youtu.be/DH6FyNY-Gh0</a></u></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/endomorphism"><strong>出典</strong></a><strong>:&nbsp;&nbsp;</strong><a href="https://cryptodeep.ru/endomorphism" target="_blank" rel="noreferrer noopener"><strong>https://cryptdeep.ru/endomorphism</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p> <a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2404} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/011-1024x576.png" alt="Ускорение secp256k1 с помощью эндоморфизма" class="wp-image-2404"/></figure>
<!-- /wp:image -->
