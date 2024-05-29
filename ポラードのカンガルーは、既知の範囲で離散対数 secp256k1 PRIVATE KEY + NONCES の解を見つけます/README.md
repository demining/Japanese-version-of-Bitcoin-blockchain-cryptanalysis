# ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます

<!-- wp:embed {"url":"https://www.youtube.com/embed/UGUJyxOhBBQ","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/UGUJyxOhBBQ
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>この記事では、計算数論の分野から ECDLP の最速のアルゴリズムを見ていきます。ポラードのカンガルーは、ポラードのラムダ アルゴリズムとも呼ばれます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ポラードのカンガルー法は、&nbsp;任意の巡回群で<a href="https://cryptodeep.ru/doc/discretelog.pdf" target="_blank" rel="noreferrer noopener"><strong>離散対数を</strong></a>計算します&nbsp;。離散対数が特定の範囲内にあることがわかっている場合に適用されます&nbsp;<code>[ a , b ]</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>ポラードのカンガルーの利点:</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>メモリをほとんど使用しない</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>直線加速で並列化可能</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>メモリ要件を効果的に追跡できます</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>これらすべてにより、カンガルー法は離散対数問題を解くための最も強力な方法になります。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>ECDSA 署名方式を破る 1 つの方法は、離散対数問題を解くことです。</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>設定では、&nbsp;指数計算法などの準指数時間アルゴリズムは使用されず、&nbsp;ポラード カンガルー法が<code>ECDSA</code>&nbsp;その基礎となる最もよく知られている解法&nbsp;です。<code>DLP</code>さまざまな理論的側面で負担をかけないようにします。実験的な部分に移りましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ビットコインのブロックチェーンで知られているように、BTC コインの送信者は常に自分の&nbsp;<em>公開鍵</em>を明らかにします。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>ポラードカンガルー方式の場合、公開鍵または</em><em>署名</em>&nbsp;&nbsp;値が&nbsp;わかれば十分です&nbsp;（&nbsp;楕円曲線平面上の&nbsp;&nbsp;座標点であるため、&nbsp;&nbsp;値&nbsp;<code>R</code>&nbsp;も&nbsp;<em>公開鍵</em><code>R</code>&nbsp;の一種です&nbsp;）。<em></em><code>Nonces</code><code>x</code><code>secp256k1</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em>&nbsp;<code>PRIVATE KEY</code>&nbsp;<em>範囲または範囲</em>&nbsp;<em>を定義するだけです</em><code>NONCES</code>。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>ビットコインのブロックチェーンで署名を作成する一部のデバイスは、<code>ECDSA</code>値に関する情報のバイトを部分的に開示する可能性があります&nbsp;<code>"K" (NONCES)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これは BTC コインを失う潜在的な脅威であると考えており、常にソフトウェアを更新し、検証済みのデバイスのみを使用することを強くお勧めします。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最近、私たちはビットコインのブロックチェーンで暗号解読を行い、そのような取引をいくつか発見しました。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>501.06516041 BTC の引き出し額があるこのビットコイン アドレスを見てください。</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/3d9/756/d50/3d9756d50d09b0584c5967175184dd42.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong>このビットコイン アドレス14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</strong></a>のトランザクションでは&nbsp;、値に関するバイト情報の部分的な開示がありました。&nbsp;<code>"K" (NONCES)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><strong><u>前回の記事</u></strong></a>でわかるように&nbsp;<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><strong><u></u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2f6/78f/d0f/2f678fd0faefca8c25518666490d795f.png" alt="habr.com/ru/post/671932/" title="habr.com/ru/post/671932/"/><figcaption class="wp-element-caption">habr.com/ru/post/671932/</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>秘密鍵の範囲を見つける</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>このトランザクションを見つけて、ポラードのカンガルー法を使用して&nbsp;<em><u>秘密鍵を回復しましょう</u></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>以前、ビデオの説明</em>を記録しました&nbsp;:&nbsp;&nbsp;<a href="https://cryptodeep.ru/terminal-google-colab/" target="_blank" rel="noreferrer noopener">「Google Colab の TERMINAL は、GITHUB で作業するためのすべての便利さを作成します」</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ターミナルで Google Colab を開く&nbsp;<a href="https://github.com/demining/TerminalGoogleColab"><strong>[TerminalGoogleColab]</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>RawTX を検索するには、リポジトリ&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">「01BlockchainGoogleDrive」を使用します。</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/01BlockchainGoogleDrive/

chmod +x getrawtx.sh

./getrawtx.sh 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/496/30f/b12/49630fb12d6c1cf64f99f24f530add95.png" alt="Bash スクリプトを実行します: getrawtx.sh" title="Bash スクリプトを実行します: getrawtx.sh"/><figcaption class="wp-element-caption">Bash スクリプトを実行します: getrawtx.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>ビットコイン アドレス&nbsp;<a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener">14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</a>トランザクションのすべての内容が&nbsp;ファイルに保存されました。&nbsp;<code>RawTX.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ファイルを開きます:&nbsp;<code>RawTX.json</code>&nbsp;そして、このトランザクションを見つけます&nbsp;<code>[строка №10]</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2c1/dca/207/2c1dca20782c1e09325836c491aeaaf0.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>コマンドを使用して&nbsp;<code>export</code>&nbsp;、この行を&nbsp;個別に&nbsp;<code>№10</code>&nbsp;保存&nbsp;してみましょう<code>RawTX.json</code><code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>export LINE=10 ; sed -n "${LINE}p" RawTX.json &gt; RawTX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b8b/0c2/508/b8b0c25080dfe2ad36c112e2f0015e72.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat RawTX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b1a/a44/976/b1aa44976ad24df74e02246a8747db31.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>調べて&nbsp;<code>TxID</code>&nbsp;、&nbsp;&nbsp;<a href="https://live.blockcypher.com/btc/decodetx/" target="_blank" rel="noreferrer noopener"><strong>Decode Raw Bitcoin Hexadecimal Transaction</strong></a>&nbsp;Web サイトを開き&nbsp;、挿入します&nbsp;<code>RawTX</code>。その結果、TxID を取得します。</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/166/292/2df/1662922df068e4d009f0efcbecc2089d.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>その結果、TxID を取得します。</h4>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/cc2/bf5/146/cc2bf5146ef7a2e6004d79986535255d.png" alt="TxID: b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b" title="TxID: b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b"/><figcaption class="wp-element-caption">TxID: b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>リンク TxID を開きます:<br><a href="https://btc.exan.tech/tx/b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b" target="_blank" rel="noreferrer noopener">https://btc.exan.tech/tx/b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b</a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/c32/5a8/e40/c325a8e40de9ca6f15431dac1dcfe274.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/3b2/8d1/648/3b28d1648bf0cf157833dbc3b0821fd8.png" alt="RawTX の確認" title="RawTX の確認"/><figcaption class="wp-element-caption">RawTX の確認</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>ここで、値に関する情報のバイトの部分的な開示を見つけます&nbsp;<code>"K" (NONCES)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これを行うには、スクリプトを使用します&nbsp;<code>«RangeNonce»</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>«RangeNonce»</code>&nbsp;秘密鍵の範囲を見つけるスクリプトです</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>配布キットのバージョンを選択しましょう&nbsp;<code>GNU/Linux</code>&nbsp;。&nbsp;<code>Google Colab</code>&nbsp;提供します&nbsp;<code>UBUNTU 18.04</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/94d/d82/af4/94dd82af4d7155e548aa7241df9b3206.png" alt="範囲ノンス" title="範囲ノンス"/><figcaption class="wp-element-caption">範囲ノンス</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>すべてのファイルをアップロード&nbsp;<code>Google Colab</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/751/91d/9a2/75191d9a233987a74ed0fa016aa5e2a1.png" alt="RangeNonce + Google Colab" title="RangeNonce + Google Colab"/><figcaption class="wp-element-caption">RangeNonce + Google Colab</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>スクリプトにパーミッションを許可してスクリプトを実行しましょう&nbsp;<code>«RangeNonce»</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>チーム:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x RangeNonce
./RangeNonce
cat Result.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8ff/546/0c3/8ff5460c3570ebbbb3c7fb0f6a394fd9.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>すべてがファイルに保存されます: Result.txt</h4>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2af/471/f7e/2af471f7eb46f84157b402ed67ea9139.png" alt="結果.txt" title="結果.txt"/><figcaption class="wp-element-caption">結果.txt</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>これは、「K」(NONCES) の値のバイト情報の部分的な開示です。</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>したがって、&nbsp;<u>秘密鍵は</u><u>次の範囲</u>&nbsp;にあります&nbsp;。</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K = 070239c013e8f40c8c2a0e608ae15a6b00000000000000000000000000000000
K = 070239c013e8f40c8c2a0e608ae15a6bffffffffffffffffffffffffffffffff</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/204/ef7/984/204ef79845ae3d93a9c93d43f81e484b.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong></strong>&nbsp;形式の&nbsp;最初の&nbsp;<code>32</code>&nbsp;数字と文字&nbsp;に<strong>注意してください。署名の値は</strong><em><u>秘密鍵の範囲、</u></em>&nbsp;つまり値と&nbsp;&nbsp;一致します&nbsp;<code>HEX</code><code>Z</code><em><u></u></em><code>"K" (NONCES)</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>これは非常に重大な ECDSA 署名エラーです</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>上で述べたように、ポラード カンガルー法では、公開鍵</em>&nbsp;または<em>&nbsp;署名</em>&nbsp;値を知っていれば十分です&nbsp;<code>R</code>&nbsp;(値は&nbsp;&nbsp;、楕円曲線平面上の&nbsp;&nbsp;座標点であるため、&nbsp;&nbsp;公開&nbsp;<em>鍵</em><code>R</code>&nbsp;の一種でもあります&nbsp;)。<em></em><code>Nonces</code><code>x</code><code>secp256k1</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;この場合の<em>署名</em>&nbsp;値&nbsp;:<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 83fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>スクリプトは、&nbsp;<em>圧縮された公開鍵</em>&nbsp;を作成することにより、&nbsp;<code>RangeNonce</code>&nbsp;必要な&nbsp;<em>プレフィックスを追加しました</em>&nbsp;<code>02</code><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K_PUBKEY = 0283fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>これで情報が得られました：</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>秘密鍵の範囲</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>圧縮された公開鍵</em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>ソース コードを使用して、&nbsp;&nbsp;フランスの開発者 Jean-Luc PONS の<a href="https://github.com/demining/CryptoDeepTools/tree/main/06KangarooJeanLucPons" target="_blank" rel="noreferrer noopener"><strong>Pollard's Kangarooプログラムを作成してみましょう。</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><em><u>計算速度を</u></em></strong>&nbsp;上げる&nbsp;<code>CUDA</code>&nbsp;ために&nbsp;、自分で組み立てることができることに注意してください&nbsp;。<code>GPU</code><strong><em><u></u></em></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/afc/280/ae8/afc280ae86d3febb27f1008e8927ae89.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>CPUの通常の組み立てを行います</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>チーム:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd /

cd content/CryptoDeepTools/06KangarooJeanLucPons/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/394/ece/ecf/394eceecf11f26952a6fc87a10be2dbc.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt-get update</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2bc/e90/cd5/2bce90cd55b48787511363f9976adbd6.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt-get install g++ -y
sudo apt-get install libgmp3-dev libmpfr-dev -y</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/707/e19/0da/707e190da23fd6b83eead65bce771b5b.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em>すべてのパッケージのインストール後、簡単なコマンドを実行してビルドします。</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>make</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/663/476/ae3/663476ae36f13e98d23f8ee3e879b545.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/1ea/932/dd2/1ea932dd2bd751c24fa95821c6833523.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>組み立て成功！</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Проверим версию:

./kangaroo -v</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/76d/f52/532/76df5253202c44d068af867a812d11db.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>そこで、「カンガルー v2.2」のバージョンを作成しました。</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>のパフォーマンスを実証するために、&nbsp;<code>«Kangaroo v2.2»</code>&nbsp;範囲&nbsp;<code>CPU</code>を上げてすべてをファイルに保存してみましょう。&nbsp;<code>rangepubkey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>テキスト ファイルを開きます: rangepubkey.txt</h4>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8ac/477/f4c/8ac477f4c2423dc5ff4cce2407481540.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>070239c013e8f40c8c2a0e608ae15a6b23d4a09295be678b2100000000000000
070239c013e8f40c8c2a0e608ae15a6b23d4a09295be678b21ffffffffffffff
0283fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Очистим терминал командой:

clear</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>実行すると、&nbsp;<code>«Kangaroo v2.2»</code>&nbsp;結果が&nbsp;<em>自動的に</em>&nbsp;ファイルに保存されます。&nbsp;<code>savenonce.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./kangaroo -ws -w save.work -wi 30 -o savenonce.txt rangepubkey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ae8/77a/6f4/ae877a6f49f7781d70cf6a986deea751.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/5eb/0b2/2e3/5eb0b22e395bd62b5a577a37ba2bebef.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e2d/6a1/e3a/e2d6a1e3ab4cd4bb5be0c58eed1ca6f7.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>検索時間は 1 分でした。18秒</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>ファイルの結果:</em>&nbsp;<code>savenonce.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/76b/fb1/f4e/76bfb1f4e28f14cebba9b68c31e510ec.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em></em>&nbsp;ファイル&nbsp;<em>を開きましょう:</em><code>savenonce.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/50d/1fd/7ae/50d1fd7aecc8ea69cdb12d8f73830d8b.png" alt="ポラードのカンガルーは、既知の範囲で離散対数 secp256k1 PRIVATE KEY + NONCES の解を見つけます"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>秘密鍵を取得しました。これが「K」の値です (NONCES)</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Key# 0 &#91;1S]Pub:  0x0283FE1C06236449B69A7BEE5BE422C067D02C4CE3F4FA3756BD92C632F971DE06 
       Priv: 0x70239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634 


070239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634

K = 070239c013e8f40c8c2a0e608ae15a6b00000000000000000000000000000000 # RangeNonce
K = 070239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634 # NONCES
K = 070239c013e8f40c8c2a0e608ae15a6bffffffffffffffffffffffffffffffff # RangeNonce</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>秘密鍵</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>値がわかったので、&nbsp;<em><u>秘密鍵を</u></em>&nbsp;ビットコイン アドレスに&nbsp;復元し<code>"K" (NONCES)</code>&nbsp;ます&nbsp;:&nbsp;<a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong>14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</strong></a><em><u></u></em><a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最初に戻りましょう。覚えているように、スクリプトは&nbsp;値の範囲に関する&nbsp;<em>情報</em>と&nbsp;<em>情報</em><code>«RangeNonce»</code>&nbsp;を明らかにしました&nbsp;。<em></em><code>"K" (NONCES)</code><em></em>&nbsp;<code>SIGNATURES</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d71/0d3/fa1/d710d3fa1cf97ab16e33f7f824c2fb87.png" alt="署名" title="署名"/><figcaption class="wp-element-caption">署名</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 83fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06
S = 7405249d2aa9184b688f5307006fddc3bd4a7eb89294e3be3438636384d64ce7
Z = 070239c013e8f40c8c2a0e608ae15a6b1bb4b8fbcab3cff151a6e4e8e05e10b7</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>Pythonスクリプト</em>の数式を使用して秘密鍵を取得します:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/b40/7d2/80e/b407d280edbe126f6ec21ac1c1ffa539.svg" alt="PRIVKEY = ((((S * K) - Z) *​​ modinv(R,N)) % N)"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>def</strong> <strong>h</strong>(n):
    <strong>return</strong> hex(n).replace("0x","")

<strong>def</strong> <strong>extended_gcd</strong>(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    <strong>while</strong> remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    <strong>return</strong> lastremainder, lastx * (-1 <strong>if</strong> aa &lt; 0 <strong>else</strong> 1), lasty * (-1 <strong>if</strong> bb &lt; 0 <strong>else</strong> 1)

<strong>def</strong> <strong>modinv</strong>(a, m):
    g, x, y = extended_gcd(a, m)
    <strong>if</strong> g != 1:
        <strong>raise</strong> ValueError
    <strong>return</strong> x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141
R = 0x83fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06
S = 0x7405249d2aa9184b688f5307006fddc3bd4a7eb89294e3be3438636384d64ce7
Z = 0x070239c013e8f40c8c2a0e608ae15a6b1bb4b8fbcab3cff151a6e4e8e05e10b7
K = 0x070239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634

<strong>print</strong> (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>チーム:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>wget https://raw.githubusercontent.com/demining/CryptoDeepTools/main/02BreakECDSAcryptography/calculate.py

python3 calculate.py
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/803/1f1/189/8031f11893dbb7de1d90858ae8ba634a.png" alt="PRIVKEY=23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf81652664714​​01b" title="PRIVKEY=23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf81652664714​​01b"/><figcaption class="wp-element-caption">PRIVKEY=23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf81652664714​​01b</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE
WIF:  5J64pq77XjeacCezwmAr2V1s7snvvJkuAz8sENxw7xCkikceV6e
HEX:  23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d8c/78d/8eb/d8c78d8eb14e5246b495e09f59631e44.png" alt="bitaddress の Web サイトで秘密鍵を確認する" title="bitaddress の Web サイトで秘密鍵を確認する"/><figcaption class="wp-element-caption">bitaddress の Web サイトで秘密鍵を確認する</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>秘密鍵が見つかりました！</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ed9/7da/c1d/ed97dac1dc07e2bce09fe0951d9f64de.png" alt="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" title="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE"/><figcaption class="wp-element-caption">www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>このビデオは、 CRYPTO DEEP TECH</strong></a>ポータル向けに作成されたもので、&nbsp;&nbsp;暗号通貨&nbsp;<code>secp256k1</code>&nbsp;の弱い署名に対して&nbsp;&nbsp;楕円曲線上でデータと暗号の財務的セキュリティを確保します。&nbsp;<code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/06KangarooJeanLucPons" target="_blank" rel="noreferrer noopener"><strong><u>ソース</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>テレグラム:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong>https://t.me/cryptodeeeptech</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>動画素材：&nbsp; https:&nbsp;<a href="https://youtu.be/UGUJyxOhBBQ" target="_blank" rel="noreferrer noopener">//youtu.be/UGUJyxOhBBQ</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>ソース:&nbsp;&nbsp;</strong><a href="https://cryptodeep.ru/kangaroo" target="_blank" rel="noreferrer noopener"><strong>https://cryptdeep.ru/kangaroo</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2402} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/010-1024x576.png" alt="Pollard's Kangaroo находим решения дискретного логарифма secp256k1 PRIVATE KEY + NONCES в известном диапазоне" class="wp-image-2402"/></figure>
<!-- /wp:image -->
