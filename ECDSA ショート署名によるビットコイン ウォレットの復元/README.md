# ECDSA ショート署名によるビットコイン ウォレットの復元

<!-- wp:embed {"url":"https://www.youtube.com/embed/xBgjWE5tA7Y","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/xBgjWE5tA7Y
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>ECDSA 署名の秘密鍵を公開すると、ビットコイン ウォレットが完全に復元される可能性があることは、誰もが知っています。<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener">以前の記事では、ブロックチェーン トランザクションの弱点と脆弱性</a>について説明しましたが、ビットコイン ウォレットの完全な回復につながる ECDSA の短い署名もあります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>これらの ECDSA 署名が短いと呼ばれるのはなぜですか?</h3>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>この質問に対する答えは、議論中のトピックから得ることができます:&nbsp;<a href="https://bitcoin.stackexchange.com/questions/38513/the-shortest-ecdsa-signature" target="_blank" rel="noreferrer noopener"><strong>「最短の ECDSA 署名」 [最短の ECDSA 署名]</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>前回の記事<a href="https://cryptodeep.ru/reduce-private-key/" target="_blank" rel="noreferrer noopener"><em>「ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減」</em></a>では、興味深い公開鍵を生成する<em>Python</em>スクリプト<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener">maxwell.py</a>を作成しました。</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/69a/7a0/b32/69a7a0b324ac3b1f3e0dc27f0f4130bf.png" alt="ECDSA ショート署名によるビットコイン ウォレットの復元"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>(0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63 , 0xc0c686408d517dfd67c2367651380d00d126e4229631fd03f8ff35eef1a61e3c)</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>署名の値がわかっているので、<code>"R"</code>これは秘密鍵からの公開鍵です<code>(Nonce)</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>ブロックチェーン トランザクションを見てみましょう:&nbsp;<a href="https://btc.exan.tech/tx/11e6b169701a9047f3ddbb9bc4d4ab1a148c430ba4a5929764e97e76031f4ee3" target="_blank" rel="noreferrer noopener"><strong>11e6b169701a9047f3ddbb9bc4d4ab1a148c430ba4a5929764e97e76031f4ee3</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>RawTX:</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001afddd5c9f05bd937b24a761606581c0cddd6696e05a25871279f75b7f6cf891f250000005f3c303902153b78ce563f89a0ed9414f5aa28ad0d96d6795f9c6302200a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8012103151033d660dc0ef657f379065cab49932ce4fb626d92e50d4194e026328af853ffffffff010000000000000000016a00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>このトランザクションのサイズは次のとおりです。<code>156 байт</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3>ECDSA ショート署名を使用してビットコイン ウォレットを復元するにはどうすればよいですか?</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>ビットコイン ブロックチェーンの暗号解読では、独自のBas</em>&nbsp;h スクリプトを使用します。<code>btcrecover.sh</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/299/fa2/616/299fa2616cbdb8e6df9304862f441ba2.gif" alt="ビットコインウォレットの回復プロセス" title="ビットコインウォレットの回復プロセス"/><figcaption class="wp-element-caption">ビットコインウォレットの回復プロセス</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>Bash スクリプト: btcrecover.sh</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt

chmod +x btcrecover.sh


 ./btcrecover.sh 12yysAMhagEm67QCX85p3WQnTUrqcvYVuk


 ./btcrecover.sh 15HvLBX9auG2bJdLCTxSvjvWvdgsW7BvAT
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>結果：</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>| privkey : addr |</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a>を開いて確認しましょう&nbsp;&nbsp;：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ac8d0abda1d32aaabff56cb72bc39a998a98779632d7fee83ff452a86a849bc1:12yysAMhagEm67QCX85p3WQnTUrqcvYVuk
b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f:15HvLBX9auG2bJdLCTxSvjvWvdgsW7BvAT</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>実験的な部分に移り、ビットコインウォレットを復元するためのすべてのスクリプトをより詳細に分析しましょう</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]</strong></a>を開きます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/09BitcoinWalletRecovery" target="_blank" rel="noreferrer noopener"><strong>「09BitcoinWalletRecovery」</strong></a>リポジトリを利用しましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/09BitcoinWalletRecovery/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/4e3/7b8/f6c/4e37b8f6cefc8f8d0553f541a5eb8b98.png" alt="ECDSA ショート署名によるビットコイン ウォレットの復元"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>必要なモジュールをすべてインストールします。</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>bitcoin
ecdsa
utils
base58</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip2 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/d5f/25e/5b1/d5f25e5b1b966ff43a48aaf0955ecfcd.png" alt="ECDSA ショート署名によるビットコイン ウォレットの復元"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/09BitcoinWalletRecovery/breakECDSA.py" target="_blank" rel="noreferrer noopener">breakECDSA.py</a>スクリプトを使用して、<code>RawTX</code>署名 [R, S, Z]から取得します。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001afddd5c9f05bd937b24a761606581c0cddd6696e05a25871279f75b7f6cf891f250000005f3c303902153b78ce563f89a0ed9414f5aa28ad0d96d6795f9c6302200a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8012103151033d660dc0ef657f379065cab49932ce4fb626d92e50d4194e026328af853ffffffff010000000000000000016a00000000 &gt; signatures.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>結果はファイルに保存されます: signatures.txt</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ファイルを開きましょう:<code>PublicKeys.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat signatures.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/cd3/2b9/9e3/cd32b99e37cc600ddd3c35965e2a0288.png" alt="ECDSA ショート署名によるビットコイン ウォレットの復元"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x00000000000000000000003b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63
S = 0x0a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8
Z = 0x521a65420faa5386d91b8afcfab68defa02283240b25aeee958b20b36ddcb6de</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://habr.com/ru/post/682220/">前回の記事</a>でわかるように、<em>署名</em>を生成するための<em><u>秘密鍵</u></em>を知っています。<em></em>&nbsp;<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/9df/b17/63d/9dfb1763d978473245abb6cab03e0e48.png" alt="ECDSA ショート署名によるビットコイン ウォレットの復元"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>この場合、<em><u>秘密鍵は次のとおりです</u></em>&nbsp;<code>(Nonce)</code>。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0 --&gt; 0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63, 0x3f3979bf72ae8202983dc989aec7f2ff2ed91bdd69ce02fc0700ca100e59ddf3
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>署名:</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K = 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0
R = 0x00000000000000000000003b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63
S = 0x0a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8
Z = 0x521a65420faa5386d91b8afcfab68defa02283240b25aeee958b20b36ddcb6de</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>]の値がわかったので、<code>[K, R, S, Z</code>式を使用して秘密鍵を取得し、Bitcoin ウォレットを復元できます。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/2db/a14/ab5/2dba14ab5cb76228181c68a9403038a7.svg" alt="Privkey = ((((S * K) - Z) *​​ modinv(R,N)) % N)"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>秘密鍵を取得するには、<em>Python</em>スクリプトを使用します:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/09BitcoinWalletRecovery/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0
R = 0x00000000000000000000003b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63
S = 0x0a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8
Z = 0x521a65420faa5386d91b8afcfab68defa02283240b25aeee958b20b36ddcb6de


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>Python スクリプトを実行しましょう: calculate.py</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/502/645/324/502645324ec5666803f791ea3cc3a109.png" alt="PrivKey = b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f" title="PrivKey = b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f"/><figcaption class="wp-element-caption">PrivKey = b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a>を開いて確認しましょう&nbsp;&nbsp;：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 15HvLBX9auG2bJdLCTxSvjvWvdgsW7BvAT
WIF:  L3LxjEnwKQMFYNYmCGzM1TqnwxRDi8UyRzQpVfmDvk96fYN44oFG
HEX:  b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/82b/5e1/157/82b5e115789ac3949bbe28bb975a2826.png" alt="ECDSA ショート署名によるビットコイン ウォレットの復元"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>秘密鍵が見つかりました！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>ビットコインウォレット復活！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/50f/e20/dbc/50fe20dbc6d9d6f4a4dbf43c6eaba268.png" alt="ECDSA ショート署名によるビットコイン ウォレットの復元"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>Короткие подписи ECDSA</code><em>コインを失う潜在的な脅威</em>&nbsp;であるため<code>BTC</code>、<em>常にソフトウェアを更新し、検証済みのデバイスのみを使用することを強くお勧めします。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>このビデオは、 CRYPTO DEEP TECH</strong></a>ポータル向けに作成されたもので、&nbsp;&nbsp;暗号通貨&nbsp;<code>secp256k1</code>&nbsp;の弱い署名に対して&nbsp;&nbsp;楕円曲線上でデータと暗号の財務的セキュリティを確保します。&nbsp;<code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/09BitcoinWalletRecovery" target="_blank" rel="noreferrer noopener"><strong>ソース</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech"><strong>電報</strong></a><strong>:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong><u>https://t.me/cryptodeeeptech</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/xBgjWE5tA7Y" target="_blank" rel="noreferrer noopener">動画素材：https://youtu.be/xBgjWE5tA7Y</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/shortest-ecdsa-signature" target="_blank" rel="noreferrer noopener"><strong>ソース: https://cryptodeeep.ru/shortest-ecdsa-signature</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2408} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/013-1024x576.png" alt="Восстановление Биткоин Кошелька через короткие подписи ECDSA" class="wp-image-2408"/></figure>
<!-- /wp:image -->
