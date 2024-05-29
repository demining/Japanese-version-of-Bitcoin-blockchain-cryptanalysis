# Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する

<!-- wp:embed {"url":"https://www.youtube.com/embed/r0fTtBDWTnw","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/r0fTtBDWTnw
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>ビットコイン ウォレットを作成するには、さまざまな形式があります。ビットコイン ウォレットを作成する最初の方法の 1 つは、&nbsp;&nbsp;<a href="https://en.bitcoin.it/wiki/Brainwallet" target="_blank" rel="noreferrer noopener"><strong>BrainWallet</strong></a>として知られていました。<br><code>BrainWallet</code>&nbsp;メモリやノートに保存できるという意味で便利な&nbsp;<em>「<u>パスフレーズ</u>」</em>&nbsp;.&nbsp;パスフレーズはアルゴリズムを使用してハッシュされ&nbsp;、<a href="https://en.bitcoin.it/wiki/Private_key" target="_blank" rel="noreferrer noopener"><strong><u>秘密鍵を</u></strong></a><code>SHA-256</code>生成するためのシードとして使用されます&nbsp;。<a href="https://en.bitcoin.it/wiki/Private_key" target="_blank" rel="noreferrer noopener"><strong><u></u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>それらの人気と使いやすさのために、&nbsp;<code>BrainWallet</code>&nbsp;過去数年間、多くが脆弱なパスフレーズで使用されてきました。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><code>BTC</code>この脆弱な秘密鍵生成方法により、攻撃者は、ブロックチェーンに保存されているハッシュに対してパスワードをクラックするだけで、かなりの量のコインを盗むことができました&nbsp;。<a href="https://github.com/ryancdotorg" target="_blank" rel="noreferrer noopener"><strong>この攻撃は何年も前から知られていましたが、 Ryan Castellucci</strong></a><code>в 2015 году</code>&nbsp;の功績により&nbsp;広く知られるようになりました。&nbsp;<a href="https://github.com/ryancdotorg" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>2015 年 8 月 7 日</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Ryan Castellucci は&nbsp;<a href="https://youtu.be/foil0hzl4Pg" target="_blank" rel="noreferrer noopener"><strong>DEFCON23で、&nbsp;</strong></a><a href="https://en.bitcoin.it/wiki/Brainwallet" target="_blank" rel="noreferrer noopener"><strong>BrainWallet の</strong></a>パスワード&nbsp;のクラッキングについて&nbsp;話しました。パスフレーズは&nbsp;<code>BrainWallet</code>&nbsp;この時点で何年も使用されていましたが、会話はこれらの問題をより広く公開するのに役立ちました.</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/foil0hzl4Pg","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/foil0hzl4Pg
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>ドキュメント&nbsp;<a href="https://eprint.iacr.org/2019/023.pdf">[&nbsp;</a><a href="https://rya.nc/files/cracking_cryptocurrency_brainwallets.pdf" target="_blank" rel="noreferrer noopener">PDF ]</a>&nbsp;:&nbsp;<a href="https://rya.nc/files/cracking_cryptocurrency_brainwallets.pdf" target="_blank" rel="noreferrer noopener"><strong>仮想通貨ブレインウォレットのクラッキング Ryan Castellucci</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>&nbsp;Ryan は、 Proven Cryptocurrency Wallet Cracker&nbsp;<code>BrainWallet</code>&nbsp;と呼ばれるツール&nbsp;やその他の低エントロピー アルゴリズムと組み合わせたハッキン​​グに関する彼の研究の結果を公開しました&nbsp;。<code>BrainFlayer</code><code>BrainWallet</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>GPU アクセラレーション</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/87f/7ce/6d2/87f7ce6d2a7b0f55ea99f5b38033c904.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>現時点では、&nbsp;<code>пробный cracker</code>&nbsp;ライアンの&nbsp;<a href="https://github.com/ryancdotorg/brainflayer" target="_blank" rel="noreferrer noopener"><u>ブレインフレイヤーは</u></a><em>さまざまなソフトウェア、ユーティリティ、スクリプトなど</em>&nbsp;にアップグレードされています&nbsp;が、&nbsp;<em><u>GPU</u></em>&nbsp;ランタイムを&nbsp;サポートする&nbsp;ための&nbsp;<em><u>グラフィック アクセラレータは</u></em>まだ作成されています&nbsp;。<a href="https://www.nvidia.com/ru-ru/data-center/tesla-v100/" target="_blank" rel="noreferrer noopener">これらのアクセラレーターは、 NVIDIA® Tesla® V100</a>コンピューティング システム&nbsp;のファミリーにちなんで&nbsp;<a href="https://cryptodeeptech.ru/tesla-brainwallet" target="_blank" rel="noreferrer noopener">、TeslaBrainWallet</a>と呼ばれます&nbsp;。<code>BrainWallet</code><em><u></u></em><a href="https://cryptodeeptech.ru/tesla-brainwallet" target="_blank" rel="noreferrer noopener"></a><a href="https://www.nvidia.com/ru-ru/data-center/tesla-v100/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b97/5f5/0df/b975f50df1ff071705fc4660df86fcfe.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>フィッシング</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>多くのビットコインの支持者は、資金を没収される可能性から保護するための優れた方法としてよく引用します&nbsp;<code>BrainWallet</code>&nbsp;が、残念ながらビットコインには多くの落とし穴があります&nbsp;<code>Bitcoin клиента Electrum</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>Electrum</code>&nbsp;一般的なすべてのハードウェア ウォレット&nbsp;<em>(たとえば、&nbsp;</em><code>Trezor</code><em>など&nbsp;</em><code>Ledger</code><em>&nbsp;)</em>をサポートしていますが&nbsp;&nbsp;、ウォレットの機能を拡張するためにサードパーティのプラグインをインストールすることまでは可能ですが、古いバージョンのビットコイン ウォレットをインストールすると、すべてを失うリスクがあります。ウォレット内の暗号通貨コイン。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/f38/a38/705/f38a38705a61104eac3fec1fa281967b.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>このトラップは、単語の下で人気があります&nbsp;<code>"фишинг"</code>。暗号コミュニティには悲しい話がたくさんあります。金額のフィッシングからの最大の損失の 1 つ&nbsp;<code>1400 BTC (16 миллионов долларов США)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>仮想通貨業界ポータル</em>&nbsp;<a href="https://cryptopotato.com/real-or-ruse-this-bitcoiner-lost-1400-btc-16m-after-installing-an-old-electrum-wallet/" target="_blank" rel="noreferrer noopener"><strong>「CryptoPotato」によると</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/53d/501/31d/53d50131d5bd815e8ab4e829f2c07127.png" alt="1,400 BTC (1,600 万ドル) の最大のフィッシング損失" title="1,400 BTC (1,600 万ドル) の最大のフィッシング損失"/><figcaption class="wp-element-caption">1,400 BTC (1,600 万ドル) の最大のフィッシング損失</figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ある名前の匿名のビットコイン投資家が&nbsp;日曜日に&nbsp;、人気のあるウォレットの古いバージョンを「ばかげて」インストールした後に&nbsp;<code>«1400BitcoinStolen»</code>&nbsp;負けたと主張しましたが&nbsp;、それは<a href="https://cryptopotato.com/real-or-ruse-this-bitcoiner-lost-1400-btc-16m-after-installing-an-old-electrum-wallet/" target="_blank" rel="noreferrer noopener"><strong><em><u>フィッシング詐欺</u></em></strong></a>であることが判明しました&nbsp;。<code>1400 BTC</code><code>Electrum</code><a href="https://cryptopotato.com/real-or-ruse-this-bitcoiner-lost-1400-btc-16m-after-installing-an-old-electrum-wallet/" target="_blank" rel="noreferrer noopener"><strong><em><u></u></em></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>トラップ：</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>不愉快な事件を説明すると、被害者は資金にアクセスできなかったと述べました&nbsp;<code>с 2017 года</code>。ウォレットを設定して送金を試みた後、&nbsp;<code>1 BTC</code>&nbsp;送金前にセキュリティ システムを更新するよう求めるポップアップ メッセージが表示されました。残念ながら、これは&nbsp;<strong><u>罠</u></strong>であり&nbsp;、&nbsp;<strong><u>フィッシングの</u></strong>試みでした。被害者によると、彼は&nbsp;<strong><u>更新プログラムをインストールし</u></strong>、すべての資金が自動的にハッカーのウォレット アドレスに転送され、詐欺師はより裕福になったとのことです&nbsp;<code>на 16 миллионов долларов США</code>。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>フィッシングの被害に遭わないためには？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>初期の投稿では、すべての人に次のことを強くお勧めします。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>実績のあるソフトウェアのみを使用してください。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ソースコードを参照してください。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>自分で組み立てます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>更新を行います。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2>弱いパスフレーズ</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4>実験的な部分に移りましょう:</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]</strong></a>を開きます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/13TeslaBrainWallet" target="_blank" rel="noreferrer noopener"><strong>「13TeslaBrainWallet」</strong></a>リポジトリ&nbsp;を利用してみましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/13TeslaBrainWallet/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ea4/a8b/182/ea4a8b182c3f2dec717d0ba5065814ff.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>Python 2.7 用の pip2 をインストールしましょう</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>(2022 年 9 月 20 日以降は の&nbsp;</em><em>&nbsp;デフォルトを&nbsp;</em><code>Google Colab</code><em>&nbsp;使用しない&nbsp;ため</em><em>)</em><code>"pip2"</code><em></em><code>"Python 2.7"</code><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e6a/ce0/283/e6ace0283266b3d45070bdd532608002.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d08/ae0/e67/d08ae0e674562990102e79f241632282.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/09c/d15/abe/09cd15abe73dc5e370ef9f25c75e5160.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>ECDSA 暗号署名ライブラリをインストールする</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip2 install ecdsa</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b32/9b6/c71/b329b6c7144dd2b8127fc10af35c1f65.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>Python スクリプトを実行します: teslaBTC.py</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4>BTCコインの残高がプラスの弱いパスフレーズの歴史</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener"><strong>ビットアドレス</strong></a>を開いて確認しましょう&nbsp;&nbsp;：</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python2</strong> <strong>teslaBTC</strong>.py "<strong>arretonprimaryschool</strong>"</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/244/db4/3c9/244db43c9b11dedf3623684d52223cbf.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Pass</strong> <strong>phrase</strong>: <strong>arretonprimaryschool</strong>
<strong>Private</strong> <strong>key</strong>: 0<strong>e57a34ee4cf2242bc331494981aa896e803c598cc4a0f890b2e85d6acb85f29</strong>
<strong>Bitcoin</strong> <strong>address</strong>: 16<strong>jLdtAxgXVwcG93MyPcNALXMCv3D6dyDB</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/19e/898/4f1/19e8984f167ef9016ab399abfbc02074.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python2</strong> <strong>teslaBTC</strong>.py "<strong>correct</strong> <strong>horse</strong> <strong>battery</strong> <strong>staple</strong>"</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/c75/873/10d/c7587310dafe93cfbc5cdf8cbcb22a6e.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Pass</strong> <strong>phrase</strong>: <strong>correct</strong> <strong>horse</strong> <strong>battery</strong> <strong>staple</strong>
<strong>Private</strong> <strong>key</strong>: <strong>c4bbcb1fbec99d65bf59d85c8cb62ee2db963f0fe106f483d9afa73bd4e39a8a</strong>
<strong>Bitcoin</strong> <strong>address</strong> <strong>U</strong>: 1<strong>JwSSubhmg6iPtRjtyqhUYYH7bZg3Lfy1T</strong>
<strong>Bitcoin</strong> <strong>address</strong> <strong>C</strong>: 1<strong>C7zdTfnkzmr13HfA2vNm5SJYRK6nEKyq8</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/97a/03c/687/97a03c68708ccf42ff0d8353c9d08840.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する" title=""/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/308/83e/3b4/30883e3b410d3a03e451b37e40d2f40f.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python2</strong> <strong>teslaBTC</strong>.py "<strong>This</strong> <strong>is</strong> <strong>the</strong> <strong>way</strong> <strong>the</strong> <strong>world</strong> <strong>ends</strong>."</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ed0/d44/48b/ed0d4448b42141bdf4f04d1e7cc94865.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Pass</strong> <strong>phrase</strong>: <strong>This</strong> <strong>is</strong> <strong>the</strong> <strong>way</strong> <strong>the</strong> <strong>world</strong> <strong>ends</strong>.
<strong>Private</strong> <strong>key</strong>: 1<strong>bad2815705c693b4df94badf0f757c601d841bff62c40f9546432034a4c29b7</strong>
<strong>Bitcoin</strong> <strong>address</strong>: 1<strong>DnqpnCFiXqMhvRfdRzPcRao7yxyoeXgjf</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/594/d80/96f/594d8096f10f02e05286f74a2c81e16e.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python2</strong> <strong>teslaBTC</strong>.py "<strong>The</strong> <strong>quick</strong> <strong>brown</strong> <strong>fox</strong> <strong>jumps</strong> <strong>over</strong> <strong>the</strong> <strong>lazy</strong> <strong>dog</strong>"</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e14/d79/632/e14d796328d2f0958131e5219c684567.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Pass</strong> <strong>phrase</strong>: <strong>The</strong> <strong>quick</strong> <strong>brown</strong> <strong>fox</strong> <strong>jumps</strong> <strong>over</strong> <strong>the</strong> <strong>lazy</strong> <strong>dog</strong>
<strong>Private</strong> <strong>key</strong>: <strong>d7a8fbb307d7809469ca9abcb0082e4f8d5651e46d3cdb762d02d0bf37c9e592</strong>
<strong>Bitcoin</strong> <strong>address</strong>: 13<strong>w4Hn1BJQM4bjZZgYtXpyp4cioiw29tKj</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4cc/daf/14d/4ccdaf14d74e7379b9f160c509655bf7.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python2</strong> <strong>teslaBTC</strong>.py "<strong>just</strong> <strong>let</strong> <strong>the</strong> <strong>lovin</strong> <strong>take</strong> <strong>ahold</strong>"</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e74/1ef/7a2/e741ef7a2c8bd6a0cec046d677e41ee0.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Pass</strong> <strong>phrase</strong>: <strong>just</strong> <strong>let</strong> <strong>the</strong> <strong>lovin</strong> <strong>take</strong> <strong>ahold</strong>
<strong>Private</strong> <strong>key</strong>: 5<strong>e6fa5565782e85f3e305c422388e687e4fc8c2e7c572748f57ff7a4d6ff736a</strong>
<strong>Bitcoin</strong> <strong>address</strong>: 1<strong>H6nTPQ8wqdQ3QFrGc1qy9r63acpTAkwvc</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4fd/7cb/9c4/4fd7cb9c4c6a831453a577f91a1023f9.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python2</strong> <strong>teslaBTC</strong>.py "<strong>en</strong> <strong>un</strong> <strong>lugar</strong> <strong>de</strong> <strong>la</strong> <strong>mancha</strong>"</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/375/fb6/81d/375fb681d891de3e84642285103bf099.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Pass</strong> <strong>phrase</strong>: <strong>en</strong> <strong>un</strong> <strong>lugar</strong> <strong>de</strong> <strong>la</strong> <strong>mancha</strong>
<strong>Private</strong> <strong>key</strong>: <strong>e9f852cd97283461e254da265a27d2bda07f245cb5f8a6ee622355fcec63eb8c</strong>
<strong>Bitcoin</strong> <strong>address</strong>: 1<strong>Gwd5BQCDsFrEvokGkto945smazwEMKqdo</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/031/479/542/0314795429f25f2ba27fbf1521eb9cfc.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python2</strong> <strong>teslaBTC</strong>.py "<strong>The</strong> <strong>quick</strong> <strong>brown</strong> <strong>fox</strong> <strong>jumped</strong> <strong>over</strong> <strong>the</strong> <strong>lazy</strong> <strong>dog</strong>."</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/6c5/17c/7f8/6c517c7f8a99a9767987f0b6e2664cc2.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Pass</strong> <strong>phrase</strong>: <strong>The</strong> <strong>quick</strong> <strong>brown</strong> <strong>fox</strong> <strong>jumped</strong> <strong>over</strong> <strong>the</strong> <strong>lazy</strong> <strong>dog</strong>.
<strong>Private</strong> <strong>key</strong>: 68<strong>b1282b91de2c054c36629cb8dd447f12f096d3e3c587978dc2248444633483</strong>
<strong>Bitcoin</strong> <strong>address</strong>: 1<strong>E2Wgex1ZGfZ9gb4MBubJJ5bnABkk2pbZf</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/6a9/866/bf2/6a9866bf2cee350e2c2aa8a09ef20a26.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python2</strong> <strong>teslaBTC</strong>.py "<strong>Thats</strong> <strong>what</strong> <strong>she</strong> <strong>said</strong> 1974"</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d92/70c/13e/d9270c13ee19a7ea2ce3b19d66199a37.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Pass</strong> <strong>phrase</strong>: <strong>Thats</strong> <strong>what</strong> <strong>she</strong> <strong>said</strong> 1974
<strong>Private</strong> <strong>key</strong>: 0<strong>e3630f0f829d93afd8569f7c50aaced3d930353db8468d8c42b58d7f5ce1fdb</strong>
<strong>Bitcoin</strong> <strong>address</strong>: 113<strong>W1qXf6DsJFtqMnR53tqvLrVfjkjR7g5</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/dec/512/4a1/dec5124a1774b939cd296c4f68545a98.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python2</strong> <strong>teslaBTC</strong>.py "<strong>lorem</strong> <strong>ipsum</strong> <strong>dolor</strong> <strong>sit</strong> <strong>amet</strong>"</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/405/d4e/f3b/405d4ef3b31f46aef3b278cfff23ac17.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Pass</strong> <strong>phrase</strong>: <strong>lorem</strong> <strong>ipsum</strong> <strong>dolor</strong> <strong>sit</strong> <strong>amet</strong>
<strong>Private</strong> <strong>key</strong>: 2<strong>f8586076db2559d3e72a43c4ae8a1f5957abb23ca4a1f46e380dd640536eedb</strong>
<strong>Bitcoin</strong> <strong>address</strong>: 1<strong>KRGyNbq2yM1vAXscib74Snp6AUuUHVi2g</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b16/1d5/ae7/b161d5ae737830255fcf4f715f57a3b9.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4>文学：</h4>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.researchgate.net/publication/317235691_The_Bitcoin_Brain_Drain_Examining_the_Use_and_Abuse_of_Bitcoin_Brain_Wallets" target="_blank" rel="noreferrer noopener">金融暗号とデータ セキュリティに関する国際会議「ビットコインの頭脳流出: ビットコインの頭脳ウォレットの使用と乱用の調査」[マリー ヴァセック、ジョセフ ボノー、ライアン カステルッチ、キャメロン キース] ., 2017</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>このビデオは、 CRYPTO DEEP TECH</strong></a>ポータル向けに作成されたもので、&nbsp;&nbsp;暗号通貨&nbsp;<code>secp256k1</code>&nbsp;の弱い署名に対して&nbsp;&nbsp;楕円曲線上でデータと暗号の財務的セキュリティを確保します。&nbsp;<code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/13TeslaBrainWallet" target="_blank" rel="noreferrer noopener"><strong>ソース</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech"><strong>電報</strong></a><strong>:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong><u>https://t.me/cryptodeeeptech</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/r0fTtBDWTnw" target="_blank" rel="noreferrer noopener">動画素材：https://youtu.be/r0fTtBDWTnw</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/tesla-brainwallet" target="_blank" rel="noreferrer noopener"><strong>ソース:&nbsp;&nbsp;<u>https://cryptodeeep.ru/tesla-brainwallet</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2416} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/017-1024x576.png" alt="Tesla BrainWallet はビットコイン ウォレットからトラップし、フィッシングや一般的なパスフレーズに注意する" class="wp-image-2416"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
