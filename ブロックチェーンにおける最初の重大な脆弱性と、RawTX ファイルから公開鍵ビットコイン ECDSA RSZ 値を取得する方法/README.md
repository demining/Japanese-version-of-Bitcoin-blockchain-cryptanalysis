# ブロックチェーンにおける最初の重大な脆弱性と、RawTX ファイルから公開鍵ビットコイン ECDSA RSZ 値を取得する方法

<!-- wp:embed {"url":"https://www.youtube.com/embed/BYd-cuFRZmM","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/BYd-cuFRZmM
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener"><strong>この記事では</strong></a>、ビットコインのブロックチェーンから署名値を抽出する方法について説明します&nbsp;<code>ECDSA R, S, Z</code>&nbsp;が、まず最初に、&nbsp;<a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener">ニールス シュナイダー</a>&nbsp;(<code>Nils Schneider</code>&nbsp;<em>別名</em>&nbsp;tcatm&nbsp;&nbsp;)によって発見されたブロックチェーン トランザクションの最初の重大な脆弱性を思い出してください。<a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>ビットコインの開発者であり、 「BitcoinWatch」</em>&nbsp;と&nbsp;「BitcoinCharts」の所有者&nbsp;<em>。</em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/20d/674/8c4/20d6748c4bdd5e28ada4e9d06b9e8d35.png" alt="4.1 ビットコインに対する危険なランダム攻撃の歴史" title="4.1 ビットコインに対する危険なランダム攻撃の歴史"/><figcaption class="wp-element-caption">4.1 ビットコインに対する危険なランダム攻撃の歴史</figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ドキュメント&nbsp;<code>[PDF]</code>:<a href="https://eprint.iacr.org/2014/848.pdf" target="_blank" rel="noreferrer noopener"><em>秘密鍵回復の組み合わせ攻撃: 貧弱な RNG イベントの存在下での一般的なビットコイン鍵管理、ウォレット、およびコールド ストレージ ソリューションの極端な脆弱性について</em></a><a href="https://eprint.iacr.org/2014/848.pdf" target="_blank" rel="noreferrer noopener">&nbsp;<em></em></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>2012 年 12 月 25 日、</em>&nbsp;&nbsp;Nils は一部のビットコイン ブロックチェーン トランザクションに潜在的な弱点があることを発見しました。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>このトランザクションを見てください:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>transaction:</code>&nbsp;<a href="https://www.blockchain.com/btc/tx/9ec4bc49e828d924af1d1029cacf709431abbde46d59554b62bc270e3b29c4b1" target="_blank" rel="noreferrer noopener">9ec4bc49e828d924af1d1029cacf709431abbde46d59554b62bc270e3b29c4b1</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/cc3/2e2/94a/cc32e294aa0e77019d1581ce61893349.png" alt="ブロックチェーンにおける最初の重大な脆弱性と、RawTX ファイルから公開鍵ビットコイン ECDSA RSZ 値を取得する方法"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>input script 1:
30440220d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1022044e1ff2dfd8102cf7a47c21d5c9fd5701610d04953c6836596b4fe9dd2f53e3e0104dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff

input script 2:
30440220d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad102209a5f1c75e461d7ceb1cf3cab9013eb2dc85b6d0da8c3c6e27e3a5a5b3faa5bab0104dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>このトランザクションには、2 つの入力と 1 つの出力があります。<br>2 つの入力スクリプトをよく見ると、最初と最後にかなりの数の同じバイトがあることがわかります。<br>末尾のこれらのバイトは、コインが費やされているアドレスの 16 進数でエンコードされた公開鍵であるため、何も問題はありません。<br>ただし、スクリプトの前半は実際の署名です&nbsp;<code>(r, s)</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>r1: d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1
r2: d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1

s1: 44e1ff2dfd8102cf7a47c21d5c9fd5701610d04953c6836596b4fe9dd2f53e3e
s2: 9a5f1c75e461d7ceb1cf3cab9013eb2dc85b6d0da8c3c6e27e3a5a5b3faa5bab</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ご覧のとおり、&nbsp;<code>r1</code>&nbsp;同じです&nbsp;<code>r2</code>。&nbsp;<em>これは&nbsp;</em><strong><em><u>大きな問題</u></em></strong><em>です。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><u>秘密鍵を</u></strong>&nbsp;この公開鍵に復元できます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>04dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>これを行うには、学校代数の簡単な公式を使用できます 😉</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>private key = (<strong>z1*s2</strong> - z2*s1)/(<strong>r*</strong>(<strong>s1-s2</strong>))</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>見つけて&nbsp;<code>z1</code>&nbsp;、&nbsp;<code>z2</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これらは&nbsp;<code>хэши</code>&nbsp;署名が必要な出力です。出力トランザクションを取得してカウントしましょう ( で計算&nbsp;<code>OP_CHECKSIG</code>):</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>z1: c0e2d0a89a348de88fda08211c70d1d7e52ccef2eb9459911bf977d587784c6e
z2: 17b0f41c8c337ac1e18c98759e83a8cccbc368dd9d89e5f03cb633c265fd0ddc</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>次に、これらすべての値を 1 つのPython</em>スクリプトにまとめてみましょう&nbsp;<em>:</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener">脆弱性R.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/c5f/301/358/c5f301358b79c833d7701b7c883235a7.png" alt="Python スクリプト: 脆弱性R.py" title="Python スクリプト: 脆弱性R.py"/><figcaption class="wp-element-caption">Python スクリプト: 脆弱性R.py</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>p</code><code>G</code>ビットコインで使用される曲線のパラメーター&nbsp;&nbsp;である、大きさのオーダーです&nbsp;<code>secp256k1</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>計算用のフィールドを作成しましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K = GF(<strong>p</strong>)</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K((<strong>z1*s2</strong> - z2*s1)/(<strong>r*</strong>(<strong>s1-s2</strong>)))</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>スクリプトを実行しましょう:&nbsp;<code>python3 vulnerabilityR.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次に、スクリプトの&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener">脆弱性 R.py は</a>&nbsp;、このフィールドで<strong><u>秘密鍵</u></strong>&nbsp;を計算します&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm
WIF:  5KJp7KEffR7HHFWSFYjiCUAntRSTY69LAQEX1AUzaSBHHFdKEpQ
hex:  c477f9f65c22cce20657faa5b2d1d8122336f851a508a1ed04e479c34985bf96</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/a69/992/dcf/a69992dcf93bacd0324c9a06722be9b5.png" alt="bitaddress の Web サイトで秘密鍵を確認する" title="bitaddress の Web サイトで秘密鍵を確認する"/><figcaption class="wp-element-caption">bitaddress の Web サイトで秘密鍵を確認する</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em><u>秘密鍵が見つかりました！</u></em></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm
</div></figure>
<!-- /wp:embed -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/049/126/899/049126899d0dc2b84a30b18fc496c258.png" alt="
0.1638109 BTC" title="
0.1638109 BTC"/><figcaption class="wp-element-caption">0.1638109 BTC</figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>もちろん、Bitcoin の開発者は決定論的関数を導入することでこの脆弱性を修正しました。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この機能により、&nbsp;<code>RFC 6979</code>&nbsp;ビットコイン署名にランダム性の要素が導入され、トランザクションの暗号強度が向上します。&nbsp;<code>ECDSA</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>ドキュメント&nbsp;<code>[PDF]</code>:&nbsp;<a href="https://datatracker.ietf.org/doc/html/rfc6979" target="_blank" rel="noreferrer noopener"><em>RFC 6979: デジタル署名アルゴリズム (DSA) および楕円曲線デジタル署名アルゴリズム (ECDSA) の決定論的使用法</em></a><a href="https://eprint.iacr.org/2014/848.pdf">&nbsp;</a><a href="https://datatracker.ietf.org/doc/html/rfc6979" target="_blank" rel="noreferrer noopener"><em></em></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>私たちが実際に知っているように、Bitcoin ブロックチェーンにはまったく異なる脆弱なトランザクションがあります。</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>статью</code>「&nbsp;<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><em>ビットコイン ブロックチェーン上の ECDSA での 1 つの脆弱なトランザクションと、ラティス アタックの助けを借りて、BTC コインの秘密鍵を受け取りました</em></a>」&nbsp;<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><em></em></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/6b8/723/07d/6b872307d4a4dc3a74386c2b83d133a2.png" alt="https://habr.com/ru/post/671932/" title="https://habr.com/ru/post/671932/"/></a></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/RawTX.json" target="_blank" rel="noreferrer noopener">次に、 「RawTX.json」ファイル (&nbsp;</a><a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"><strong>01BlockchainGoogleDrive</strong></a>&nbsp;で取得&nbsp;&nbsp;)から&nbsp;公開鍵&nbsp;<code>Bitcoin</code>&nbsp;<code>ECDSA</code>&nbsp;と値を&nbsp;取得しましょう。<code>R, S, Z</code><a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/RawTX.json" target="_blank" rel="noreferrer noopener"></a><a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>これを行うには、Google Colab のターミナル&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[&nbsp;<strong>TerminalGoogleColab]を使用します。</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>以前にビデオを録画しました:&nbsp;&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener"><strong>「Google Colab の TERMINAL は、GITHUB で作業するためのすべての便利さを作成します」</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography" target="_blank" rel="noreferrer noopener"><strong>詳細な暗号解析のために「CryptoDeepTools」</strong></a>リポジトリを調べて&nbsp;、&nbsp;<em>Bash スクリプトが</em>&nbsp;どのように機能するかを詳しく見てみましょう&nbsp;:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>チーム:</strong></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/02BreakECDSAcryptography/

sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt

chmod +x getsign.sh

./getsign.sh</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/9bf/c35/0c7/9bfc350c715272db79f6bd5c6039e924.png" alt="ファイル" title="ファイル"/><figcaption class="wp-element-caption">ファイル</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/5f0/cf5/6f0/5f0cf56f00c897f69fab24e8a3073588.png" alt="Bash スクリプト コード: getsign.sh" title="Bash スクリプト コード: getsign.sh"/><figcaption class="wp-element-caption">Bash スクリプト コード: getsign.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>それでは、&nbsp;&nbsp;<em>Bash スクリプト</em>の全体的な作業を詳細に見てみましょう:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat RawTX.json &gt; index.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ファイルのコピーを&nbsp;<code>RawTX.json</code>&nbsp;新しいファイルに&nbsp;作成する<code>index.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>for</strong> run <strong>in</strong> {1..4}; <strong>do</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>ファイルで4行を</em>&nbsp;取得する&nbsp;<code>ЦИКЛ</code>&nbsp;ため、&nbsp;それを開きます&nbsp;<code>index.json</code>&nbsp;<em></em><code>{1..4}</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>export LINE=1 ; sed -n "${LINE}p" index.json &gt; index2.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ユーティリティは&nbsp;<em>行 #1</em><code>export</code>&nbsp;を取得し&nbsp;&nbsp;、それを新しいファイルに保存します&nbsp;<em></em><code>index2.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sed -i '1d' index.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ユーティリティは、&nbsp;ファイルから&nbsp;<em>行 #1&nbsp;</em><code>sed</code>&nbsp;を削除します&nbsp;<em></em><code>index.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/972/d1b/555/972d1b5554e84191da57b16415061198.png" alt="echo ユーティリティは、私たちのために Python スクリプトを作成します fileopen.py" title="echo ユーティリティは、私たちのために Python スクリプトを作成します fileopen.py"/><figcaption class="wp-element-caption">echo ユーティリティは、私たちのために Python スクリプトを作成します fileopen.py</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 fileopen.py</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>Python スクリプト</em>&nbsp;を実行する&nbsp;<code>fileopen.py</code>&nbsp;と、新しい&nbsp;<em>Bash スクリプトが</em>正常に作成されます。&nbsp;<code>signscript.sh</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x signscript.sh
./signscript.sh</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>Bash スクリプト</em>への権利を取得します&nbsp;: signscript.sh</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>その結果、&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/breakECDSA.py" target="_blank" rel="noreferrer noopener">breakECDSA.py&nbsp;</a><em>Python スクリプト</em>&nbsp;が起動され&nbsp;、最終的に&nbsp;ビットコインの値&nbsp;&nbsp;と公開鍵が<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/breakECDSA.py" target="_blank" rel="noreferrer noopener"></a><code>RawTX</code><code>R, S, Z</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これはすべてファイルに保存されます。&nbsp;<code>"signatures.json"</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2e1/9df/c27/2e19dfc270a6f0bc6bd2ea9123215442.png" alt="ファイル: &quot;signatures.json&quot; ビットコインの公開鍵と R、S、Z 値" title="ファイル: &quot;signatures.json&quot; ビットコインの公開鍵と R、S、Z 値"/><figcaption class="wp-element-caption">ファイル: 「signatures.json」 ビットコインの公開鍵と R、S、Z の値</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>rm</strong> <strong>signscript</strong>.sh
<strong>rm</strong> <strong>fileopen</strong>.py</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ユーティリティは&nbsp;<em>Python スクリプト</em><code>rm</code>&nbsp;を削除し&nbsp;&nbsp;、新しい&nbsp;<em>Bash スクリプト</em>を正常に作成します。&nbsp;<em></em>&nbsp;<code>fileopen.py</code><em></em><code>signscript.sh</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>done</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>その結果、<em>&nbsp;4サイクル後にすべてが終了します</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>rm <strong>index</strong>.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>サイクルが終了し、ユーティリティが&nbsp;<code>rm</code>&nbsp;削除します&nbsp;<code>index.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>Bash スクリプト</em>:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a>&nbsp;<code>Завершает работу!</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>これで、次のことがわかりました。</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Bitcoin&nbsp;</code>から公開鍵を取得する&nbsp;<code>&nbsp;ECDSA</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>価値&nbsp;<code>R, S, Z</code>&nbsp;を得る<code>&nbsp;ECDSA</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>に適用します&nbsp;<code>криптоанализа</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>ソースコード:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>テレグラム:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>動画素材：&nbsp; https:&nbsp;<a href="https://youtu.be/BYd-cuFRZmM" target="_blank" rel="noreferrer noopener">//youtu.be/BYd-cuFRZmM</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/BYd-cuFRZmM","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/BYd-cuFRZmM
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
