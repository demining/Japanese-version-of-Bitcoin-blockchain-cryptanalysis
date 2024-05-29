# ブロックチェーン トランザクションを Google ドライブ フォルダに解析する方法

<!-- wp:embed {"url":"https://www.youtube.com/embed/ECAPypsmMQs","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/ECAPypsmMQs
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>この記事では、ビットコイン トランザクションを分析し、RawTX をブロックチェーン ネットワークから Google ドライブ フォルダーに非常に迅速に解析する方法を学習します。これはすべて、ビットコイン トランザクションがどのように機能し、そのすべてのコンテンツがブロックチェーン ネットワーク上にあるのかをよりよく理解するのに役立ちます。<br>まず、すべてのビットコイン トランザクションが [txid] に保存されていることを知る必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>txid</strong>&nbsp;はビットコイン ブロックチェーンに保存されるトランザクション ID で、RawTX はダブル ハッシュの形式で保存されます。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>これは、RawTX が SHA256 アルゴリズムを 2 回実行して、ブロックチェーンで確認できるトランザクション ハッシュを取得したことを意味します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>たとえば、次のハッシュを持つトランザクション:&nbsp;&nbsp;<a href="https://www.blockchain.com/btc/tx/d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f" target="_blank" rel="noreferrer noopener">d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ビットコイン ブロックチェーン上のトランザクションは、ダブル ハッシュの形式で保存されます。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>SHA256(SHA256(0100000001f2068914e2fea859cacd8df990daf4008f11296b3cb953794051147a265d850a000000008b483045022043784344e1e0cb498c1d73b4cee970fb0f9adf38b7891d0b1310fdb9cbc23929022100a734f4e97a05bd169a9f0eb296fc841fa57f8753db09869f8f6f8cc1232616d4014104d6597d465408e6e11264c116dd98b539740e802dc756d7eb88741696e20dfe7d3588695d2e7ad23cbf0aa056d42afada63036d66a1d9b97070dd6bc0c87ceb0dffffffff0100b864d9450000001976a9142df31a60b02cce392822c9a87198753578ef7de888ac00000000) = d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>RawTX を取得するには、トランザクション ID [txid] を入力するだけです。</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://blockchain.info/rawtx/[txid]?format=hex"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://blockchain.info/rawtx/[txid]?format=hex
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>さらにHEX形式で情報を受け取ります。これは大切なRawTXです。</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://blockchain.info/rawtx/d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f?format=hex"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://blockchain.info/rawtx/d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f?format=hex
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>しかし、私たちが知っているように、1 つのビットコイン アドレスに多くのトランザクション [txid] が存在する可能性があり、これが主な問題であり、見つけるのに多くの時間がかかり、PC に負荷がかかり、多くのディスク スペースを占有します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この問題を解決するには、&nbsp;<code>API</code>&nbsp;サイト&nbsp;<strong><a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener">https://chain.so/api/を使用してください。</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>そのため、bash スクリプトで 1 つの Bitcoin アドレスを指定します。&nbsp;<code>getrawtx.sh «address»</code>&nbsp;次に、前の出力ハッシュ全体を抽出します。すべての入力は出力を参照します。&nbsp;<code>(UTXO)</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>UTXO は、</strong>&nbsp;新しい入力に費やされる&nbsp;<em>(未使用のトランザクション出力)</em>&nbsp;です&nbsp;。<em>これのハッシュ値は&nbsp;</em><code>UTXO</code><em>&nbsp;逆順で格納されます。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>その結果、未使用のトランザクション出力はすべてファイルに保存されます。&nbsp;<code>«RawTX.json»</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ビットコイン アドレスを取得するには&nbsp;<code>RawTX</code>&nbsp;、&nbsp;&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/01BlockchainGoogleDrive/getrawtx.sh" target="_blank" rel="noreferrer noopener">Bash スクリプトを使用します: getrawtx.sh</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/7e4/268/a3a/7e4268a3ab7e36fc45020c6b222b7611.png" alt="Google ドライブでのブロックチェーンの解析" title="Google ドライブでのブロックチェーンの解析"/><figcaption class="wp-element-caption">Google ドライブでのブロックチェーンの解析</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>Google ドライブ フォルダに解析する方法は?</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">これを行うには、Google Colab [TerminalGoogleColab]</a></strong>のターミナルを使用できます。&nbsp;<strong><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以前にビデオ チュートリアルを録画しました&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener">。</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Bash スクリプトがどのように機能するかを詳しく見てみましょう: getrawtx.sh</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/060/833/01b/06083301bd4339d46a9a62e3d8bd606c.png" alt="Bash スクリプト: getrawtx.sh" title="Bash スクリプト: getrawtx.sh"/><figcaption class="wp-element-caption">Bash スクリプト: getrawtx.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>./getrawtx.sh 12ib7dApVFvg82TXKycWBNpN8kFyiAN1dr</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>Bitcoinユーティリティ</em>コマンドに指定したアドレス&nbsp;<em></em>&nbsp;<code>wget</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b68/785/9f6/b687859f62fd52efdfe6b536cf3040be.png" alt="ブロックチェーン トランザクションを Google ドライブ フォルダに解析する方法"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/338/b5b/10e/338b5b10ebb67a28ce79bcabb7ed4925.png" alt="すべてのコンテンツはファイルに保存されます: index.json" title="すべてのコンテンツはファイルに保存されます: index.json"/><figcaption class="wp-element-caption">すべてのコンテンツはファイルに保存されます: index.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:embed {"url":"https://chain.so/api/v2/get_tx_spent/BTC/12ib7dApVFvg82TXKycWBNpN8kFyiAN1dr"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://chain.so/api/v2/get_tx_spent/BTC/12ib7dApVFvg82TXKycWBNpN8kFyiAN1dr
</div></figure>
<!-- /wp:embed -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/073/505/252/07350525294fb491a864ca1d19c4c0f5.png" alt="grep ユーティリティは、すべての「txid」トランザクション ID を 1 つの共通の index2.json ファイルに保存します。  " title="grep ユーティリティは、すべての「txid」トランザクション ID を 1 つの共通の index2.json ファイルに保存します。  "/><figcaption class="wp-element-caption">grep ユーティリティは、すべてのトランザクション ID「txid」を 1 つの共通ファイル index2.json に保存します。</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b0e/fa6/edb/b0efa6edbf242f2f6f70bc1cc8b87640.png" alt="すべてのコンテンツはファイルに保存されます: index2.json" title="すべてのコンテンツはファイルに保存されます: index2.json"/><figcaption class="wp-element-caption">すべてのコンテンツはファイルに保存されます: index2.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4cb/904/b7a/4cb904b7a36460710dd6d51679c8317f.png" alt="index.json を削除" title="index.json を削除"/><figcaption class="wp-element-caption">index.json を削除</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/395/b95/c44/395b95c44bc13e60cbc0abb38c38108b.png" alt="sed ユーティリティを使用して、「txid」プレフィックスと引用符コンマを削除します" title="sed ユーティリティを使用して、「txid」プレフィックスと引用符コンマを削除します"/><figcaption class="wp-element-caption">sed ユーティリティを使用して、「txid」プレフィックスと引用符コンマを削除します</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/951/b67/986/951b6798689d0b357259abf07e711b5a.png" alt="ファイルの最終結果: index2.json" title="ファイルの最終結果: index2.json"/><figcaption class="wp-element-caption">ファイルの最終結果: index2.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/375/856/5cf/3758565cfb656de3fcc0069574fbd93c.png" alt="Echo ユーティリティを使用した Python スクリプトの作成" title="Echo ユーティリティを使用した Python スクリプトの作成"/><figcaption class="wp-element-caption">Echo ユーティリティを使用した Python スクリプトの作成</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/9f0/a0f/a55/9f0a0fa556623a5c9e436c0f0c118161.png" alt="Python スクリプト fileopen.py を実行します" title="Python スクリプト fileopen.py を実行します"/><figcaption class="wp-element-caption">Python スクリプト fileopen.py を実行します</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8cf/23f/c9c/8cf23fc9ce47c1fc907eb723b13c7c23.png" alt="Python スクリプト fileopen.py を実行すると、Bash スクリプト rawscript.sh が作成されます。" title="Python スクリプト fileopen.py を実行すると、Bash スクリプト rawscript.sh が作成されます。"/><figcaption class="wp-element-caption">Python スクリプト fileopen.py を実行すると、Bash スクリプト rawscript.sh が作成されます。</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/35a/f1b/200/35af1b20063d6255c73c95b6628cd111.png" alt="index2.json を削除" title="index2.json を削除"/><figcaption class="wp-element-caption">index2.json を削除</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e63/b09/091/e63b090910e9e2e08d47b61d0ceb065c.png" alt="Bash スクリプト rawscript.sh のアクセス許可を取得し、正常に実行しました。" title="Bash スクリプト rawscript.sh のアクセス許可を取得し、正常に実行しました。"/><figcaption class="wp-element-caption">Bash スクリプト rawscript.sh のアクセス許可を取得し、正常に実行しました。</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/f03/a8d/9c2/f03a8d9c2ecb1e3576e388c59bf33374.png" alt="スクリプトの削除 fileopen.py // rawscript.sh" title="スクリプトの削除 fileopen.py // rawscript.sh"/><figcaption class="wp-element-caption">スクリプトの削除 fileopen.py // rawscript.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e91/ddd/baa/e91dddbaa475462a42032e3b0f87cbc5.png" alt="すべてのトランザクションはファイル「RawTX.json」に保存されます。" title="すべてのトランザクションはファイル「RawTX.json」に保存されます。"/><figcaption class="wp-element-caption">すべてのトランザクションはファイル「RawTX.json」に保存されます。</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>その結果、どのような利点が得られますか。</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>RawTX の解析は高速で、すべてが Google ドライブ フォルダ内の 1 つのファイルに保存されます</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>getrawtransaction コマンドとは異なり&nbsp;<code>«txid»</code>、コンソールに&nbsp;<code>Bitcoin Сore</code>&nbsp;入力する必要はなく、&nbsp;<code>«txid»</code>&nbsp;ビットコイン アドレス&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">getrawtx.sh "address"を入力するだけです。</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>bash スクリプト:&nbsp;サイト&nbsp;<a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener">API&nbsp;</a><a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener">https://chain.so/api/</a>&nbsp;を使用して&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">getrawtx.sh を</a>実行すると&nbsp;、未使用のトランザクション出力が検出されます&nbsp;<a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener"></a><a href="https://chain.so/api/">&nbsp;</a><a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener"></a><code>(UTXO)</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>ソースコード:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>テレグラム:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>動画素材：&nbsp;&nbsp;<a href="https://youtu.be/ECAPypsmMQs" target="_blank" rel="noreferrer noopener">https://youtu.be/ECAPypsmMQs</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/ECAPypsmMQs","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/ECAPypsmMQs
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
