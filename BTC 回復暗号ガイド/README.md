# BTC 回復暗号ガイド

<!-- wp:embed {"url":"https://www.youtube.com/embed/imTXE4rGqHw"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/imTXE4rGqHw
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/17BTCRecoverCryptoGuide" target="_blank" rel="noreferrer noopener">この記事では、 Crypto Deep Tools</a>レポジトリにあるオープンソースのパスワード回復ツールとウォレット シード フレーズを詳しく見ていきます。また、誤ってニーモニックの一部を紛失したり忘れたりした場合や、暗号化中にミスを犯した場合の状況についても説明します。それを解読します。(したがって、空のウォレットが表示されるか、シードが無効であるというエラーが表示されます) ウォレットのパスワードまたはパスフレーズの回復では、パスワードが何であるかについて合理的な考えがある場合に主に役立ちます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>BTCRecover は</em>&nbsp;、オープン ソースのウォレット パスワードおよびシード回復ツールです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/" target="_blank" rel="noreferrer noopener">最善の策は、BTCRecover のインストール ガイドに従い、必要な復旧タイプの「クイック スタート」を読むことです。（または、いくつかの使用例を見てください）</a></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="usage-examples">使用例</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>このページでは、多くの異なる回復シナリオで BTCRecover を使用するためのセットアップと構文を示す多くの例へのリンクを提供します。(通常、対応する YouTube ビデオを使用)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>与えられたコマンドは、YouTube ビデオで示されている例を再現できるように、ほとんどそのままコピー アンド ペーストできます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>注:</strong>&nbsp;プラットフォームによっては、いくつかの変更が必要になる場合があります。多くの場合、「python」と「python3」を使用するなどの単純なものです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Python バージョン:</strong>&nbsp;これらのビデオの多くは、BTCRecover のさまざまなフォークを使用して作成されました。ここでのリソースとコマンドは若干異なる場合がありますが、Python3 でこのフォークを使用するように設計されています。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="seed-recovery">種子回収</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>基本的なシード リカバリ (さまざまなタイプのウォレットでのリカバリに使用する基本的なコマンドを示します)</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 id="basic-passwordpassphrase-recoveries">基本的なパスワード/パスフレーズの回復</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>このツールを Windows で実行している場合は、これらの例を直接コピーして貼り付けることができます。(それらはすべて、自動テストにある同じシードとアドレスを使用します)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>彼らは皆、ほとんどすぐに結果を見つけるでしょう。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="seed-based-recovery-notes">シードベースの回復に関する注意事項</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注意事項</strong>&nbsp;Seedrecover.py は、単純な「無効なメモニック」または「無効なシード」タイプのエラーの大部分について、デフォルトで結果が得られるように設定されています。(例: タイプミスのある無傷のシード バックアップがある場合)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>すべての一般的な派生パスで、サポートされている暗号通貨のすべてのアカウント タイプを検索します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最長で数時間かかる 4 つの検索フェーズが自動的に実行されます。1. 1 つのタイプミス 2. 2 つのタイプミス (1 つは完全に異なる BIP39 ワードを使用している可能性がある) 3. 3 つのタイプミス (1 つは完全に異なる BIP39 ワードを使用している可能性がある) 4. 2 つのタイプミス (完全に異なるワードである可能性がある)。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>完全にサポートされているウォレット</strong>&nbsp;(サポートされている暗号通貨用)</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>ハードウェアウォレット<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>レジャーナノXとS</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>トレザーワンとT</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>キープキー</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>セーフパル</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コールドカード</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bitbox02</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>キーストーン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コボボールト</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>エリパル</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>CoolWallet S (シード番号を BIP39 シード ワードに変換し、ビットコインとライトコインに –force-p2sh 引数を使用する必要があります…)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ソフトウェアウォレット<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Electrum – V1 シードと V2 シードの両方 (これには、Electrum-LTC、Electron-Cash などのフォークが含まれます)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コノミ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>わさび</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>エッジウォレット</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>菌糸体</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>エクソダス</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>トラストウォレット</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Metamask (Binance Chain Wallet Extension のようなクローンを含む)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>互換性の問題があるウォレット</strong>(派生基準に従っていないため…)</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>アトミックウォレット。(ETH (およびすべての ERC20 トークン) の非標準派生、&nbsp;&nbsp;<code>--checksinglexpubaddress</code>XRP で使用する必要があります)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>アブラウォレット。(非標準のシード形式、最初の単語は非 BIP39 の「at」、最後の 12 は BIP39 (およびチェックサム) ですが、派生を再現できません)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="examples">実験的な部分に移りましょう:</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]</strong></a>を開きましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>リポジトリ<strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/17BTCRecoverCryptoGuide" target="_blank" rel="noreferrer noopener">«17BTCRecoverCryptoGuide»</a></strong>を使用しましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/17BTCRecoverCryptoGuide/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1301} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-1024x561.png" alt="BTC 回復暗号ガイド" class="wp-image-1301"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>必要なすべてのパッケージ、モジュール、およびライブラリをインストールします</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip3 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1304} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-1-1024x474.png" alt="BTC 回復暗号ガイド" class="wp-image-1304"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1305} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-2-1024x375.png" alt="BTC 回復暗号ガイド" class="wp-image-1305"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>lscpu コマンドを使用して Google Colab のプロセッサ アーキテクチャを調べる</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>lscpu</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1325} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-7-1024x403.png" alt="BTC 回復暗号ガイド" class="wp-image-1325"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>Linux用のPyOpenCLのインストール</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python3-pyopencl</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1308} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-3-1024x491.png" alt="BTC 回復暗号ガイド" class="wp-image-1308"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>システムのテスト</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 -m btcrecover.test.test_passwords -v GPUTests</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1311} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-4-1024x359.png" alt="BTC 回復暗号ガイド" class="wp-image-1311"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-bitoin-recoveries">基本的なビトインの回復</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注:</strong>&nbsp;ほとんどの場合、seedrecover.py を実行するだけで済みます。それをダブルクリックして、グラフィカル インターフェイスに従うだけでもかまいません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ネイティブ Segwit アドレスの場合 – 欠落している単語が 1 つあり、アドレス生成の上限は 5 です (したがって、アドレスはそのアカウントの最初の 5 つのアドレスに含まれている必要があります)。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>python3 seedrecover.py --wallet-type bip39 --addrs bc1qv87qf7prhjf2ld8vgm7l0mj59jggm6ae5jdkx2 --mnemonic "element entire sniff tired miracle solve shadow scatter hello never tank side sight isolate sister uniform advice pen praise soap lizard festival connect" --addr-limit 5
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1312} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-5-1024x487.png" alt="BTC 回復暗号ガイド" class="wp-image-1312"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>P2SH Segwit アドレスの場合 – 欠落している単語が 1 つあり、アドレス生成の上限は 5 です (したがって、アドレスはそのアカウントの最初の 5 つのアドレスに含まれている必要があります)。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --wallet-type bip39 --addrs 3NiRFNztVLMZF21gx6eE1nL3Q57GMGuunG --mnemonic "element entire sniff tired miracle solve shadow scatter hello never tank side sight isolate sister uniform advice pen praise soap lizard festival connect" --addr-limit 5
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1313} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-6-1024x488.png" alt="BTC 回復暗号ガイド" class="wp-image-1313"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-cardano-recoveries">基本的なカルダノの回復</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>カルダノの回収については、こちらのメモも参照してください。Shelley-Era のベース アドレスまたはステーク アドレスを使用できます。(バイロン時代はサポートされていません)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>標準ベースアドレスを使用して、Ledger Nano からのシード、1 単語が欠落しています。(カルダノではアドレス生成制限は適用されません)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 seedrecover.py --wallet-type cardano --addrs addr1qyr2c43g33hgwzyufdd6fztpvn5uq5lwc74j0kuqr7gdrq5dgrztddqtl8qhw93ay8r3g8kw67xs097u6gdspyfcrx5qfv739l --mnemonic "wood blame garbage one federal jaguar slogan movie thunder seed apology trigger spoon basket fine culture boil render special enforce dish middle antique"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>標準のベース アドレスを使用して、1 つの単語が欠落している Trezor からのシード。(カルダノではアドレス生成制限は適用されません)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 seedrecover.py --wallet-type cardano --addrs addr1q8k0u70k6sxkcl6x539k84ntldh32de47ac8tn4us9q7hufv7g4xxwuezu9q6xqnx7mr3ejhg0jdlczkyv3fs6p477fqxwz930 --mnemonic "ocean kidney famous rich season gloom husband spring convince attitude boy"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Yoroi、Adalite、または Daedalus からのシード (ソフトウェア ウォレットとして機能)、標準のステーク アドレスを使用</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>python3 seedrecover.py --wallet-type cardano --addrs stake1uxztdzzm4ljw9a0qmgregc8efgg56p2h3kj75kc6vmhfj2cyg0jmy --mnemonic "cave table seven there limit fat decorate middle gold ten battle trigger luggage demand"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-tron-recoveries">基本トロン回復</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>欠落している単語が 1 つ、アドレスの生成制限が 1 です (したがって、アドレスは最初のアカウントにある必要があります)。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 seedrecover.py --wallet-type tron --addrs TLxkYzNpMCEz5KThVuZzoyjde1UfsJKof6 --mnemonic "have hint welcome skate cinnamon rabbit cable payment gift uncover column duck scissors wedding decorate under marine hurry scrub rapid change roast print arch" --addr-limit 1
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-helium-recoveries">基本的なヘリウム回収</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>欠けている一言</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 seedrecover.py --wallet-type helium --addrs 13hP2Vb1XVcMYrVNdwUW4pF3ZDj8CnET92zzUHqYp7DxxzVASbB --mnemonic "arm hundred female steel describe tip physical weapon peace write advice"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-polkadotsubstrate-recoveries">基本的なポルカドット（基質）の回復</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ひとつの欠けた言葉、空白の秘密の導出経路</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 seedrecover.py --wallet-type polkadotsubstrate --addrs 13SsWBQSN6Se72PCaMa6huPXEosRNUXN3316yAycS6rpy3tK --mnemonic "toilet assume drama keen dust warrior stick quote palace imitate music disease"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>欠落している 1 つの単語、「//hard/soft///btcr-test-password」の秘密の派生パス ソフト/ハード派生パスは、-substrate-path 引数を介してプログラムに渡され、パスワードはパスワードと同じように扱われます。パスフレーズ (先頭の /// なし)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>python3 seedrecover.py --wallet-type polkadotsubstrate --addrs 12uMBgecqfkHTYZE4GFRx847CwR7sfs2bTdPbPLpzeMDGFwC --mnemonic "toilet assume drama keen dust warrior stick quote palace imitate music disease" --passphrase-arg btcr-test-password --substrate-path //hard/soft
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-stacks-recoveries">基本スタック回復</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>欠落している単語が 1 つ、アドレス生成の制限が 10 です。(したがって、特定のシードの最初の 10 個の「アカウント」がチェックされます)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>python3 seedrecover.py --wallet-type stacks --addrs SP11KHP08F4KQ06MWESBY48VMXRBK5NB0FSCRP779 --mnemonic "hidden kidney famous rich season gloom husband spring convince attitude boy" --addr-limit 10
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>12 ワード BIP39 シードのデスクランブル (Electrum Legacy、Electrum Segwit、BIP39 Bitcoin、および BIP39 Ethereum のスクランブル解除シードに TokenList を使用する方法を示します)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="descrambling-12-word-seeds">12 個の単語シードのデスクランブル</h1>
<!-- /wp:heading -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/ruSF8OKwBRk"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/ruSF8OKwBRk
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>これらのテスト用に、3 種類のトークン ファイルが用意されています。最初のチェックで結果を見つけるトークン ファイル、最後の可能な組み合わせとして結果を見つけるトークン ファイル、およびその間のある時点で結果を見つけるトークン ファイル。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これにより、物事が機能していることをすばやく確認し (最初の結果を調べる)、完全な実行にかかる時間を把握し (最後の結果)、現実世界の状況を代表する何かを試すことができるようになります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>12 ワードのシードをデスクランブするだけの場合、-no-eta なしで実行する意味はあまりありません。テストするシードの数は簡単に計算でき、シード ジェネレーターは少なくとも 48 スレッドに簡単に対応できるからです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>注:</strong>&nbsp;&nbsp;YouTube のビデオと例は、OpenCL アクセラレーションが Blockchain.com ウォレットに追加される前に作成されたもので、パフォーマンスが 2 倍向上する可能性があります。(詳細については、GPU アクセラレーションを参照してください)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>パフォーマンス</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>48 コアの Linode では、次のことが期待できます。 * 12 ワードの Electrum シードを 15 分以内にデスクランブルします。 * 12 ワードの BIP39 シードを 50 分以内にデスクランブルします。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>現在 (2020 年半ば) のミッドレンジ CPU では、この約 5 倍の時間がかかると予想できます。</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="electrum">エレクトラム</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="legacy-wallet-last-result">レガシー ウォレット (最終結果)</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist lastcombination_electrum.txt の使用</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>book fit fly ketchup also elevator scout mind edit fatal where rookie</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --addr-limit 1 --addrs 1CU62HPowYSxhHiiNu1ukSbMjrkGj4x52i --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/lastcombination_electrum.txt --wallet-type electrum2
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="segwit-wallet">セグウィットウォレット</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist randomcombination_electrum.txt の使用</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>social shoe spin enlist sponsor resource result coffee ocean gas file paddle</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type electrum2 --addr-limit 1 --addrs bc1qtylwmarke39nysxepdx5xzfatvrlel5z8m0jx2 --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/randomcombination_electrum.txt --bip32-path "m/0'/0"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="bip39">BIP39</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="ethereum-address-default-derivation-path-for-trezor-mew">イーサリアム アドレス (Trezor、MEW の既定の派生パス)</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist randomcombination_bip39.txt の使用</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>boy hidden kidney famous spring convince rich season gloom ocean husband attitude</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type ethereum --addr-limit 1 --addrs 0x66F9C09118B1C726BC24811a611baf60af42070A --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/randomcombination_bip39.txt --bip32-path "m/44'/60'/0'/0"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="legacy-btc-address-first-result">レガシー BTC アドレス (最初の結果)</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist firstcombination_bip39.txt の使用</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>boy attitude convince spring husband gloom season rich famous kidney hidden ocean</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/firstcombination_bip39.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="legacy-btc-address-last-result">レガシー BTC アドレス (最終結果)</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist lastcombination_bip39.txt の使用</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>ocean hidden kidney famous rich season gloom husband spring convince attitude boy</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/lastcombination_bip39.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="litecoin-native-segwit-address-seed-with-positional-anchors-for-known-words-last-word-as-any-valid-bip39-word-starting-with-b">Litecoin ネイティブ Segwit アドレス (既知の単語の位置アンカーを含むシード、最後の単語は「B」で始まる有効な BIP39 単語)</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist fixedwords_bip39.txt の使用</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>^1^ocean ^2^ocean ^3^ocean ^1^hidden ^2^hidden ^3^hidden ^1^kidney ^2^kidney ^3^kidney ^4^famous ^5^rich ^6^season gloom husband spring convince attitude baby bachelor bacon badge bag balance balcony ball bamboo banana banner bar barely bargain barrel base basic basket battle beach bean beauty because become beef before begin behave behind believe below belt bench benefit best betray better between beyond bicycle bid bike bind biology bird birth bitter black blade blame blanket blast bleak bless blind blood blossom blouse blue blur blush board boat body boil bomb bone bonus book boost border boring borrow boss bottom bounce box boy bracket brain brand brass brave bread breeze brick bridge brief bright bring brisk broccoli broken bronze broom brother brown brush bubble buddy budget buffalo build bulb bulk bullet bundle bunker burden burger burst bus business busy butter buyer buzz</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs ltc1q9srpp39hev6dpsxjjp8t5g0m3z7509vc9llalv --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/fixedwords_bip39.txt --bip32-path "m/84'/2'/0'/0"
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>マルチデバイス デスクランブリング 12 ワード シードとエクストラ ワード (「必須」アンカー、「位置」アンカー、および複数のデバイスにまたがる作業の分散を示します)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="required-anchors-positional-anchors-and-spreading-work-accross-multiple-devices">「必須」アンカー、「位置的」アンカー、および複数のデバイスへの作業の分散</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>YouTube ビデオはここにあります: TBC</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="background"><strong>バックグラウンド</strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>&nbsp;潜在的な単語のトークンリストを使用して BIP39 シードを簡単にデスクランブルできることに加えて、BTCRecover は、シード フレーズに追加のおとり単語がありながら、<em>いくつかの</em>単語の位置を知っている可能性がある状況でも使用できます。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>使用中のトークンリストの例: tokenlist.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17</td><td><code>+ ^1^ocean + ^2^hidden + ^3^kidney famous + ^5^rich + ^6^season + ^7^gloom husband spring + ^10^convince + ^11^attitude + ^12^boy glove section chunk brick sauce</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>大規模なリカバリ ジョブの場合、BTCRecover を使用すると、ワークロードを複数のデバイスに分散させることもできます。<strong>BTCRecover が使用するプロセスは決定</strong>論的であることを理解することが重要です。&nbsp;&nbsp;これが簡単に言えば、BTCRecover を実行するたびに、潜在的なパスワード/パスフレーズがまったく同じ順序で毎回検索されるということです。つまり、–workers コマンドを使用せずに 2 つのデバイスで同時に実行すると、単純に同じ作業を 2 回実行することになります…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>さいわい、検索をスライスに分割して、これらのスライスを異なるデバイスに割り当てることができます。このメカニズムは非常に単純で、基本的に「ラウンド ロビン」スケジューリング スタイルでパスワードを割り当てます。(例: 作業が 3 つのデバイスの 3 つのスライスに分割されている場合、各デバイスは 3 つ目のパスワードごとに処理します)その他。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>では、PC1 と PC2 という 2 つのデバイスの例を考えてみましょう。この例では、PC1 は PC2 の 2 倍の能力があるため、作業の 2/3 が割り当てられ、PC2 には 1/3 が割り当てられます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="practical-limits">実用上の限界</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>このような状況で潜在的なパスワードがいくつあるかを調べるのは非常に簡単です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>たとえば、20 個の単語のリストがあり、そのうち 3 個が 12 個の単語シード内での位置を知っている場合、次のようになります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>17 * 16 * 15 * 14 * 13 * 12 * 11 * 10 * 9 = 8,821,612,800 の可能なシード (使用可能な CPU パワーに応じて、数日で非常に実行可能)</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="running-btcrecover">BTCRecover の実行</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>両方の PC に BTCRecover をインストールする必要があり、PC ごとに異なる –worker コマンドを除いて、両方とも同じコマンドを使用します。(このトークンリストがテストする非常に小さなセットしか生成しないという事実は無視できます)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>デバイスは同じオペレーティング システムを実行している必要はなく、相互に通信する必要もありません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="command-on-pc-1">PC 1 のコマンド</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>したがって、ワーク スライス 1 と 2 を PC1 に割り当てます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-23_multi_device_descrambling_12_word_seed_with_extras/tokenlist.txt
 --no-eta --worker 1,2/3
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="command-on-pc-2">PC 2 のコマンド</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>そしてワークスライス3をPC2へ</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-23_multi_device_descrambling_12_word_seed_with_extras/tokenlist.txt
 --no-eta --worker 3/3
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="the-outcome">結果…</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>この例では、正しいシード フレーズが PC2 によって検出されます。デバイス間に通信がないため、PC1 は検索スペースを使い果たすまで検索を続けます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これは、このコマンドを使用するときに何をしているのかに注意を払う必要があることも強調しています。誤って PC に作業共有を割り当てるのを忘れたり、同じ共有を 2 回割り当てたりした場合、BTCrecover はこれが発生したことを知る方法がなく、テストされていない共有で正しいパスワードが発生した場合、結果は見つかりません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="closing-thoughts">最後に</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>–no-eta コマンドを使用すると、デバイスがパスワードをチェックしている現在の速度が表示されるため、このような状況で役立ちます。こちらもすぐに起動します。（クラウドサーバー時間にお金を払っている場合、これは良いことです）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このコマンドを使用すると便利な方法の 1 つは、PC でパスワード検索を既に開始していて、チェックする必要があるパスワードの数がわかっている場合、–no-eta を使用して実行する速度を上げ、手動で作業することです。物事にかかる時間。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1 台のデバイスでシード リカバリを開始し、複数デバイスのセットアップに移行したいが、1 台のデバイスで既にテスト済みのパスワードを再確認したくない場合は、単一のデバイスがテストされ、複数のデバイスでテストを再開するときに –skip コマンドを使用するだけです。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>トークンリスト ベースのシード リカバリで単語をグループ化する (互いに続くことが知られている複数の単語グループが存在する 24 単語シードのスクランブル解除を示しますが、シード内のこれらのグループの位置は不明です)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="grouping-words-together-in-tokenlist-based-seed-recoveries">トークンリスト ベースのシード リカバリで単語をグループ化する</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="background">バックグラウンド</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>場合によっては、誰かが順序がわからないような方法でシードを書き込んだり、バックアップを複数の部分に分割したりするリカバリがあります。いずれにせよ、これは、相対的な順序がわかるような方法で単語がグループ化されていることを意味しますが、より大きなシード内でのこれらの単語の位置はわかりません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このような状況では、&nbsp;&nbsp;<code>,</code>&nbsp;tokenlist 内の単語に単一のコンマ文字 (スペースなし、単一のコンマのみ) を使用して、提供された順序で単語を一緒に使用する必要があることを示すことができます。これは「相対アンカー」機能に似ていますが、はるかに効率的であり、複数の単語のグループ化も可能です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>グループ化された単語トークンは、他のタイプのアンカー、位置などと組み合わせて使用​​することもできます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これらのトークンを使用すると、トークンの数がニーモニックの長さと等しくならないことも意味します (通常、単一の単語トークンを使用したデスクランブルの場合と同様)。そのため、 および 引数を使用して、試行するトークンの最小数を指定することもでき&nbsp;<code>--min-tokens</code>&nbsp;ます&nbsp;<code>--max-tokens</code>&nbsp;。与えられたシード推測に対して。(コンマで区切られた単語のグループは、1 つのトークンとしてカウントされます)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>シードのデスクランブリングと同様に、この種の回復の上限はトークンの数に基づいており、一般に (位置アンカーなしで) 最大トークンがあります!&nbsp;(max-tokens factorial) チェックする可能性のあるシード。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="example">例</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>次の例では、次のトークン リストを使用します。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>^basic,dawn,renew,punch,arch,situate arrest,question,armor hole,lounge,practice resist zoo,zoo,zoo indicate,call lens,group,empty zoo husband verify,eternal,injury battle,satoshi brother,damp,this</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>このトークンリストには、正しい順序であると確信しているトークンのブロックがいくつかあることがわかります (シード ワードのグループの 1 つの位置アンカーを含む) と、余分な単語または単一の単語がいくつかあります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>そして、次のコマンドで実行されます (結果は数秒で見つかります)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --tokenlist ./docs/Usage_Examples/2022-04-02_Seed_Tokenlist_TokenBlocks/tokengroups_tokenlist.txt --mnemonic-length 24 --language en --wallet-type bip39 --addrs 1PTcESpqrmWePYB5h18Ni11QTKNfMkdSYJ --dsw --addr-limit 10 --max-tokens 9 --min-tokens 8
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>正しいシードは次のとおりです。&nbsp;<code>basic dawn renew punch arch situate resist indicate call lens group empty brother damp this verify eternal injury arrest question armor hole lounge practice</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ご覧のとおり、これは上記の tokenlist ファイルに含まれるいくつかのトークン グループで構成されています。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="password-recovery">パスワードの復元</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>基本的なパスワード回復 (さまざまなタイプのウォレットでの回復に使用する基本的なコマンドを示します)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="basic-passwordpassphrase-recoveries">基本的なパスワード/パスフレーズの回復</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>これらの例はいずれも、さまざまなタイプのタイプミス、トークンリストなどに使用する引数には関係していません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このツールを Windows で実行している場合は、これらの例を直接コピーして貼り付けることができます。(それらはすべて、自動テストにある同じシードとアドレスを使用します)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>彼らは皆、ほとんどすぐに結果を見つけるでしょう。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>以下の基本的な例で使用される基本的なパスワードリスト</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>btcr-test-password btcr-test-password:p2pkh btcr-test-password:p2wpkh btcr-test-password:p2wpkh-p2sh btcrtestpassword2022</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 id="bip38-encrypted-paper-wallet-recovery">BIP38 暗号化されたペーパー ウォレットの回復。</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注記</strong>&nbsp;BIP38 ウォレットは sCrypt によって暗号化されるため、ブルート フォースに対して非常に遅くなります。これらのウォレットの GPU アクセラレーションは利用可能ですが、複数の GPU または CPU に比べて特に強力な GPU を使用しない限り、パフォーマンスは大幅に向上しません… (または、ある種の専用 OpenCL アクセラレーター)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>サポートされているウォレット</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.bitaddress.org/">bitaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://liteaddress.org/">liteaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://paper.dash.org/">paper.dash.org</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>そして、他のほぼすべての BIP38 暗号化された秘密鍵。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>コマンド</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ビットコインの場合 (コインを指定する必要はありません。デフォルトでビットコインがチェックされています)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 btcrecover.py --bip38-enc-privkey 6PnM7h9sBC9EMZxLVsKzpafvBN8zjKp8MZj6h9mfvYEQRMkKBTPTyWZHHx --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ライトコインの場合</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 btcrecover.py --bip38-enc-privkey 6PfVHSTbgRNDaSwddBNgx2vMhMuNdiwRWjFgMGcJPb6J2pCG32SuL3vo6q --bip38-currency litecoin --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ダッシュ用</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 btcrecover.py --bip38-enc-privkey 6PnZC9Snn1DHyvfEq9UKUmZwonqpfaWav6vRiSVNXXLUEDAuikZTxBUTEA --bip38-currency dash --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="bip39-passphrase-protected-wallets-electrum-extra-words">BIP39パスフレーズで保護されたウォレットとエレクトラム「エクストラワード」</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注</strong>&nbsp;BIP39 パスフレーズを参照するために使用される言語は、ベンダーによって異なる場合があります。「25 番目の単語」として語られることもあれば、「もっともらしい否認パスフレーズ」として語られることもあれば、単に「パスフレーズ」として語られることもあります。これはウォレットのパスワードや PIN とは異なることに注意してください。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>BIP39 パスフレーズでエラーが発生した場合の最も一般的な症状は、シードとパスフレーズが完全に空のアカウントのセットを生成し、残高や取引履歴がないことです。(すべての BIP39 パスフレーズは有効であるため、エラー メッセージは表示されません)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>BIP39 シードの回復は GPU アクセラレーションの恩恵を受けることができますが、現時点では BIP39 パスフレーズの回復には当てはまりません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以下のすべてのコマンド例では、アドレス生成制限が 10 に設定されているため、検索するアドレスはウォレットの最初の 10 個のアドレス内にある必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>サポートされているウォレット</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>BIP39/44 をサポートするほとんどのハードウェア ウォレット<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Trezor (ワン アンド T)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>レジャーナノ（S、X）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>キープキー</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コールドカード</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bitbox02</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コボボールトプロ</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP39/44 をサポートするほとんどのソフトウェア ウォレット<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Wasabi Wallet (Wasabi ではこれをウォレットのパスワードと呼びます)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>サムライウォレット</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コノミ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>菌糸体</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Zillet (「パスワードベース」のウォレット タイプとして BIP39 パスフレーズを参照)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>エレクトラム</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>エクソダス</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>コマンド</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本的な Bitcoin コマンドなので、指定する必要はありません&nbsp;<code>--wallet-type</code>&nbsp;。これは、追加のパラメーターを追加する必要なく、すべての Bitcoin アドレスの種類 (レガシー、Segwit、またはネイティブ Segwit) をサポートします。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>python3 btcrecover.py --bip39 --addrs 1AmugMgC6pBbJGYuYmuRrEpQVB9BBMvCCn --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "certain come keen collect slab gauge photo inside mechanic deny leader drop"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Bitcoin Electrum ウォレット コマンド。これらは BIP39 ではないため、&nbsp;<code>--wallet-type electrum2</code>&nbsp;これを使用する必要があります。追加のパラメータなしで、レガシー エレクトラム ウォレットと Segwit Electrum ウォレットの両方をサポートします。(ほとんどの Electrum Altcoin クローンでも動作します)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 btcrecover.py --wallet-type electrum2 --addrs bc1q6n3u9aar3vgydfr6q23fzcfadh4zlp2ns2ljp6 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "quote voice evidence aspect warfare hire system black rate wing ask rug"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Ethereum コマンドなので、指定する必要があります&nbsp;<code>--wallet-type</code>&nbsp;(ただし、暗黙に示されているため、引数を省略することができます&nbsp;<code>--bip39</code>&nbsp;)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 btcrecover.py --wallet-type ethereum --addrs 0x4daE22510CE2fE1BC81B97b31350Faf07c0A80D2 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Zilliqa コマンドなので、指定する必要があります&nbsp;(ただし&nbsp;、暗黙的に引数を<code>--wallet-type</code>&nbsp;省略することができます&nbsp;)。これは、追加のパラメーターを追加する必要なく、すべてのアドレス タイプ (Base16 および Bech32) をサポートします。<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>注: 現時点では、Ledger Nano シード/パスフレーズを回復するためのベースとして Zilliqa シード回復を使用することはできません。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 btcrecover.py --wallet-type zilliqa --addrs zil1dcsu2uz0yczmunyk90e8g9sr5400c892yeh8fp --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的なビットコイン キャッシュ コマンドなので、指定する必要があります&nbsp;(ただし&nbsp;、暗黙に示されているように、引数を<code>--wallet-type</code>&nbsp;省略することができます&nbsp;) これは、Cashaddres またはレガシー スタイルのアドレスのいずれかを受け入れます... これは、BSV のような BCH フォークでも機能します...<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>python3 btcrecover.py --wallet-type bch --addrs bitcoincash:qqv8669jcauslc88ty5v0p7xj6p6gpmlgv04ejjq97 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的なカルダノなので、特定する必要があります&nbsp;(ただし&nbsp;、暗示されているため、議論を&nbsp;<code>--wallet-type</code>&nbsp;省略することができます&nbsp;) カルダノの回復については、<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/bip39-accounts-and-altcoins/">ここのメモも参照してください。</a>&nbsp;これは、ベースアドレスまたはステークアドレスのいずれかを受け入れます... (バイロン時代のアドレスはサポートされていません))<code>--bip39</code><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/bip39-accounts-and-altcoins/"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>python3 btcrecover.py --wallet-type cardano --addrs addr1q90kk6lsmk3fdy54mqfr50hy025ymnmn5hhj8ztthcv3qlzh5aynphrad3d26hzxg7xzzf8hnmdpxwtwums4nmryj3jqk8kvak --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "ocean hidden kidney famous rich season gloom husband spring convince attitude boy"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>&nbsp;基本的なダッシュ コマンドです&nbsp;<code>--wallet-type</code>&nbsp;。&nbsp;<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>python3 btcrecover.py --wallet-type dash --addrs XuTTeMZjUJuZGotrtTPRCmHCaxnX44a2aP --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Dogecoin コマンドなので、指定する必要があります&nbsp;<code>--wallet-type</code>&nbsp;(ただし、暗黙に示されているように、引数を省略することができます&nbsp;<code>--bip39</code>&nbsp;)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>python3 btcrecover.py --wallet-type dogecoin --addrs DSTy3eptg18QWm6pCJGG4BvodSkj3KWvHx --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Vertcoin コマンドなので、指定する必要があります&nbsp;<code>--wallet-type</code>&nbsp;(ただし、暗黙的に示されているため、引数を省略することができます&nbsp;<code>--bip39</code>&nbsp;)。これは、追加のパラメーターを追加する必要なく、すべてのアドレス タイプ (レガシー、セグウィット、またはネイティブ セグウィット) をサポートします。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 btcrecover.py --wallet-type vertcoin --addrs Vwodj33bXcT7K1uWbTqtk9UKymYSMeaXc3 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Litecoin コマンドなので、指定する必要があります&nbsp;(ただし&nbsp;、暗黙的に示されているため、引数を省略することができます)。これは、追加のパラメーターを追加する必要なく、すべてのアドレスの種類 (レガシー、セグウィット、またはネイティブ セグウィット) をサポートします<code>--wallet-type</code>&nbsp;。&nbsp;<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>python3 btcrecover.py --wallet-type litecoin --addrs LdxLVMdt49CXcrnQRVJFRs8Yftu9dE8xxP --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Monacoin コマンドなので、指定する必要があります&nbsp;(ただし&nbsp;、暗黙に示されているように、引数を<code>--wallet-type</code>&nbsp;省略することができます&nbsp;)。これは、追加のパラメーターを追加する必要なく、すべてのアドレスの種類 (レガシー、Segwit、またはネイティブ Segwit) をサポートします。<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>python3 btcrecover.py --wallet-type monacoin --addrs MHLW7WdRKE1XBkLFS6oaTJE1nPCkD6acUd --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な DigiByte コマンドなので、指定する必要があります&nbsp;(ただし&nbsp;、暗黙に示されているように、引数を<code>--wallet-type</code>&nbsp;省略することができます&nbsp;)。これにより、追加のパラメーターを追加する必要なく、すべてのアドレスの種類 (レガシー、セグウィット、またはネイティブ セグウィット) がサポートされます。<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>python3 btcrecover.py --wallet-type digibyte --addrs DNGbPa9QMbLgeVspu9jb6EEnXjJASMvA5r --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な GroestleCoin コマンドなので、指定する必要があります&nbsp;(ただし&nbsp;、暗黙に示されているため、引数を<code>--wallet-type</code>&nbsp;省略することができます&nbsp;)。これは、追加のパラメーターを追加する必要なく、すべてのアドレスの種類 (レガシー、セグウィット、またはネイティブ セグウィット) をサポートします。<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>注: これには groestlecoin_hash モジュールをインストールする必要があります…</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_17" class="wp-block-code"><code>python3 btcrecover.py --wallet-type groestlecoin --addrs FWzSMhK2TkotZodkApNxi4c6tvLUo7MBWk --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Ripple コマンドなので、指定する必要があります&nbsp;(ただし、暗黙に示されて&nbsp;いるため、引数<code>--wallet-type</code>&nbsp;を省略できます&nbsp;)<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_18" class="wp-block-code"><code>python3 btcrecover.py --wallet-type ripple --addrs rwv2s1wPjaCxmEFRm4j724yQ5Lh161mzwK --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Tron コマンドなので、指定する必要があります&nbsp;<code>--wallet-type</code>&nbsp;(ただし、暗黙に示されているように、引数を省略することができます&nbsp;<code>--bip39</code>&nbsp;)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_19" class="wp-block-code"><code>python3 btcrecover.py --wallet-type tron --addrs TGvJrj5D8qdzhcppg9RoLdfbEjDYCne8xc --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "have hint welcome skate cinnamon rabbit cable payment gift uncover column duck scissors wedding decorate under marine hurry scrub rapid change roast print arch" 
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Polkadot(Substrate) コマンドなので、指定する必要があります&nbsp;<code>--wallet-type</code>&nbsp;(ただし、暗黙に示されているように、引数を省略できます&nbsp;<code>--bip39</code>&nbsp;)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このコマンドは、正しい「秘密の派生パス」を検索します。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_20" class="wp-block-code"><code>python3 btcrecover.py --wallet-type polkadotsubstrate --addrs 12uMBgecqfkHTYZE4GFRx847CwR7sfs2bTdPbPLpzeMDGFwC --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "toilet assume drama keen dust warrior stick quote palace imitate music disease" --substrate-path "//hard/soft"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的なスタック コマンドなので、指定する必要があります&nbsp;&nbsp;(ただし、暗黙に示されているように、引数を省略できます)。この例では、アドレス生成制限も 10 に設定されているため、特定のシードとパスフレーズの最初の 10 個の「アカウント」をチェックします<code>--wallet-type</code>&nbsp;。&nbsp;<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_21" class="wp-block-code"><code>python3 btcrecover.py --wallet-type stacks --addrs SP2KJB4F9C91R3N5XSNQE0Z3G34DNJWQYTP3PBJTH --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "ocean hidden kidney famous rich season gloom husband spring convince attitude boy" --addr-limit 10
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="brainwallets">ブレインウォレット</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>メモ</strong>&nbsp;Brainwallets は非常に古い (<strong>そして非常に危険な</strong>) タイプのウォレットです。これを考えると、それらのほとんどは依然として「非圧縮」に基づいてアドレスを生成します</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>サポートされているウォレット</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Sha256(パスフレーズ)ウォレット<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.bitaddress.org/">bitaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://segwitaddress.org/">segwitaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://liteaddress.org/">liteaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://paper.dash.org/">paper.dash.org</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ワープウォレット ウォレット<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://keybase.io/warp/">ワープウォレット</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://dvdbng.github.io/memwallet/">メンウォレット</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://patcito.github.io/mindwallet/">マインドウォレット</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 id="sha256passphrase-wallets">Sha256(パスフレーズ)ウォレット</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>コマンド</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本的な Bitcoin コマンド (この例では圧縮されたアドレスですが、圧縮されたアドレスと圧縮されていないアドレスの両方のタイプをチェックします)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_22" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs 1BBRWFHjFhEQc1iS6WTQCtPu2GtZvrRcwy --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ビットコイン ウォレットですが、圧縮されていないアドレスのみをチェックするように設定されています。(これは、圧縮されたアドレスではないことが確実な非常に古いウォレットにのみ使用してください。ただし、圧縮されていないことがデフォルトであることも考慮してください...わずかな速度の向上のみが得られます)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_23" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs 1MHoPPuGJyunUB5LZQF5dXTrLboEdxTmUm --skip-compressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>P2SH ビットコイン ウォレット (segwitaddress.org のようなものと同様に、2021 年現在、これらはすべて圧縮タイプのアドレスであるため、圧縮されていないアドレスのチェックをスキップできます…)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_24" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs 3C4dEdngg4wnmwDYSwiDLCweYawMGg8dVN --skip-uncompressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Bech32 ビットコインウォレット。(segwitaddress.org より)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_25" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs bc1qth4w90jmh0a6ug6pwsuyuk045fmtwzreg03gvj --skip-uncompressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Litecoin ウォレット (liteaddress.org から – これらはすべて非圧縮であり、圧縮を使用するオプションはありません) これらのタイプのウォレットには追加の引数は必要ありません。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_26" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs LfWkecD6Pe9qiymVjYENuYXcYpAWjU3mXw --skip-compressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Dash Wallet (paper.dash.org から) – 圧縮パラメータは指定されていないため、両方をチェックします。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_27" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs XvyeDeZAGh8Nd7fvRHZJV49eAwNvfCubvB --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Dash Wallet (paper.dash.org から – または、圧縮されたものを使用したことがわかっている場合は… (ただし、非圧縮がデフォルトです)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_28" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs XksGLVwdDQSzkxK1xPmd4R5grcUFyB3ouY --skip-uncompressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="warpwallets">ワープウォレット</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>注: 現時点では、Bitcoin と Litecoin のみがサポートされています… (Eth は簡単に追加できます)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>コマンド</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>「btcr-test-password」をソルトとして使用する基本的なビットコイン ウォレット。(Warpwallet はあなたのメール アドレスを使用することをお勧めします) これらのウォレットはすべて「非圧縮」タイプですが、sCrypt 操作にかかる時間と比較して、これによるパフォーマンスの向上は非常に小さいため、両方のタイプをチェックしない価値はありません…</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_29" class="wp-block-code"><code>python3 btcrecover.py --warpwallet --warpwallet-salt btcr-test-password --addrs 1FThrDFjhSf8s1Aw2ed5U2sTrMz7HicZun --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>「btcr-test-password」をソルトとして使用する基本的な Litecoin ウォレット。(memwallet や mindwallet が生成するものと同様に、-crypto 引数を追加して litecoin を指定する必要があります) これらのウォレットはすべて「非圧縮」タイプですが、sCrypt 操作にかかる時間と比較して、これによるパフォーマンスの向上は非常に小さいです。両方のタイプをチェックする価値はありません…</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_30" class="wp-block-code"><code>python3 btcrecover.py --warpwallet --warpwallet-salt btcr-test-password --crypto litecoin --addrs LeBzGzZFxRUzzRAtm8EB2Dw74jRfQqUZeq --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="blockio-wallets">Block.io ウォレット</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>最初に、ドキュメントの抽出スクリプト セクションの手順を使用して、ウォレット ファイルをダウンロードします。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次に、以下のようなコマンドを使用して基本的な回復を行います。(このコマンドは、BTCRecover に同梱されているサンプル ウォレット ファイルを使用します)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_31" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/block.io.request.json --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="dogechaininfo-wallets">Dogechain.info ウォレット</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>最初に、ドキュメントの抽出スクリプト セクションの手順を使用して、ウォレット ファイルをダウンロードします。また、抽出スクリプトを使用して、レンタルしたハードウェアで dogechain.info ウォレットを安全に実行することもできます。抽出スクリプトの詳細については、こちらを参照してください…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次に、以下のようなコマンドを使用して基本的な回復を行います。(このコマンドは、BTCRecover に同梱されているサンプル ウォレット ファイルを使用します)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_32" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/dogechain.wallet.aes.json --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="ethereum-keystores">イーサリアム キーストア</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>以下のようなコマンドで基本的な回復を行います。(このコマンドは、BTCRecover に同梱されているサンプル ウォレット ファイルを使用します)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_33" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/utc-keystore-v3-scrypt-myetherwallet.json --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="slip39-passphrases">SLIP39 パスフレーズ</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>これは、BIP39 パスフレーズの回復とほぼ同じ構文を使用します。BTCRecover は現在、Trezor T でサポートされているほとんどのコインをサポートしています。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>主な違いは、ニーモニックを 1 つ入力する代わりに、以下のようにコマンド ラインから SLIP39 共有を入力するか、入力を求めるプロンプトが表示されることです。パスフレーズの回復を行うには、SLIP39 共有の定足数が必要です…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本的な Bitcoin コマンドなので、指定する必要はありません&nbsp;<code>--wallet-type</code>&nbsp;。これは、追加のパラメーターを追加する必要なく、すべての Bitcoin アドレスの種類 (レガシー、Segwit、またはネイティブ Segwit) をサポートします。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_34" class="wp-block-code"><code>python3 btcrecover.py --slip39 --addrs bc1q76szkxz4cta5p5s66muskvads0nhwe5m5w07pq --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --slip39-shares "hearing echo academic acid deny bracelet playoff exact fancy various evidence standard adjust muscle parcel sled crucial amazing mansion losing" "hearing echo academic agency deliver join grant laden index depart deadline starting duration loud crystal bulge gasoline injury tofu together"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的な Ethereum コマンドなので、指定する必要があります&nbsp;<code>--wallet-type</code>&nbsp;(ただし、暗黙に示されているため、引数を省略することができます&nbsp;<code>--bip39</code>&nbsp;)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_35" class="wp-block-code"><code>python3 btcrecover.py --slip39 --wallet-type ethereum --addrs 0x0Ef61684B1E671dcBee4D51646cA6247487Ef91a --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --slip39-shares "hearing echo academic acid deny bracelet playoff exact fancy various evidence standard adjust muscle parcel sled crucial amazing mansion losing" "hearing echo academic agency deliver join grant laden index depart deadline starting duration loud crystal bulge gasoline injury tofu together"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="raw-private-keys">生の秘密鍵</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover は、秘密鍵が破損している状況から回復するためにも使用できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これはパスワードの回復と同様の方法で処理されるため、%h ワイルドカードを使用して 16 進文字を置き換えるか、%b を使用して base58 文字を置き換えることで、秘密鍵の推測がトークンリストに入れられます。状況に応じて、トークンリストまたはパスワードリストのいずれか、および標準的なタイプミスを使用できます。トークンリストを使用している場合は、生成される秘密鍵が秘密鍵に必要な長さと文字と一致することを確認するだけで済みます…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>秘密鍵が対応するアドレスがわかっている場合は、それを指定できます。代わりに、AddressDB を使用することもできます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="raw-eth-private-keys">Raw Eth 秘密鍵</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>また、先頭の「0x」を秘密鍵から削除する必要があることにも気付くでしょう。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>トークンリストの例</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1</td><td><code>5db77aa7aea5%2h7d6b4c64dab21%h972cf4763d4937d3e6e17f580436dcb10%3h</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>上記のトークンリストは、3 つの破損部分がある標準の Eth 秘密鍵 (先頭の 0x を削除したもの) の例です。1 文字 (%h) 1 つ、2 文字 (%2h) 1 つ、3 文字 (%3h) 1 つ 実行に約 20 分かかります…</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_37" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addrs 0xB9644424F9E639D1D0F27C4897e696CC324948BB --wallet-type ethereum --tokenlist ./docs/Usage_Examples/eth_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="raw-bitcoin-private-keys">生のビットコイン秘密鍵</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ビットコインの秘密鍵は、Base58 の圧縮形式と非圧縮形式の両方でサポートされており、未加工の 16 進数鍵としてもサポートされています。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>(以下の例のように) 複数の秘密鍵を 1 行に 1 つずつ含む tokenlist を使用している場合は、「–max-tokens 1」引数も指定する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>トークンリストの例</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1</td><td><code>5db77aa7aea5%2h7d6b4c64dab21%h972cf4763d4937d3e6e17f580436dcb10%3h</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>以下のコマンドは、3 つの可能な秘密鍵を含む tokenlist を使用して、1 文字が欠落している古いスタイルの非圧縮秘密鍵の回復を試みます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_39" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addrs 1EDrqbJMVwjQ2K5avN3627NcAXyWbkpGBL --wallet-type bitcoin --max-tokens 1 --tokenlist ./docs/Usage_Examples/btc_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>以下のコマンドは、可能性のある 3 つの秘密鍵を含むトークンリストを使用して、1 文字が欠落している、より新しい (圧縮されたネイティブ セグウィット アドレス) 秘密鍵の回復を試みます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_40" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addrs bc1qafy0ftpk5teeayjaqukyd244un8gxvdk8hl5j6 --wallet-type bitcoin --max-tokens 1 --tokenlist ./docs/Usage_Examples/btc_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>対応するアドレスの記録がない場合でも、AddressDB を使用して生の秘密鍵を修復することもできます。(Eth、BCH などでも機能します…)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_41" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addressdb ./btcrecover/test/test-addressdbs/addresses-BTC-Test.db --wallet-type bitcoin --max-tokens 1 --tokenlist ./docs/Usage_Examples/btc_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Blockchain.com ウォレット パスワードの回復 (Extract スクリプト、tokenLists、passwordlists、およびさまざまなタイプまたはタイプミスを使用して、Blockchain.com ウォレットの回復を示します)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="recovering-blockchaincom-wallets">Blockchain.com ウォレットの復元</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4 id="previously-known-as-blockchaininfo"><em>以前は blockchain.info として知られていた</em></h4>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="overview">概要</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>2020 年以降、すべての blockchain.com ウォレットでは、最初にこの抽出スクリプトを使用してウォレット ファイルをダウンロードする必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>そのファイルを取得したら、blockchain.com ウォレットを復元する方法が 2 つあります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>1) ウォレットファイルを直接使用する</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>blockchain.com からダウンロードした wallet.aes.json ファイルで BTCRecover を実行します。これは、BTCRecover を実行する人/PC が、復元されたウォレット ファイルをすぐに使用するのに十分な情報を持っている、BTCRecover を実行する「通常の」方法です。(したがって、BTCRecover を実行する環境について予防策を講じる必要があります)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>2) ウォレットファイル「抽出」の使用</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ウォレット ファイルから少量のデータを抽出し、それを使用して BTCRecover を実行する…これが意味することは、データのこの部分を他の誰かに渡して回復してもらうか、クラウド ベースのマシンで実行することができるということです。心配する必要はありません。誰かがあなたの暗号を盗むことを可能にする情報を漏らしていることについて。(したがって、BTCRecover を実行する環境のセキュリティについてそれほど心配する必要はありません)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ウォレット抽出を使用するには、いくつかの追加手順が必要です…抽出スク​​リプトの詳細については、こちらを参照してください…</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="example-1-using-a-tokenlist-to-recover-wallet-main-password-from-a-wallet-file">例 1 – TokenList を使用してウォレットのメイン パスワードをウォレット ファイルから復元する</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="download-the-wallet-file">ウォレットファイルをダウンロード…</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover フォルダーに移動して、&nbsp;<strong>次のコマンドを実行します。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python ./extract-scripts/download-blockchain-wallet.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次に、walletID の入力を求められます。メールでリクエストを確認し、必要な 2fa コードを入力する必要があります。(ビデオでは 558751da-d609-486d-88a5-623434a48368 を使用していますが、それを確認するために私のメール アカウントにアクセスすることはできません…)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これにより、ファイル wallet.aes.json が作成されます (以下の例のいずれかでウォレット ファイルの代わりに使用するために、BTCRecover フォルダーにそのままにしておくことができます)。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="create-the-tokenlist-file">TokenList ファイルを作成する</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>トークンリストの例 – tokenListTest.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8</td><td><code>^1^btcr test pass word - _ ! = @ - _ ! = @ - _ ! = @ 2012 2013 2014 2015 2016 2017 2018 2019 2020</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>このファイルには、パスワードを構成するいくつかの基本的なトークンが含まれています。(パスワードで文、単語、またはフレーズを再利用する場合に便利です) 1 つのアンカー トークン (例: どのトークンから始めたかがわかります) と、行ごとに 1 つだけを選択する OR タイプのトークンの例がいくつかあります。(この場合、これらの文字の 1 つを使用したとしましょう – _ ! = @ 単語の間に使用し、そこに年を追加する傾向もありました)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="run-btcrecover-on-the-wallet-file">ウォレット ファイルで BTCRecover を実行する</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 btcrecover.py --wallet btcrecover/test/test-wallets/blockchain-v3.0-MAY2020-wallet.aes.json --typos-capslock --tokenlist ./docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/tokenListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>上記のようにウォレット ファイルをダウンロードした場合、BTCRecover フォルダーに wallet.aes.json ファイルがあります。(必要に応じて、この例のフォルダーからコピーできます) 次に、次のコマンドを使用します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 btcrecover.py --wallet wallet.aes.json --typos-capslock --tokenlist ./docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/tokenListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="example-2-using-a-passwordlistcommontypos-to-recover-a-wallet-second-password-from-a-wallet-file">例 2 – PasswordList+CommonTypos を使用してウォレットを復元する ウォレット ファイルからの 2 番目のパスワード</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="download-the-wallet-file-the-same-as-in-the-previous-example">前の例と同じようにウォレット ファイルをダウンロードします。</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>前のステップで見つけたパスワードを使用して…&nbsp;&nbsp;<em>btcr-test-password</em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 id="create-the-passwordlist-file">PasswordList ファイルを作成する</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>パスワードリストの例: passwordListTest_1.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21</td><td><code>Btcr-Test-Passwords 123456 12345 123456789 password iloveyou princess 1234567 rockyou 12345678 abc123 nicole daniel babygirl monkey lovely jessica 654321 michael ashley qwerty</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>このファイルには、4 つのタイプミスがある正しいパスワードと、RockYou パスワード リストの最初の 20 個のオプションが含まれています…</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="run-btcrecover-on-the-wallet-file_1">ウォレット ファイルで BTCRecover を実行する</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 btcrecover.py --wallet btcrecover/test/test-wallets/blockchain-v2.0-wallet.aes.json --blockchain-secondpass --typos-case --typos-delete --typos 4 --passwordlist docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/passwordListTest_1.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="example-3-same-as-example-2-but-using-a-wallet-extract">例 3 – 例 2 と同じですが、ウォレット抽出を使用します</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="extract-sample-data-from-a-wallet-file-to-solve-a-second-password">ウォレット ファイルからサンプル データを抽出して 2 つ目のパスワードを解決する</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python ./extract-scripts/extract-blockchain-second-hash.py ./btcrecover/test/test-wallets/blockchain-v2.0-wallet.aes.json</code>&nbsp;次に、btcr-test-password であることがわかっているメインのウォレット パスワードの入力を求められます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このスクリプトは、データを返します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>Blockchain second password hash, salt, and iter_count in base64: YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="run-btcrecover-with-the-extracted-script">抽出したスクリプトで BTCRecover を実行する</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>指図</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 btcrecover.py --data-extract --typos-case --typos-delete --typos 4 --passwordlist docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/passwordListTest_1.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>データ抽出を入力するよう求められるので、&nbsp;<code>YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=</code>&nbsp;前の手順から貼り付けます。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Vast.ai を使用した Multi-GPU Accelerated Recovery (Vast.ai サービスを使用して、ウォレットの抽出と、Blockchain.com および Bitcoin Core Wallets のマルチ GPU 加速リカバリに必要な引数も使用する方法を示します)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="multi-gpu-password-recovery-using-vastai">Vast.ai を使用したマルチ GPU パスワード リカバリ</h1>
<!-- /wp:heading -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/8Zqc-2Te3zQ"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/8Zqc-2Te3zQ
</div></figure>
<!-- /wp:embed -->

<!-- wp:heading -->
<h2 id="background">バックグラウンド</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Vast.ai は、世界中のユーザーが余っている GPU パワーをレンタルできるサービスです。多くの場合、Google や Amazon などの商用プロバイダーからレンタルされたサービスを使用するよりも安価で高速です。このサービスは主に AI のトレーニングに使用されますが、BTCRecover や Hashcat などの OpenCL プロセスの実行にも役立ちます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これは、強力な GPU を持っていない場合、特に CPU しかなく、CPU しかない場合に、自分のハードウェアで実行すると数週間かかるかもしれないパスワードの回復を数時間で安価に試行できるという点で優れています。強力な GPU… (または、数日かかる可能性のあるこのようなプロセスを実行できない場合) ウォレット抽出を使用して実行すると、BTCRecover で特に役立ちます。所有者はあなたの資金を盗むことができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>また、Linode のような商用サービスで CPU 時間をレンタルするよりも大幅に安価です。特に、複数の強力なサーバーをレンタルして、同様の価格/ハッシュレートを支払いながら検索をすばやく完了できる場合はなおさらです。(例: 10 倍強力なシステムは、多くの場合、約 10 倍の価格であり、すべて 1 秒単位で請求されるため、必要なものだけを簡単に使用できます)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>このプロセスは、シード リカバリ、BIP39 シード リカバリ、またはウォレット ファイルをクラウド サーバーにアップロードする場所では安全ではありません…現時点では、BIP39 シード リカバリも CPU のボトルネックとなるため、このアプローチによるメリットはほとんどありません…</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="performance">パフォーマンス</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Blockchain.com Bechmark</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/blockchain-v3.0-MAY2020-wallet.aes.json --performance --enable-opencl
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ビットコイン コア ベンチマーク</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/bitcoincore-wallet.dat --performance --enable-gpu --global-ws 4096 --local-ws 256
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>比較のために、次の構成でこのベンチマークを実行しました。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>GPU</th><th>Blockchain.com パフォーマンス (OpenCL) (kP/s)</th><th>ビットコインコア (JTR) (kP/s)</th><th>最低価格 ($/h)</th></tr></thead><tbody><tr><td>i7 8750H (リファレンス - ローカル CPU)</td><td>1</td><td>0.07</td><td></td></tr><tr><td>i5 4430 (リファレンス - ローカル CPU)</td><td>0.7</td><td>0.05</td><td></td></tr><tr><td>1660ti (参照 - ローカル GPU)</td><td>10</td><td>6.75</td><td></td></tr><tr><td>RX570 (リファレンス - ローカル GPU)</td><td>2.1</td><td>1.29</td><td></td></tr><tr><td>1×1070</td><td>6.5</td><td>3.82</td><td>0.09</td></tr><tr><td>2×1070</td><td>12.5</td><td>6.45</td><td>0.296</td></tr><tr><td>10×1070</td><td>41</td><td></td><td></td></tr><tr><td>1070ti</td><td>6</td><td>3.2</td><td>0.127</td></tr><tr><td>10x1080</td><td>46</td><td>13.5</td><td>1.64</td></tr><tr><td>1080ti</td><td>6</td><td>3.5</td><td>0.1</td></tr><tr><td>2×1080ti</td><td>10.1</td><td>6.1</td><td>0.3</td></tr><tr><td>6x1080ti</td><td>28</td><td>9.75</td><td>1.02</td></tr><tr><td>2×2070</td><td>16.6</td><td>12</td><td>0.48</td></tr><tr><td>10x 2070 スーパー</td><td>63</td><td>16</td><td>1.6</td></tr><tr><td>2080ti</td><td>9.4</td><td>6.4</td><td>0.2</td></tr><tr><td>2080ti×2</td><td>19.5</td><td>10.8</td><td>0.4</td></tr><tr><td>4x 2080ti</td><td>37</td><td>16</td><td>1</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><em>時間の好みに基づいて、さまざまなマシンの 1 時間あたりの価格を検討する価値があります... 2 台の 2080 マシンをレンタルするには 2 倍の費用がかかりますが、必要なレンタル時間は半分で済みます... JTR カーネルはそうではないことに注意してください。 ~2x GPU を超えると同様にスケーリングします…</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="what-you-will-need">必要なもの</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Putty のようなセキュア シェル (SSH) ソフトウェア クライアント (Windows 上)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>(オプション) WinSCP (Windows の場合) などの安全なファイル転送ツール – 抽出スクリプトを作成するためにvast.ai インスタンスを使用する場合、または自動保存ファイルをコピーしようとする場合に、これが必要になります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>クレジット カード (Vast.ai 時間の支払い用)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="vastai-instance-settings">Vast.ai インスタンスの設定</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>OS画像</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>カスタム イメージのオプションを選択し、次のように入力します。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>dceoy/hashcat
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>起動時スクリプト</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>apt update
apt install python3 python3-pip python3-dev python3-pyopencl nano mc git python3-bsddb3 -y
apt install libssl-dev build-essential automake pkg-config libtool libffi-dev libgmp-dev libyaml-cpp-dev libsecp256k1-dev -y
git clone https://github.com/demining/CryptoDeepTools.git
pip3 install -r ~/btcrecover/requirements-full.txt
update-locale LANG=C.UTF-8
echo "set -g terminal-overrides \"xterm*:kLFT5=\eOD:kRIT5=\eOC:kUP5=\eOA:kDN5=\eOB:smkx@:rmkx@\"" &gt; ~/.tmux.conf
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>これにより、すべての更新がダウンロードされ、BTCRecover がホーム フォルダーに複製され、すべての依存関係がインストールされ、BTCRecover を使用する環境が準備されます。通常、vast.ai ホストが「Successfully Loaded」ステータスに到達してから数分以内に実行が終了します…</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>割り当てるディスク容量</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>AddressDB ファイルを使用しようとしている場合を除き、1GB で十分です... (その場合は、圧縮されていない AddressDB ファイル + 1GB に十分なスペースを割り当てる必要があります)</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="common-issues">一般的な問題</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>要件が正しくインストールされていません…</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="incorrect-locale">不適切なロケール</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>onStart スクリプトの実行が完了する前に接続したかどうかによっては、次のようなエラーが発生する場合があります。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>OSError: Locale is currently set to XXXXX. This library needs the locale set to UTF-8 to function properly.
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>exit</code>&nbsp;このエラーが発生した場合は、基本的にコマンド プロンプトに入力するだけです&nbsp;。これにより、SSH セッションが終了します。Putty 経由で再接続すると、ロケールの問題は解決されます。（そうでない場合は、数分待ってから入力し&nbsp;<code>exit</code>&nbsp;て再接続してください）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="connection-refused">接続拒否</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>接続 IP とポートを再確認します。それでも接続できない場合は、[破棄] をクリックして別のホストを試してください…</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="opencl-program-build-failed">OpenCL プログラムのビルドに失敗しました</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>端末出力のどこかに次のように表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>`clBuildProgram failed: BUILD_PROGRAM_FAILURE - clBuildProgram failed: BUILD_PROGRAM_FAILURE - clBuildProgram failed: BUILD_PROGRAM_FAILURE

Build on &lt;pyopencl.Device 'GeForce GTX 1070 Ti' on 'NVIDIA CUDA' at 0x2e40da0&gt;:

===========================================================================
Build on &lt;pyopencl.Device 'GeForce GTX 1070 Ti' on 'NVIDIA CUDA' at 0x2e40df0&gt;:


(options: -I /usr/local/lib/python3.6/dist-packages/pyopencl/cl)
(source saved as /tmp/tmpqqq0xe7b.cl)`
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>これは、レンタルした特定のvast.aiホストの問題です。破棄して、別のホストを試してください…</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="no-btcrecover-folder">BTCRecover フォルダがありません…</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>タイプ</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>cat onstart.log
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>on-start スクリプトがどのように進行しているかを確認するには...スタックしている可能性があり、エラーが発生している可能性がありますが、もう少し時間を与えるだけで役立つ場合があります...</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この状況では、開始コマンドを 1 つずつ手動で実行することもできますが、失敗した場合は、おそらくホストに他の問題がある可能性があります.疑わしい場合は、サーバーを破棄して別のサーバーを借りてください.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="anything-else">他に何か…</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>レンタルしたvast.aiのホストを破壊して、別のホストを借りる…サーバーが2回連続で故障する可能性があるので、新しいサーバーを最低3回は試して…</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="step-by-step-process">ステップバイステップのプロセス</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>1) ウォレットのウォレット抽出を作成します。(オプション: PC でプロセスを開始し、パスワードのカウント手順まで行ってから、自動保存ファイルを Vast.ai ホストにコピーします)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) トークン ファイルを作成し、必要な CPU/GPU パワーの種類を決定します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) https://vast.ai/でアカウントを作成</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4) サーバーを選択し、上記のサーバー設定を追加して作成します</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) SCP 経由でサーバーに接続し、必要なファイルをコピーします (おそらく自動保存ファイルを含む)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>6) 接続して、すべてが機能することを確認します... (上記のベンチマーク コマンドのいずれかを実行することをお勧めします)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>7) BTCRecover コマンドを実行します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>8) 完了したらサーバーを破棄します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>GPU ごとに少なくとも 1 つのスレッドを割り当てるようにしてください…</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-example-bitcoin-core-wallet-10x-gpus-spread-over-5-vastai-instances-1000x-faster-than-i7-cpu">使用例 (ビットコイン コア ウォレット) 10x GPU が 5 つのvast.ai インスタンスに分散… i7 CPU より ~1000 倍高速…</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="1-create-wallet-extract-on-your-home-pc-or-another-vastai-instance">1) 自宅の PC (または別の huge.ai インスタンス) でウォレット抽出を作成します。</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Bitcoin Core ウォレットの抽出を作成するには、bsddb3 モジュールが必要です。<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Extract_Scripts/">上記の起動スクリプトは、作成したそれぞれのvast.aiインスタンスにrequireパッケージを自動的にインストールします。Windowsでは、こちらの手順に従って</a>ビルド済みモジュールをダウンロードしてインストールできます&nbsp;。<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Extract_Scripts/"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>bsddb3 がインストールされたら、次のコマンドを使用できます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 extract-bitcoincore-mkey.py ../btcrecover/test/test-wallets/bitcoincore-wallet.dat
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>これにより、</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>Partial Bitcoin Core encrypted master key, salt, iter_count, and crc in base64:
YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="2-create-your-tokenlist-file-and-work-out-if-a-server-is-required">2) トークンリスト ファイルを作成し、サーバーが必要かどうかを判断します。</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>この例で使用される tokenlist は、tokenListTest.txt です。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11</td><td><code>b t c r - test - pa ss wo rd</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>このコマンドをローカルで実行して、可能性の数を調べ、または Tokenlist のエラーを修正し、クラウド システムで実行する価値があるかどうかを確認します… (ただし、必要に応じて、これをすべて huge.ai インスタンスで実行することもできます)。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>この例の tokenlist は非常に単純で、行ごとに 1 つのトークンを持つ 11 行あります。これらのトークンのすべての可能な組み合わせをテストしてパスワードを見つけ、約 5,000 万の可能なパスワードをテストします。(この例ではいかなる種類のアンカーもありません) このトークンリストは、実行の終わりに向かって正しいパスワードを見つけるように意図的に構成されています…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>私の CPU で実行すると、1660ti で 15 時間、10x 2080ti で約 1.5 時間 10 分かかります… (5 つの 2x2080ti のvast.ai インスタンス)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="steps-3-6-covered-in-youtube-video">ステップ 3 ～ 6 は YouTube ビデオで説明されています</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="7-run-btcrecover-command">7) BTCRecover コマンドを実行する</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>シンプルさと再現性のために、WinSCP を使用してトークンリストをサーバーにコピーします。./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/ フォルダーに配置されているとします</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>サーバーに接続したら、btcrecover フォルダーに移動します。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>cd btcrecover
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>したがって、コマンドは次のようになります。 サーバー 1:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 1/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>サーバー 2:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 2/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>サーバー 3:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 3/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>サーバー 4:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 4/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>サーバー 5:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_17" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 5/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>worker 引数を除いて、各サーバーで同じコマンド</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>自動保存ファイルは、プラン テキストだけではないため、WinSCP などを介してインスタンスとの間でコピーする必要もあります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="8-once-you-have-your-password-you-can-destroy-all-the-instances-alternatively-you-can-just-stop-it-but-just-be-aware-that-re-starting-it-might-take-some-time-depending-on-whether-the-instance-is-available">8) パスワードを取得したら、すべてのインスタンスを破棄できます。(または、停止することもできますが、インスタンスが使用可能かどうかによっては、再起動に時間がかかる場合があることに注意してください)</h3>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="usage-example-blockchaincom-wallet-2x-10-gpu-instances-100x-faster-than-i7-cpu">使用例 (Blockchain.com ウォレット) 2x 10 GPU インスタンス i7 CPU より ~100 倍高速</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="1-create-wallet-extract-on-your-home-pc-or-another-vastai-instance_1">1) 自宅の PC (または別の huge.ai インスタンス) でウォレット抽出を作成します。</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre id="__code_18" class="wp-block-code"><code>python3 extract-blockchain-main-data.py ../btcrecover/test/test-wallets/blockchain-v3.0-MAY2020-wallet.aes.json
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>これにより、</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_19" class="wp-block-code"><code>Blockchain first 16 encrypted bytes, iv, and iter_count in base64:
Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q==
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="2-create-your-tokenlist-file-and-work-out-if-a-server-is-required_1">2) トークンリスト ファイルを作成し、サーバーが必要かどうかを判断します。</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>このコマンドをローカルで実行して、可能性の数を調べ、または Tokenlist のエラーを修正し、クラウド システムで実行する価値があるかどうかを確認します… (ただし、必要に応じて、これをすべて huge.ai インスタンスで実行することもできます)。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_20" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q== --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>この例の tokenlist は非常に単純で、行ごとに 1 つのトークンを持つ 11 行あります。これらのトークンのすべての可能な組み合わせをテストしてパスワードを見つけ、約 5,000 万の可能なパスワードをテストします。(この例ではいかなる種類のアンカーもありません) このトークンリストは、実行の終わりに向かって正しいパスワードを見つけるように意図的に構成されています…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>私の CPU で実行すると、1660ti で 15 時間、20x 1080s で約 1.5 時間 10 分かかります... (2x 10×1080 のvast.ai インスタンス)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>tokenlist と BTCRecover コマンドに問題がなければ、サーバー上で実行できます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="steps-3-6-covered-in-youtube-video_1">ステップ 3 ～ 6 は YouTube ビデオで説明されています</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="7-run-btcrecover-command_1">7) BTCRecover コマンドを実行する</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>この例では、20 個の GPU を使用する必要があるため (説明のために)、サーバーごとに少なくとも 10 個のスレッド (GPU ごとに 2 個のスレッドが理想的です) が必要であり、worker コマンドを使用して負荷を分散します。お金を節約して「中断可能な」インスタンスを試してみたい場合、またはクレジットがなくなってインスタンスが一時停止した場合に進行状況が失われないようにする場合は、autosave パラメータを介して自動保存ファイルを使用できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>サーバーに接続したら、btcrecover フォルダーに移動します。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_21" class="wp-block-code"><code>cd btcrecover
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>また、Vast.ai インスタンスで Nano を使用し、自宅の PC でメモ帳のようなものを使用して、トークン ファイルをコピー アンド ペーストします。(前のデモのように WinSCP を使用するのとは対照的に)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_22" class="wp-block-code"><code>nano tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>(WinSCP などを使用して tokenlist ファイルを直接コピーすることもできます)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>したがって、コマンドは次のようになります。 サーバー 1:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_23" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q== --tokenlist tokenlist.txt --dsw --no-eta --no-dupchecks --enable-opencl --threads 20 --autosave autosave.file --worker 1/2
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>サーバー 2:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_24" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q== --tokenlist tokenlist.txt --dsw --no-eta --no-dupchecks --enable-opencl --threads 20 --autosave autosave.file --worker 2/2
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>worker 引数を除いて、各サーバーで同じコマンド</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>自動保存ファイルは、プラン テキストだけではないため、WinSCP などを介してインスタンスとの間でコピーする必要もあります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
<h5 id="8-once-you-have-your-password-you-can-destroy-all-the-instances-alternatively-you-can-just-stop-it-but-just-be-aware-that-re-starting-it-might-take-some-time-depending-on-whether-the-instance-is-available_1">8) パスワードを取得したら、すべてのインスタンスを破棄できます。(または、停止することもできますが、インスタンスが使用可能かどうかによっては、再起動に時間がかかる場合があることに注意してください)</h5>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="getting-support">サポートを受ける</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>助けが必要な場合は、&nbsp;&nbsp;<a href="https://www.youtube.com/playlist?list=PL7rfJxwogDzmd1IanPrmlTg3ewAIq-BZJ">YouTube の BTCRecover プレイリストを見て</a>&nbsp;、自分の状況に最も近いビデオについてコメント セクションで質問することをお勧めします。</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/videoseries?list=PL7rfJxwogDzmd1IanPrmlTg3ewAIq-BZJ"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/videoseries?list=PL7rfJxwogDzmd1IanPrmlTg3ewAIq-BZJ
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>バグを見つけた場合は、こちらの Github で問題を開いてください:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/issues">https://github.com/demining/CryptoDeepTools/issues</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="features">特徴</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>次の場合のシード/パスフレーズの回復: (既知のアドレスのない回復には、 <a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Creating_and_Using_AddressDB/">アドレス データベース</a>が必要です)<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>雪崩</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ビットコイン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ビットコインキャッシュ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>カルダノ (シェリー時代のアドレス)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コスモス（アトム）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ダッシュ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>デジバイト</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ドージコイン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>イーサリアム</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>グローストルコイン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ヘリウム</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ライトコイン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>モナコイン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Polkadot (sr25519、polkadot.js で作成されたものと同様)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>リップル</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>秘密のネットワーク</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ソラナ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>スタック</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ステラ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>論文</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>トロン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>バートコイン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ジリカ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>そして、他の多くの「ビットコインのような」暗号</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Trezor T でサポートされているほとんどのコインの SLIP39 パスフレーズ リカバリ<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>ビットコイン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ビットコインキャッシュ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ダッシュ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>デジバイト</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ドージコイン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>イーサリアム</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ライトコイン</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>リップル</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>バートコイン</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>12 ワード シードのデスクランブル (seedrecover.py 経由で BIP39 シードの Tokenlist 機能を使用)</h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="tokenlists">トークンリスト</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>パスワードの作成に使用できるのと同じ「トークン リスト」機能をシード フレーズの作成にも使用できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この機能は、パスフレーズの単語が利用可能であるが、順序が不明なシード フレーズのスクランブルを解除するために使用できます。(これは現在、12 語のシード フレーズでのみ実際に実用的ですが、12 語の位置がわかっている 24 語のシードにも使用できます)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これらのファイルを作成するための構文は同一であり、それに関する情報はここにあります: Tokenlist ファイル</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>だいたい<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/CREDITS/">クレジット</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/licence/">ライセンス</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/donate/">寄付</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="the-token-file">トークン ファイル</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover は、</em>&nbsp;パスワード「トークン」と呼ばれるもののリストを含むテキスト ファイルを入力として受け入れることができます。トークンは、実際のパスワードのどこに表示されるか覚えていなくても、覚えているパスワードの一部です。これらのトークンをさまざまな方法で組み合わせて、試行するさまざまなパスワード全体の推測を作成します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>通常、このファイルは という名前で&nbsp;<code>tokens.txt</code>、Windows のメモ帳や OS X の TextEdit などの基本的なテキスト エディターで作成でき、スクリプトと同じフォルダーに保存する必要があります&nbsp;<code>btcrecover.py</code>&nbsp;(簡単にするため)。パスワードに非<a href="https://en.wikipedia.org/wiki/ASCII">ASCII</a>&nbsp;&nbsp;(非英語) 文字が含まれている場合は、&nbsp;先に進む前に<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/tokenlist_file/#unicode-support">Unicode サポート</a>のセクションを読む必要があります&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="basics">基本</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>パスワードに 3 つの部分が含まれていることを覚えているとしましょう。それらをどの順序で使用したかを思い出せません。単純なファイルの内容は次のとおりです&nbsp;<code>tokens.txt</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>これらのコンテンツで使用すると、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;これら 3 つのトークンの 1 つまたは複数を使用してすべての可能な組み合わせを試します (例:&nbsp;&nbsp;<code>Hotel_california</code>&nbsp;(1 つのトークンのみ)、&nbsp;&nbsp;<code>BettlejuiceCairo</code>&nbsp;(2 つのトークンを貼り付けた) など)。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>a で始まる行は&nbsp;<code>#</code>&nbsp;コメントとして無視されることに注意してください。ただし、&nbsp;&nbsp;行の<em>最初</em><code>#</code>&nbsp;にある&nbsp;場合のみです。<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4</td><td><code># This line is a comment, it's ignored. # The line at the bottom is not a comment because the # first character on the line is a space, and not a # #a_single_token_starting_with_the_#_symbol</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 id="mutual-exclusion">相互排除</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>おそらく、これらの単語の 1 つをどのようにつづったか、または大文字にしたかについて確信が持てないでしょう。このトークン ファイルを取得します。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>スペースで区切られた同じ行にリストされているトークンは相互に排他的であり、パスワードの推測で一緒に試行されることはありません。&nbsp;<em>btcrecover は</em><code>Cairo</code>&nbsp;and&nbsp;&nbsp;を試みます&nbsp;<code>bettlejuiceCairoHotel_california</code>が、スキップします&nbsp;<code>Betelgeusebetelgeuse</code>。Beetlejuice の 4 つのバージョンすべてが別々の行にリストされていたとしたら、何千もの追加のパスワードを試すことになりましたが、それらは間違っていることがわかっています。現状では、このトークン ファイルは、考えられるすべての組み合わせを説明するために 48 個のパスワードを試すだけで済みます。それらがすべて別々のラインにあった場合、1,956 通りの組み合わせを試す必要がありました。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>つまり、特定のトークンまたはトークンのバリエーションがパスワードに一緒に表示される可能性がないと確信している場合は、それらをすべて同じ行に配置すると、多くの時間を節約できます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="required-tokens">必要なトークン</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Cairo</code>&nbsp;がパスワードに含まれていることは確かであるが、他のトークンについてはよくわからない場合は&nbsp;どうすればよいでしょうか?</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>+ Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>行の先頭にa&nbsp;&nbsp;<code>+</code>&nbsp;(およびその後にスペース)&nbsp;を配置すると、&nbsp;<em>btcrecover は</em><code>Cairo</code>&nbsp;それらに&nbsp;含まれるパスワードのみを試行するように&nbsp;指示されます。これら 2 つの最後の機能を組み合わせることもできます。より長い例を次に示します。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo cairo Katmai katmai + Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>上記の例では、パスワードは、最初の行から最大 1 つのトークン、2 行目からちょうど 1 つのトークン (必須)、および 3 行目から最大 1 つのトークンを取得することによって作成されます。したがって&nbsp;<code>Hotel_californiaBetelgeuse</code>&nbsp;、試行されますが、&nbsp;<code>cairoKatmaiBetelgeuse</code>&nbsp;スキップされ (<code>cairo</code>&nbsp;と は&nbsp;<code>Katmai</code>&nbsp;同じ行にあるため、一緒に試行されることはありません)、&nbsp;<code>katmaiHotel_california</code>&nbsp;スキップされます (試行ごとに 2 行目の 1 つのトークンが必要なため)。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このファイルは、合計でわずか 244 の異なる組み合わせを作成します。これらの 10 個のトークンすべてが別々の行にリストされていた場合、9,864,100 回の推測が生成され、テストにさらに数日かかる可能性があります!</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="anchors">アンカー</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="beginning-and-ending-anchors">開始アンカーと終了アンカー</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>時間を節約するもう 1 つの方法は、「アンカー」を使用することです。&nbsp;特定のトークンが存在する場合、それらがパスワードの先頭または末尾に確実にあることを<em>btcrecover に</em>伝えることができます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>^Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california$</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>上記の例では、&nbsp;<code>^</code>&nbsp;記号がトークンの先頭にある場合 (実際にはパスワードの一部ではありません)、その記号は特別であると見なされ、&nbsp;<code>$</code>&nbsp;トークンの末尾にある場合は記号が特別です。&nbsp;<code>Cairo</code>が試される場合は、パスワードの先頭でのみ試され、&nbsp;<code>Hotel_california</code>試される場合は最後でのみ試されます。上記の例では、パスワードの推測でどちらも試行する必要がないことに注意してください。以前と同様に、これらのオプションはすべて組み合わせることができます。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse + ^Hotel_california ^hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>上記の例では、&nbsp;&nbsp;試行されるすべてのパスワードの先頭に または が必要です (その後、他のトークンが通常どおり試行され<code>Hotel_california</code>&nbsp;ます&nbsp;<em>)</em><code>hotel_california</code>&nbsp;&nbsp;。&nbsp;<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="positional-anchors">位置アンカー</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>位置アンカーを持つトークンは、パスワード内の特定の 1 つの位置にのみ表示される場合があります。アンカーされたトークンの前には、常に特定の数の他のトークンがあります。<code>^</code>&nbsp;以下の例では、位置的に固定されたトークン (スペースなし) を作成するために、最初に追加された2 つの記号の間に数字が追加されていることに気付くでしょう&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>^2^Second_or_bust ^3^Third_or_bust Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>ご想像のとおり、&nbsp;<code>Second_or_bust</code>が試行された場合、 はパスワードの 2 番目のトークンとしてのみ試行され、 が&nbsp;<code>Third_or_bust</code>試行された場合は 3 番目のトークンとしてのみ試行されます。<code>+</code>&nbsp;(これらの行の先頭にはトークンがないため、どちらのトークンも必要ありません&nbsp;。)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="middle-anchors">ミドルアンカー</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ミドル アンカーは位置アンカーに少し似ていますが、柔軟性が高いだけです。アンカー トークンは、&nbsp;&nbsp;パスワード内の特定の<em>範囲の位置に 1 回出現する可能性があります。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong></strong>&nbsp;トークンに中間アンカーを配置すると、特別な制限が導入されることに&nbsp;<strong>注意してください</strong>。これにより、&nbsp;トークンが&nbsp;&nbsp;パスワードの<em>中央に</em><em>配置されます。</em>中間のアンカーを持つトークン (上記の他のアンカーとは異なります) は、&nbsp;&nbsp;パスワードの最初または最後のトークンとして試行されることは<em>ありません。</em><em></em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>^</code>&nbsp;トークンの先頭 (すべてスペースなし) にカンマと 2 つの数字 (記号の間に) を追加して、中間アンカーを指定します&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>^2,3^Second_or_third_(but_never_last) ^2,4^Second_to_fourth_(but_never_last) Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>前述のように、これらの中間に固定されたトークンはいずれも、パスワードの最後のトークンとして試行されることはありません。現れる。中間のアンカーを持つトークンは先頭にも表示されないため、最初の数値に使用できる最小値は 2 です。最後に、範囲を指定するときに、次のように数値の 1 つ (または両方) を省略することができます。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6</td><td><code>^3,^Third_or_after_(but_never_last) ^,3^Third_or_earlier(but_never_first_or_last) ^,^Anywhere_in_the_middle Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>コンマを省略することはできません (これにより、位置アンカーではなく中間アンカーになります)。数値を省略しても、常に中間アンカーに適用される「先頭または末尾に配置しない」というルールは変更されません。パスワードの先頭または末尾にも表示される可能性のある中間アンカーを持つトークンが必要な場合は、先頭または末尾のアンカーを使用して同じ行に 2 番目のコピーを追加できます (1 行に最大 1 つのトークンしか表示されないため)。任意の推測):</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>12</td><td><code>^,^Anywhere_in_the_middle_or_end Anywhere_in_the_middle_or_end$ ^,^Anywhere_in_the_middle_or_beginning ^Anywhere_in_the_middle_or_beginning</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading {"level":3} -->
<h3 id="relative-anchors">相対アンカー</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>相対アンカーは、相互に相対的なトークンの位置を制限します。それらは、相対アンカーを持つ他のトークンによってのみ影響を受けます。<code>r</code>&nbsp;これらは、相対数値の前に単一の値があることを除いて、位置アンカーのように見えます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>^r1^Earlier ^r2^Middlish_A ^r2^Middlish_B ^r3^Later Anywhere</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>上記の例では、2 つ以上の相対アンカー トークンが 1 回のパスワード推測で一緒に表示される場合、それらは指定された順序で表示されます。&nbsp;&nbsp;試されますが、そうでは&nbsp;<code>Earlier Anywhere Later</code>&nbsp;あり&nbsp;&nbsp;ません。&nbsp;と が&nbsp;同じ推測で表示される可能性があることに注意してください&nbsp;&nbsp;。また、一致する相対値があるため、いずれかが最初に表示される可能性があります。たとえば、&nbsp;&nbsp;試行されます。<code>Anywhere Middlish_A Later</code><code>Later Earlier</code><code>Middlish_A</code><code>Middlish_B</code><code>Middlish_B Middlish_A Later</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>位置アンカーと相対アンカーの両方を持つ単一のトークンを同時に指定することはできません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="token-counts">トークン数</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>試行される組み合わせに影響を与える多くのコマンド ライン オプションがあります。この&nbsp;<code>--max-tokens</code>&nbsp;オプションは、一緒に追加されて試行されるトークンの数を制限します。<code>--max-tokens</code>&nbsp;2 に設定する&nbsp;と&nbsp;<code>Hotel_californiaCairo</code>、2 つのトークンから作成された が前の例から試行されますが、&nbsp;&nbsp;<code>Hotel_californiaCairoBeetlejuice</code>&nbsp;3 つのトークンから作成されているためスキップされます。&nbsp;妥当な値に設定されている&nbsp;限り、多数のトークンがある場合でも&nbsp;<em>btcrecover</em>を使用できます&nbsp;。&nbsp;最初に成功しなかった場合に、&nbsp;&nbsp;より多くの数で&nbsp;<em>btcrecover を</em><code>--max-tokens</code>再実行したい場合は&nbsp;、&nbsp;既に試した組み合わせを試さないように指定することもできます。<em></em><code>--max-tokens</code><code>--min-tokens</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="expanding-wildcards">ワイルドカードの拡張</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>トークンの 1 つに数字が含まれていると思われるが、その数字がわからない場合はどうすればよいでしょうか?&nbsp;たとえば、カイロの後に間違いなく 1 桁が続くと思われる場合は、次のようにします。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo0 Cairo1 Cairo2 Cairo3 Cairo4 Cairo5 Cairo6 Cairo7 Cairo8 Cairo9 Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>これは確かに機能しますが、あまり便利ではありません。この次のトークン ファイルは同じ効果がありますが、書きやすいです。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo%d Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>は、&nbsp;&nbsp;<code>%d</code>&nbsp;1 桁のすべての組み合わせに置き換えられるワイルドカードです。使用できるさまざまな種類のワイルドカードの例を次に示します。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%d</code>&nbsp;– 一桁</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2d</code>&nbsp;– 正確に 2 桁</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,3d</code>&nbsp;– 1 桁から 3 桁の間 (考えられるすべての順列)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%0,2d</code>&nbsp;– 0桁から2桁の間（つまり、桁がない場合も試す）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%a</code>&nbsp;– 1 つの ASCII 小文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,3a</code>&nbsp;– 1 ～ 3 個の小文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%A</code>&nbsp;– 1 つの ASCII 大文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%n</code>&nbsp;– 1 桁の数字または小文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%N</code>&nbsp;– 1 桁の数字または大文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%ia</code>&nbsp;– %a の「大文字と小文字を区別しない」バージョン: 単一の小文字または大文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%in</code>&nbsp;– 1 桁の小文字または大文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,2in</code>– 1 ～ 2 文字の長さの数字、小文字または大文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%[chars]</code><code>[</code>&nbsp;–と の&nbsp;&nbsp;間の文字のちょうど 1 つ&nbsp;<code>]</code>&nbsp;(例: a&nbsp;&nbsp;<code>c</code>、&nbsp;&nbsp;<code>h</code>、&nbsp;&nbsp;<code>a</code>、&nbsp;&nbsp;<code>r</code>、または&nbsp;<code>s</code>)&nbsp;<em><strong>注</strong>: このワイルドカード内のすべての文字は、通常、その文字がトークンとして使用された場合に独自のワイルドカード (スペースなど) を持つ場合でも、そのまま使用されます。 $、% または ^</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,3[chars]</code><code>[</code>&nbsp;–と の&nbsp;&nbsp;間の文字の 1 から 3 の間&nbsp;<code>]</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%[0-9a-f]</code>&nbsp;– これらの文字の 1 つだけ:&nbsp;<code>0123456789abcdef</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2i[0-9a-f]</code>&nbsp;– これらの文字のうち正確に 2 つ:&nbsp;<code>0123456789abcdefABCDEF</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%s</code>&nbsp;– 単一のスペース</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%l</code>&nbsp;– 1 つの改行文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%r</code>&nbsp;– 1 つのキャリッジ リターン文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%R</code>&nbsp;– 1 つの改行またはキャリッジ リターン文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%t</code>&nbsp;– 単一のタブ文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%T</code>&nbsp;– 単一のスペースまたはタブ文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%w</code>&nbsp;– 1 つのスペース、改行、またはキャリッジ リターン文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%W</code>&nbsp;– 単一のスペース、改行、キャリッジ リターン、またはタブ文字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%y</code>&nbsp;– 任意の 1 つの ASCII 記号</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%Y</code>&nbsp;– 任意の 1 つの ASCII 数字または記号</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%p</code>&nbsp;– 単一の ASCII 文字、数字、または記号</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%P</code>&nbsp;– または のいずれかからの任意の 1 文字&nbsp;<code>%p</code>&nbsp;(&nbsp;<code>%W</code>&nbsp;ほとんどすべて)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%q</code>&nbsp;– 単一の ASCII 文字、数字、記号、またはスペース。(ほとんどのベンダーの BIP39 パスフレーズに通常使用される文字)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%c</code>&nbsp;– コマンド ラインで指定されたカスタム セットからの 1 文字&nbsp;<code>--custom-wild characters</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%C</code>&nbsp;– の大文字バージョン&nbsp;(&nbsp;小文字がない&nbsp;場合&nbsp;<code>%c</code>&nbsp;と同じ&nbsp;)<code>%c</code><code>%c</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%ic</code>&nbsp;– の大文字と小文字を区別しないバージョン&nbsp;<code>%c</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%%</code>&nbsp;– 単一&nbsp;<code>%</code>&nbsp;(&nbsp;<code>%</code>パスワードにある がワイルドカードと混同されないようにするため)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%^</code>&nbsp;– 単一&nbsp;<code>^</code>&nbsp;(したがって、トークンの先頭にある場合、アンカーと混同されません)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%S</code>&nbsp;– 単一&nbsp;<code>$</code>&nbsp;(はい、それは&nbsp;<code>%</code>&nbsp;大文字で、&nbsp;<code>S</code>&nbsp;ドル記号に置き換えられます。混乱を招く場合は申し訳ありません)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%h</code>&nbsp;– 単一の 16 進文字 (0-9、AF)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%*</code>&nbsp;– 単一の Base58 文字 (ビットコイン Base58 文字セット)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>これまで、ほとんどの機能は、パスワードに何が含まれている可能性があるかについての知識を利用して、試行する必要があるパスワードの数を減らすのに役立ちました。ワイルドカードを使用すると、試行する必要があるパスワードの数が大幅に増えるため、適度に使用することをお勧めします。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="backreference-wildcards">後方参照ワイルドカード</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>後方参照ワイルドカードは、パスワードの前のどこかに現れる 1 つ以上の文字をコピーします。最も単純なケースでは、あまり役に立ちません。たとえば、トークンでは&nbsp;<code>Z%b</code>、 は&nbsp;<code>%b</code>&nbsp;その直前の文字を単純にコピーして、&nbsp;&nbsp;<code>ZZ</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>パスワードに&nbsp;<code>AA</code>、 、&nbsp;<code>BB</code>から まで&nbsp;のパターンが含まれている<code>ZZ</code>が、 は決して含まれない&nbsp;場合を考えてみましょう<code>AZ</code>。これらのパターンを生成するために使用することはできます&nbsp;<code>%2A</code>&nbsp;が、最終的には&nbsp;<code>AZ</code>&nbsp;試されることになります。&nbsp;<code>%2A</code>&nbsp;は 676 の異なる組み合わせを生成しますが、この例では 26 のみを試したいと考えています。代わりに、2 つのワイルドカードを一緒に使用できます&nbsp;<code>%A%b</code>。は&nbsp;<code>%A</code>&nbsp;1 文字 (から&nbsp;<code>A</code>&nbsp;まで&nbsp;<code>Z</code>) に展開され、&nbsp;&nbsp;この展開が行われた&nbsp;<em>後</em><code>%b</code>、 は&nbsp;その文字をコピーするため、必要な 26 個のパターンのみが得られます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>通常のワイルドカードと同様に、後方参照ワイルドカードにはコピーの長さが含まれる場合があります。次に例を示します。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Test%d%b</code>&nbsp;–&nbsp;<code>Test00</code>&nbsp;を通じて&nbsp;<code>Test99</code>、しかし決して&nbsp;<code>Test12</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%d%2b</code>&nbsp;–&nbsp;<code>Test000</code>&nbsp;を通じて&nbsp;<code>Test999</code>、しかし決して&nbsp;<code>Test123</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%d%0,3b</code>&nbsp;–&nbsp;&nbsp;<code>Test0</code>&nbsp;to&nbsp;&nbsp;<code>Test9</code>&nbsp;(後方参照の長さは 0)、&nbsp;&nbsp;<code>Test00</code>&nbsp;to&nbsp;<code>Test99</code>など、&nbsp;&nbsp;<code>Test0000</code>&nbsp;to&nbsp;<code>Test9999</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>これまでの例では、コピーは のすぐ左にある文字から開始されます&nbsp;が、これは&nbsp;の直前に を&nbsp;<code>%b</code>追加することで変更できます&nbsp;。たとえば、次のようになります。<code>;#</code><code>b</code></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Test%b</code>&nbsp;-&nbsp;<code>Testt</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%;1b</code>&nbsp;– 上記と同じように、1 戻ることを開始します。&nbsp;<code>Testt</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%;2b</code>&nbsp;– 開始 2 バック,&nbsp;<code>Tests</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%;4b</code>&nbsp;– 開始 4 バック,&nbsp;<code>TestT</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%2;4b</code>&nbsp;– コピーの長さが 2 で、4 つ後ろに開始します。&nbsp;<code>TestTe</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%8;4b</code>&nbsp;– コピーの長さが 8 で、4 つ後ろに開始します。&nbsp;<code>TestTestTest</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%0,2;4b</code>&nbsp;– 4 つ後ろから開始し、コピーの長さは 0 から 2 まで:&nbsp;&nbsp;<code>Test</code>、&nbsp;&nbsp;<code>TestT</code>、および&nbsp;<code>TestTe</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2Atest%2;6b</code><code>ABtestAB</code>&nbsp;–と の&nbsp;&nbsp;ようなパターンで、&nbsp;<code>XKtestXK</code>&nbsp;前後の 2 つの大文字が&nbsp;<code>test</code>&nbsp;互いに一致しますが、&nbsp;<code>ABtestXK</code>&nbsp;一致しない場所は決してありません。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>要約すると、最初に a の左側のワイルドカード&nbsp;<code>%b</code>&nbsp;が展開され、次に&nbsp;<code>%b</code>&nbsp;左側から 1 つまたは複数の文字をコピーして が置き換えられ、次に右側のワイルドカード (存在する場合) が調べられます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="contracting-wildcards">ワイルドカードの縮小</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>パスワード推測に新しい文字を追加する代わりに、ワイルドカードを縮小すると 1 つ以上の文字が削除されます。次に例を示します。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>Start%0,2-End
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>縮小&nbsp;<code>%0,2-</code>&nbsp;ワイルドカードは、どちらかの側から 0 ～ 2 個の隣接する文字を削除するため、&nbsp;&nbsp;<code>StartEnd</code>&nbsp;(0 を削除)、&nbsp;&nbsp;<code>StarEnd</code>&nbsp;(左から 1 を削除)、&nbsp;&nbsp;<code>StaEnd</code>&nbsp;(左から 2 を削除)、&nbsp;&nbsp;<code>Starnd</code>&nbsp;(左から 1、右から 1 を削除)、&nbsp;&nbsp;<code>Startnd</code>&nbsp;(右から 1 を削除)、および&nbsp;<code>Startd</code>&nbsp;(右から 2 を削除) が試行されます。これは、コピーと貼り付けのエラーを考慮する場合に役立ちます。たとえば、次のようになります。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>%0,20-A/Long/Password/with/symbols/that/maybe/was/partially/copy/pasted%0,20-
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>このパスワードのさまざまなバージョンが試行され、両端から最大 20 文字が削除されます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以下に、短縮ワイルドカードの 3 つのタイプを示します。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%0,5-</code>&nbsp;– ワイルドカードのいずれかの側から取られた 0 ～ 5 個の隣接する文字 (合計) を削除します</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%0,5&lt;</code>&nbsp;– ワイルドカードの左側からのみ隣接する 0 ～ 5 文字を削除します</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%0,5&gt;</code>&nbsp;– ワイルドカードの右側からのみ隣接する 0 ～ 5 文字を削除します</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>1 つのトークンの縮小ワイルドカードは、他のトークンから文字を削除する可能性がありますが、別のワイルドカードを削除したり、交差させたりすることは決してないことに注意してください。これを完全に説明する例を次に示します (これらの特定の詳細に興味がない場合は、次のセクションにスキップしてください)。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>12</td><td><code>AAAA%0,10&gt;BBBB xxxx%dyyyy</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>これらの 2 つのトークンには、それぞれ 8 つの通常の文字があります。最初のトークンには、右側から最大 10 文字を削除する短縮ワイルドカードがあり、2 番目のトークンには、1 桁に拡張される拡張ワイルドカードがあります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これらのトークンから生成されるパスワードの 1 つが です&nbsp;<code>AAAABBxxxx5yyyy</code>。これは、最初のトークンとそれに続く 2 番目のトークンを選択し、ワイルドカードを適用して短縮ワイルドカードで 2 文字を削除したものです。もう 1 つは&nbsp;<code>AAAAxx5yyyy</code>&nbsp;同じトークンから取得されたものですが、短縮ワイルドカードによって 6 文字が削除されており、そのうちの 2 つは 2 番目のトークンからのものです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>yyyy</code>&nbsp;他のワイルドカードが削除されたり交差したりすることはないため、数字と the は&nbsp;短縮ワイルドカードによって削除されることはありません。短縮ワイルドカードが最大 10 文字を削除するように設定されていても、 によって&nbsp;ブロックされる<code>AAAAyyy</code>&nbsp;ため、生成されることはありません&nbsp;<code>%d</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="keyboard-walking-backreference-wildcards-revisited">キーボード ウォーキング — 後方参照ワイルドカード、再訪</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>この機能は、後方参照ワイルドカードとタイプミス マップの両方の特性を 1 つの関数に結合します。以下のタイプミス マップ (または上記の後方参照ワイルドカード) をまだ読んでいない場合は、このセクションを飛ばして後で戻ってくる必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>00test11</code>、&nbsp;<code>11test22</code>などから まで&nbsp;の複雑なパスワード パターンを考えてみましょう&nbsp;<code>88test99</code>。つまり、パターンは次の 5 つの文字列を組み合わせて生成されます&nbsp;<code>#</code>&nbsp;<code>#</code>&nbsp;<code>test</code>&nbsp;<code>#+1</code>&nbsp;<code>#+1</code>。単純な後方参照ワイルドカードを使用すると、このトークンでそのようなパターンをほぼ生成できます:&nbsp;&nbsp;<code>%d%btest%d%b</code>.&nbsp;<code>33test55</code>&nbsp;これにより、リストからすべてが生成されますが、たとえば、3 + 1 は 5 ではないため、パターンに一致しない場合でも、より多くの不要なものが生成されます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;代わりに、後方参照ワイルドカードが前の文字を単純にコピーする以上のことを行う方法が必要です。前の文字の<em>変更されたコピー</em>を作成できる必要があります&nbsp;。これは、別のマップ ファイルを使用して置換を決定することにより、タイポス マップが文字を置換するのと同じ方法で行うことができます。この例を続けるには、新しいマップ ファイルが必要です&nbsp;<code>nextdigit.txt</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9</td><td><code>0 1 1 2 2 3 3 4 4 5 5 6 6 7 7 8 8 9</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>最後に、このマップ ファイルを使用して探しているパターンを生成するトークンを次に示します&nbsp;<code>%d%btest%2;nextdigit.txt;6b</code>。これはかなり複雑なので、分解してみましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%d</code>&nbsp;– まで展開&nbsp;<code>0</code>&nbsp;する&nbsp;<code>9</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%b</code>&nbsp;– 前の文字をコピーします&nbsp;<code>00</code>&nbsp;。&nbsp;<code>99</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>test</code>&nbsp;– 今、私たちは&nbsp;<code>00test</code>&nbsp;やり遂げました&nbsp;<code>99test</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2;nextdigit.txt;6b</code>&nbsp;– 以下で構成される単一の後方参照ワイルドカード:<ul><li><code>2</code>&nbsp;– コピーの長さ (展開後の結果の長さ)</li><li><code>nextdigit.txt</code>&nbsp;– 使用されるマップ ファイルは、文字の変更方法を決定します</li><li><code>6</code>&nbsp;– コピーを開始するワイルドカードの左端。の末尾から左に数えて6文字が&nbsp;<code>00test</code>&nbsp;最初&nbsp;<code>0</code></li></ul>トークンが で始まるときにこのワイルドカードを展開した結果&nbsp;は<code>00test</code>&nbsp;.&nbsp;<em>コピーの長さが2</em><code>00test11</code>であるため、2 つの に展開され&nbsp;、&nbsp;ファイルが a&nbsp;&nbsp;&nbsp;(最初の列の) を a&nbsp;&nbsp;&nbsp;(2 列目の)にマップするため、単に をコピーするのではなく、&nbsp;変更された に展開されます。同様に、 a&nbsp;&nbsp;は に展開されます&nbsp;。&nbsp;&nbsp;検索文字 a が&nbsp;マップ ファイル (の最初の列) に存在しないため、展開され、変更されずにコピーされます&nbsp;。&nbsp;<em></em>&nbsp;<code>1</code><code>1</code><code>0</code><code>0</code><code>1</code><code>77test</code><code>77test88</code><code>99test</code><code>99test99</code><code>9</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>後方参照ワイルドカード内でマップ ファイルを使用する場合、ファイル名の<code>;</code>両側に常にセミコロン ( ) があることに注意してください。これらはすべて有効な後方参照ワイルドカードです (ただし、コピーの長さと開始位置が異なるため、すべて異なります)&nbsp;&nbsp;:&nbsp;<code>%;file.txt;b</code>,&nbsp;&nbsp;<code>%2;file.txt;b</code>,&nbsp;&nbsp;<code>%;file.txt;6b</code>.&nbsp;<code>%2;file.txt;6b</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最後の例には、キーボード ウォーキングと呼ばれるものが含まれます。タイピストが任意の文字で開始し、特定のパターンを使用して指を動かして次の文字を選択するパスワード パターンを考えてみましょう。一定の長さです。マップ ファイルを使用する 1 つの後方参照ワイルドカードで、このパターンを作成できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このパターン のマップ ファイルの先頭は次&nbsp;<code>pattern.txt</code>のようになります。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6</td><td><code>q 2a a wz z s 2 w w 3s ...</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>したがって、最後の文字が a の場合&nbsp;<code>q</code>、パターン内の次の文字は a&nbsp;<code>2</code>&nbsp;または an&nbsp;&nbsp;<code>a</code>&nbsp;(右上または右下に移動するため) のいずれかになります。最後の文字が の場合&nbsp;<code>z</code>、次の文字に使用できる方向は 1 つだけです。つまり、右上から です&nbsp;<code>s</code>。このマップ ファイルと次のトークンを使用すると、4 ～ 6 文字の長さでこのパターンに従うすべての組み合わせが試行されます。&nbsp;<code>%a%3,5;pattern.txt;b</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="delimiters-spaces-and-special-symbols-in-passwords">パスワードの区切り文字、スペース、および特殊記号</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>デフォルトでは、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;1 つ以上の空白を使用して、tokenlist ファイル内のトークンを分離し、typos-map ファイル内の置換文字から置換対象文字を分離します。また、これらのファイル内の余分な空白も無視されます。これにより、スペースやその他の特定の記号を含むパスワードをテストすることが難しくなります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これを回避する 1 つの方法は、トークンリスト ファイルに対してのみ有効で、&nbsp;<code>%s</code>&nbsp;単一のスペースに置き換えられるワイルドカードを使用することです。トークンリスト ファイルとタイポス マップ ファイルの両方で機能する別のオプションは、&nbsp;<code>--delimiter</code>&nbsp;この動作を変更できるオプションを使用することです。使用された場合、空白は無視されなくなり、余分な空白も取り除かれます。代わりに、新しい&nbsp;文字列を<em>指定どおりに正確に</em>使用して&nbsp;、トークンまたはタイポス マップの列を区切る<code>--delimiter</code>&nbsp;必要があります&nbsp;。空白はすべてトークンの一部になるため、これらのファイルに誤って空白を追加しないように注意する必要があります。<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>さらに、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;、tokenlist ファイル内の特定の状況下で次のシンボルを特別なものと見なします (シンボルについては&nbsp;<code>#</code>&nbsp;、typos-map ファイル内でも)。特殊記号は構文の一部であり、パスワードの一部ではありません。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%</code>&nbsp;– 常に特別と見なされます (スタイルのワイルドカード内の場合を除きます&nbsp;&nbsp;。&nbsp;<em>ワイルド</em><code>%[...]</code>カードのセクションを参照してください&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#expanding-wildcards">)</a>&nbsp;&nbsp;。&nbsp;<code>%%</code>&nbsp;トークン内の は、&nbsp;<code>%</code>&nbsp;検索中にに置き換えられます</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>^</code>&nbsp;– トークンの最初の文字である場合のみ特別です。&nbsp;&nbsp;検索中<code>%^</code>&nbsp;に に置き換えられます&nbsp;<code>^</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>$</code>&nbsp;– トークンの最後の文字である場合のみ特別です。&nbsp;<code>%S</code>&nbsp;(大文字に注意してください&nbsp;) は、&nbsp;検索中に<code>S</code>に置き換えられます&nbsp;<code>$</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>#</code>&nbsp;–&nbsp;&nbsp;行の&nbsp;<em>最初の文字の場合のみ特別です。</em><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#basics">ここのコメントに関する注記を参照してください</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>+</code>&nbsp;– それが行の最初の (スペースを含まない) 文字であり、その直後にスペース (または区切り文字) といくつかのトークンが続く場合にのみ特別です (相互除外セクションを参照)。<code>+</code>&nbsp;トークンとして単一の文字が必要な場合は&nbsp;、それが行の最初のトークンではないことを確認するか、それ自体が行にあることを確認してください</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>]</code>&nbsp;–&nbsp;スタイルのワイルドカード<code>%[</code>&nbsp;の終わりをマークするトークンが&nbsp;続く場合にのみ特別です<code>%[...]</code>。&nbsp;の&nbsp;<em>直後に</em>ある場合&nbsp;<code>%[</code>、それは置換セットの一部であり、次&nbsp;<em>は</em>&nbsp;<code>]</code>&nbsp;実際にワイルドカードを終了します。たとえば、ワイルドカード&nbsp;<code>%[]x]</code>&nbsp;には 2 つの置換文字&nbsp;<code>]</code>&nbsp;と&nbsp;<code>x</code>.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>これはいずれも passwordlist ファイルには当てはまりません。このファイルは常にスペースと記号 (キャリッジ リターンとライン フィードを除く) を逐語的に扱い、それらをパスワードの一部として扱います。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>既知の位置の 6 文字と未知の 6 文字を含むファイルの例は、次の場所にあります: Sample TokenList</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このトークンリストを使用するコマンドの例は次のとおりです。&nbsp;<code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./btcrecover/test/test-listfiles/SeedTokenListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>この方法を使用する場合は、ニーモニックの長さと言語を指定する必要があることに注意してください。</strong>&nbsp;サポートされている言語は、こちらで確認できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>BTCRecover は、コマンドを介してテストされるシードを出力することもできます&nbsp;<code>--listpass</code>&nbsp;。これは、トークンリストのデバッグに役立ちます。トークンリストからのシードリストの詳細については、こちらを参照してください… (多くのシード フレーズを生成する場合にも役立ちますが、これは現在のところ非常に大きくなり、非常に速くなるテキストファイルをダンプするだけです...これは将来的に少し最適化されます）</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="the-passwordlist">パスワードリスト</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>テストしたいパスワード全体の単純なリストが既にあり、上記の機能が必要ない場合は、コマンドライン オプションを使用できます (btcrecover の実行で後述するオプションの&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#running-btcrecover"><em>代わり</em></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#running-btcrecover">に&nbsp;</a>&nbsp;)&nbsp;&nbsp;<code>--passwordlist</code>&nbsp;。&nbsp;&nbsp;セクション）。パスワードに非<a href="https://en.wikipedia.org/wiki/ASCII">ASCII</a>&nbsp;&nbsp;(非英語) 文字が含まれている場合は、&nbsp;先に進む前に<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#unicode-support">Unicode サポート</a>のセクションを読む必要があります&nbsp;。<code>--tokenlist</code><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#running-btcrecover"><em></em></a><a href="https://en.wikipedia.org/wiki/ASCII"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#unicode-support"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>--passwordlist</code>&nbsp;ファイルなしで&nbsp;指定すると&nbsp;、&nbsp;<em>btcrecover は</em>&nbsp;、コマンド プロンプト ウィンドウで、パスワードのリストを 1 行に 1 つずつ入力するように求めます。パスワードを含むテキスト ファイルが既にある場合は、代わりに使用できます&nbsp;<code>--passwordlist FILE</code>&nbsp;(&nbsp;<code>FILE</code>&nbsp;ファイル名に置き換えます)。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これらのスペースが実際にパスワードの一部でない限り、余分なスペースを追加しないでください。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>オプションを使用する場合、各行は 1 つのパスワードとして逐語的に使用されます&nbsp;<code>--passwordlist</code>&nbsp;(上記の機能は適用されません)。ただし、以下で説明するタイポ機能のいずれかを使用して、パスワードリストのさまざまなバリエーションのパスワードを試すことができます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="seedlists">シードリスト</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>「passwordlist」(&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/">こちらを</a>参照) 機能は、引数を介してシードフレーズで使用することもできます&nbsp;<code>--seedlist</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>パスワード リストとの主な違いは、1 行に 1 つのシード フレーズをリストするだけで、コマンドを介してエクスポートされるのと同じスタイルでフォーマットする必要があることです&nbsp;<code>--listpass</code>&nbsp;。これは、このツールの tokenlst ステップの出力を passwordlist ステップで直接使用できるようにするためです。<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/btcrecover/test/test-listfiles/SeedListTest.txt">サンプルシードリスト</a>を参照してください&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/btcrecover/test/test-listfiles/SeedListTest.txt"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>SeedList の使用例 (上記の token list コマンドからの出力として listseeds を使用して作成されたシードリスト):&nbsp;<code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --seedlist ./btcrecover/test/test-listfiles/SeedListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>さまざまなウォレットのウォレット ファイルのパスワード回復</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>以下のウォレットのシードフレーズ (ニーモニック) リカバリー<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://electrum.org/">Electrum</a>&nbsp;&nbsp;(1.x、2.x、3.x、および 4.x) (レガシーおよび Segwit ウォレットの場合。Segwit ウォレットの場合は –bip32-path “m/0'/0” を設定し、レガシーの場合は bip32-path を空白のままにします… 2fa ウォレットのサポートなし…)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.electroncash.org/">電子キャッシュ</a>&nbsp;(2.x、3.x、および 4.x)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>以下を含むBIP-32/39 準拠のウォレット ( <a href="https://bitcoinj.github.io/">bitcoinj</a> ):<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://multibit.org/">マルチビット HD</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://play.google.com/store/apps/details?id=de.schildbach.wallet">Android/BlackBerry 用のビットコイン ウォレット(以前に</a><a href="https://github.com/gurnec/decrypt_bitcoinj_seed">decrypt_bitcoinj_seeds</a>&nbsp;によって抽出されたシードを使用&nbsp;)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://play.google.com/store/apps/details?id=com.hivewallet.hive.cordova">Android 用 Hive</a>、&nbsp;&nbsp;<a href="https://github.com/hivewallet/hive-ios">iOS 用 Hive</a>、および&nbsp;<a href="https://hivewallet.com/">Hive Web</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://brd.com/">ブレッドウォレット</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-32/39/44 Bitcoin & Ethereum 準拠のウォレット:<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://wallet.mycelium.com/">Android用菌糸体</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.bitcointrezor.com/">安全</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.ledgerwallet.com/">元帳</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://shapeshift.io/keepkey/">キープキー</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://jaxx.io/">ジャックス</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.coinomi.com/">コノミ</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.exodus.io/">エクソダス</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.myetherwallet.com/">マイイーサウォレット</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://bither.net/">ビター</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://blockchain.com/wallet">Blockchain.com</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://bitaddress.org/">暗号化 (BIP-38) ペーパー ウォレットのサポート (例: Bitaddress.org から)</a>&nbsp;&nbsp;liteaddress.org、paper.dash.org などのアルトコイン フォークでも動作します…</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ブレインウォレット<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Sha256(パスフレーズ) ブレインウォレット (例: Bitaddress.org、liteaddress.org、paper.dash.org)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>sCrypt で保護されたブレインウォレット (例: Warpwallet、Memwallet)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ビットコイン ウォレットのパスワード回復のサポート:<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://bitcoincore.org/">ビットコインコア</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://multibit.org/">MultiBit HD</a>&nbsp;および&nbsp;<a href="https://multibit.org/help/v0.5/help_contents.html">MultiBit Classic</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://electrum.org/">Electrum</a>&nbsp;&nbsp;(1.x、2.x、3.x、および 4.x) (レガシーおよび Segwit ウォレットの場合。Segwit ウォレットの場合は –bip32-path “m/0'/0” を設定し、レガシーの場合は bip32-path を空白のままにします… 2fa ウォレットのサポートなし…)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://github.com/hivewallet/hive-mac/wiki/FAQ">Hive for OS X を</a>含む&nbsp;<a href="https://bitcoinj.github.io/">bitcoinj</a>に基づくほとんどのウォレット&nbsp;<a href="https://github.com/hivewallet/hive-mac/wiki/FAQ"></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-39 パスフレーズ (シード回復でサポートされているすべての暗号、および Electrum シードの「Extra Words」の回復もサポートしています)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://ciphrex.com/products/">mSIGNA (コインボールト)</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://blockchain.com/wallet">Blockchain.com</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://block.io/">block.io</a>&nbsp;&nbsp;(ウォレット「シークレットPIN」の復元)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://github.com/jackjack-jj/pywallet">pywallet –</a>&nbsp;ビットコイン アンリミテッド/クラシック/XT/コア ウォレットのダンプウォレット</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://play.google.com/store/apps/details?id=de.schildbach.wallet">Android/BlackBerry の</a>&nbsp;支出 PIN と暗号化されたバックアップ用のビットコイン ウォレット</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://github.com/kncgroup/bitcoin-wallet"></a>&nbsp;Android暗号化バックアップ<a href="https://github.com/kncgroup/bitcoin-wallet">用の KnC ウォレット</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://bither.net/">ビター</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>以下を含む、上記のいずれかから派生したほとんどのウォレットの Altcoin パスワード回復サポート:<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.coinomi.com/en/">Coinomi</a>&nbsp;&nbsp;(パスワードで保護されたウォレットのみをサポート)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://metamask.io/">Metamask</a>&nbsp;&nbsp;(および Binance Chain Wallet、Ronin Wallet などの Metamask クローン)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://litecoin.org/">ライトコインコア</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://electrum-ltc.org/">Electrum-LTC</a>&nbsp;&nbsp;(Legacy および Segwit ウォレットの場合。Segwit ウォレットの場合は –bip32-path “m/0'/0” を設定し、Legacy の場合は bip32-path を空白のままにします... 2fa ウォレットのサポートはありません...)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.electroncash.org/">電子キャッシュ</a>&nbsp;(2.x、3.x、および 4.x)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://litecoin.org/"></a>&nbsp;Android暗号化バックアップ<a href="https://litecoin.org/">用 Litecoin ウォレット</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://dogecoin.com/">ドージコインコア</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://multidoge.org/">マルチドージ</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://dogechain.info/">dogechain.info</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://dogecoin.com/"></a>&nbsp;Android暗号化バックアップ<a href="http://dogecoin.com/">用の Dogecoin ウォレット</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://yoroi-wallet.com/#/">Cardano Master_Passwords の Yoroi Wallet for Cardano</a>&nbsp;&nbsp;Master_Passwords は、ウォレット データから抽出されます (ブラウザーまたは rooted/jailbroken 電話で)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/">Raw Eth 秘密鍵の破損</a>&nbsp;文字が欠落している個々の秘密鍵。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://myetherwallet.com/">Ethereum UTC キーストア ファイル</a>&nbsp;Ethereum キーストア ファイル。通常、MyEtherWallet、MyCrypto などのウォレットで使用されます (Theta などの Eth クローンでもよく使用されます)。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://en.wikipedia.org/wiki/Free_and_open-source_software">無料でオープン ソース</a>&nbsp;- 誰でもこのソフトウェアをダウンロード、検査、使用、再配布できます</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Windows、Linux、OS X でサポート</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Unicode パスワードとシードのサポート</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ユーザーが選択可能なスレッド数によるマルチスレッド検索</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>検索ワークロードを複数のデバイスに分散する機能</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/GPU_Acceleration/"></a>&nbsp;ビットコイン コア パスワード、Blockchain.com (メインおよびセカンド パスワード)、エレクトラム パスワード + BIP39、エレクトラム シードの<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/GPU_Acceleration/">GPU アクセラレーション</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>パスワードのワイルドカード展開</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>パスワードとシードの入力シミュレーション</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>進行状況バーと ETA 表示 (コマンド ライン)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>オプションの自動保存 - 進行状況を失うことなく、パスワードの回復を中断して続行します</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>シンプルなグラフィカル ユーザー インターフェイスによる自動シード リカバリ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>–pathlist コマンドを使用して、特定のシードの複数の派生パスを同時に検索する機能 (パスリスト ファイルの例)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>サポートされているほぼすべてのウォレットの「オフライン」モード - 抽出スクリプトの 1 つ&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Extract_Scripts/">(詳細についてはクリック)</a><em>を</em>使用して&nbsp;、パスワードの回復&nbsp;を試みる&nbsp;&nbsp;のに十分な情報だけを抽出します&nbsp;<em>。</em>ビットコインウォレット。<em></em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>上記に記載されていない暗号/ウォレットをツールでサポートする場合は、ツールが機能することをテストし、そのコインの単体テストと、アドレス形式を受け入れるために必要なコードを含む PR を送信してください。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 id="btcrecover-extract-scripts"><em>btcrecover</em>&nbsp;抽出スクリプト</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>&nbsp;場合によっては、ターゲット ウォレット ファイルが保存されているコンピュータで直接<em>btcrecover</em>を実行することが望ましくないことがあります&nbsp;。例えば：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>より高速な CPU または GPU を備えたコンピューターまたはクラウドベースの仮想マシンは、&nbsp;&nbsp;<em>btcrecover を</em>実行するのに適した場所である可能性があります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;パスワードを正しく検索するように<em>btcrecover</em>を構成するのは&nbsp;難しい場合があります。&nbsp;自分のコンピューターで<em>btcrecover</em>を構成して実行できる人を探すことに興味があるかもしれません&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>btcrecover</em>&nbsp;に有害なバグやその他の悪意のある動作がない&nbsp;ことを信頼できない場合があります&nbsp;。<em>btcrecover</em>&nbsp;はオープン ソースであり、信頼できないバイナリをインストールする必要はありません。ただし、これはかなり長く複雑な Python スクリプトでもあるため、他の Python プログラマーでさえ、有害なコードが含まれていないことを確認することは困難です (意図的に悪意のあるもの、または偶然に発生したもの)。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>このディレクトリ内の抽出スクリプトは、&nbsp;&nbsp;<em>btcrecover が</em>&nbsp;パスワード検索を実行できるように、ウォレット ファイルから必要なだけの情報を抽出する、比較的短く単純なスクリプトです。これらのスクリプトは、パスワードが見つかった後でも、ビットコイン ファンドを危険にさらすほどの情報を抽出することはありません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>btcrecover</em>の詳細については&nbsp;<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/CREDITS/">クレジット</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/licence/">ライセンス</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="btcrecoverpy-tutorial">btcrecover.py チュートリアル</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover.py は</em>&nbsp;、Bitcoin Core、MultiBit (Classic および HD)、Electrum (1.x および 2.x)、mSIGNA (CoinVault)、Hive for OS X、Blockchain をサポートする、無料でオープン ソースのマルチスレッド ウォレット パスワード回復ツールです。 com (v1-v3 ウォレット形式、メイン パスワードとセカンド パスワードの両方)、Bither、および Android 用のビットコイン &amp; KNC ウォレット。これは、ほとんどのパスワードを既に知っているが、考えられるさまざまな組み合わせを試す際に支援が必要な場合のために設計されています。このチュートリアルでは、提供する機能について説明します。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="installation">インストール BTCRecover</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover をインストールするには、いくつかの基本的な手順があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1) BTCRecover スクリプトをダウンロードして解凍します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) Python3 をダウンロードしてインストールする</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) Python PIP 経由で必要なパッケージをインストールします</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4) (オプション) GPU アクセラレーション用の PyOpenCL モジュールをインストールする</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) インストールをテストします (オプションですが、良い考えです)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これらの手順は、サポートされているオペレーティング システムごとに以下のビデオでも説明されています。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><code>python</code>&nbsp;注: オペレーティング システムと python 環境によっては、コマンド&nbsp;を&nbsp;<code>python3</code>.&nbsp;(デフォルトでは、使用するコマンドは&nbsp;<code>python</code>&nbsp;Windows と&nbsp;<code>python3</code>&nbsp;Linux で使用されます)ほとんどの技術者以外のユーザーは Windows を使用しているため、すべての例のコマンドは、&nbsp;<code>python</code>&nbsp;このプラットフォームのデフォルトと一致するように使用されます。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>ビデオチュートリアル</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>ウィンドウズ：&nbsp;</strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/8q65eqpf4gE"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/8q65eqpf4gE
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>Ubuntu Linux:</strong>&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/Met3NbxcZTU"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Met3NbxcZTU
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>マックOS：&nbsp;</strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/Qzc3oHzbcAo"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Qzc3oHzbcAo
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="1-downloading-btcrecover">1)&nbsp;&nbsp;<em>btcrecoverのダウンロード</em></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/archive/master.zip">https://github.com/demining/CryptoDeepTools/archive/master.zip</a>から最新バージョンをダウンロードし&nbsp;&nbsp;、選択した場所に解凍します。<em>btcrecover</em>自体のインストール手順はありません&nbsp;&nbsp;が、オペレーティング システムと回復しようとしているウォレットの種類に応じて、以下の追加要件があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="2-install-python">2) パイソンをインストールする</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注:</strong>&nbsp;公式にサポートされているのは Python 3.7 以降のみです。BTCRecover は、サポートされているすべての環境 (Windows、Linux、Mac) で、サポートされているすべての Python バージョン (3.7、3.8、3.9、3.10) で自動的にテストされるため、BTCRecover と必要なパッケージはすべて正しく機能します。BTCRecover の一部の機能は、以前のバージョンの Python でも動作する可能性があります。最善の策は、run-all-tests.py を使用して、何が機能し、何が機能しないかを確認することです…</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="windows">ウィンドウズ</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Windows に BTCRecover をインストールするビデオ デモ:&nbsp;&nbsp;<a href="https://youtu.be/8q65eqpf4gE">https://youtu.be/8q65eqpf4gE</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Python のダウンロード ページ (&nbsp;&nbsp;<a href="https://www.python.org/downloads/windows/">https://www.python.org/downloads/windows/ ) にアクセスし、最新の</a><strong>Python 3.9</strong>リリースのリンクをクリックします&nbsp;&nbsp;(Python 3.10 なども動作しますが、Python 3.9 では必要なモジュールのインストールが簡単です)。 ) のページの上部にある&nbsp;<em>[Python Releases for Windows]</em>という見出しの下にあるリリース。<code>Windows x86 MSI installer</code>&nbsp;Python の 32 ビット バージョン用、または&nbsp;<code>Windows x86-64 MSI installer</code>&nbsp;64 ビット バージョン用の をダウンロードして実行します&nbsp;。最新の PC では 64 ビット バージョンを使用する必要がありますが、お使いの PC と互換性があるバージョンがわからない場合は、32 ビット バージョンを選択してください。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em><strong>Windows に Python をインストールする場合は、インストーラーの最初の画面で [Python 3.9 を PATH に追加] を選択してください。</strong></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>大規模なマルチ CPU システムに関する注意:</strong>&nbsp;&nbsp;Windows では、可能なスレッド数が 64 に制限されています。システムにこれよりも多くの論理/物理コアがある場合は、Linux でツールを実行することをお勧めします。(Ubuntu は簡単に始められる場所です)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="linux">Linux</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Ubuntu Live USB に BTCRecover をインストールするビデオ デモ:&nbsp;&nbsp;<a href="https://youtu.be/Met3NbxcZTU">https://youtu.be/Met3NbxcZTU</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最近のほとんどのディストリビューションには、Python 3 がプリインストールされています。古い Linux ディストリビューションには Python2 が含まれているため、python3 をインストールする必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>SeedRecover を使用している場合、seedrecover にデフォルトの GUI ポップアップを使用する場合は、tkinter (python3-tk) もインストールする必要があります。(コマンド ラインの使用は、このパッケージがなくても機能します)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Linux の一部のディストリビューションではこれが Python3 にバンドルされていますが、Ubuntu などの他のディストリビューションでは、tkinter モジュールを手動でインストールする必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次のコマンドでこれをインストールできます。&nbsp;<code>sudo apt install python3-tk</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以下の「pip3」コマンドのいずれかが失敗した場合は、次のコマンドを使用して PIP をインストールする必要がある場合もあります。&nbsp;<code>sudo apt install python3-pip</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Python3-pip のインストール候補がないというメッセージが表示された場合は、次のコマンドで「universe」リポジトリを有効にする必要があります。&nbsp;<code>sudo add-apt-repository universe</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>その後、コマンドを再実行して、上記から python3-pip をインストールできます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="enabling-native-ripemd160-support">ネイティブ RIPEMD160 サポートの有効化</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>OpenSSL v3 (Late 2021) の時点で、ripemd160 はデフォルトで有効ではなくなり、ハッシュ関数の「レガシー」セットの一部になりました。Linux/MacOS 環境では、Python の hashlib モジュールは、ripemd160 の OpenSSL に依存しているため、これらの環境で完全なパフォーマンスが必要な場合は、OpenSSL 設定を変更してレガシー プロバイダーを有効にする必要がある場合があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2022 年 7 月の時点で、BTCRecover には RIPEMD160 の「純粋な Python」実装が含まれていますが、hashlib によるネイティブ実装と比較した場合、これは約 1/3 のパフォーマンスしか提供しません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この適用修正のビデオ デモは、こちらにあります:&nbsp;&nbsp;<a href="https://youtu.be/S3DWKp0i4i0">https://youtu.be/S3DWKp0i4i0</a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/S3DWKp0i4i0"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/S3DWKp0i4i0
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/master/docs/example_openssl.cnf">変更された構成ファイルの例は、https: //github.com/demining/CryptoDeepTools/blob/master/docs/example_openssl.cnf</a>にあります。&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/master/docs/example_openssl.cnf"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>詳細については、OpenSSL Github リポジトリの関連する問題を参照してください:&nbsp;&nbsp;<a href="https://github.com/openssl/openssl/issues/16994">https://github.com/openssl/openssl/issues/16994</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1265} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/11/image-191.png" alt="BTC 回復暗号ガイド" class="wp-image-1265"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="macos">マックOS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>MacOS に BTCRecover をインストールするビデオ デモ:&nbsp;&nbsp;<a href="https://youtu.be/Qzc3oHzbcAo">https://youtu.be/Qzc3oHzbcAo</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1）&nbsp;&nbsp;<a href="https://brew.sh/">brew.shの指示に従ってbrewをインストールします</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>インストール コマンドは次のとおりです。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>必ず指示に従い、brew をパスに追加してください…</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2)&nbsp;<a href="https://ofek.dev/coincurve/install/">コインカーブのビルド要件をインストールする</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>インストール コマンドは次のとおりです。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>brew install autoconf automake libffi libtool pkg-config python
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>グラフィカル インターフェイスを使用する場合は、指示に従って tkinter もインストールしてください。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Brew 経由で Python をインストールしたら、完全なバージョン番号を含むコマンドで Python と PIP の両方を実行する必要があります。(例: python3.9 と pip3.9)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="3-install-requirements-via-python-pip">3) Python Pip を介して要件をインストールする</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Python3 と PIP の両方がインストールされたら、次のコマンドを使用して、BTCRecover のすべての機能のすべての要件を自動的にインストールできます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>pip3 install -r requirements.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>上級ユーザーの場合は、試行している特定の回復に必要な追加パッケージのみをインストールすることを選択できます。どのウォレットがどのパッケージを必要とするかについての詳細は、このガイドの最後にあります。</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="4-install-pyopencl-for-gpu-acceleration">4) GPU アクセラレーション用に PyOpenCL をインストールする</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>GPU サポートには、上記のコマンドではカバーされない追加の OpenCL ライブラリをインストールする必要があります…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>詳細と手順については、こちらの GPU アクセラレーション ページを参照してください。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>GPU アクセラレーション</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="btcrecover-gpu-acceleration-guide">BTCRecover GPU アクセラレーション ガイド</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="performance-notes">パフォーマンスノート</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover には、1 つ以上のグラフィックス カードまたは専用のアクセラレータ カードを使用して検索パフォーマンスを向上させるためのサポートが含まれています。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これによるパフォーマンスの向上は、復元しようとしているウォレットのタイプ、CPU および GPU によって異なります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>比較のために、i7-8750 と NVidia 1660ti の CPU と GPU のパフォーマンスは、さまざまなウォレットで一般的に次のようになります。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>回復の種類</th><th>CPU パフォーマンス (kp/秒)</th><th>GPU パフォーマンス (kp/秒)</th><th>GPU 速度ブースト vs CPU</th></tr></thead><tbody><tr><td>ビットコイン コア (JTR カーネル)</td><td>0.07</td><td>6.75</td><td>96倍</td></tr><tr><td>ビットコイン コア (OpenCL_Brute)</td><td>0.07</td><td>0.95</td><td>14倍</td></tr><tr><td>Blockchain.com メイン パスワード</td><td>1</td><td>10</td><td>10倍</td></tr><tr><td>Blockchain.com の 2 番目のパスワード</td><td>0.39</td><td>15.5</td><td>40倍</td></tr><tr><td>dogechain.info</td><td>1.3</td><td>11.3</td><td>10倍</td></tr><tr><td>Electrum 2 ウォレットのパスワード</td><td>4.5</td><td>21</td><td>4.5倍</td></tr><tr><td>BIP39 パスフレーズ (または Electrum 'Extra Words'</td><td>2.3</td><td>10.4</td><td>4.5</td></tr><tr><td>BIP39 12 ワードシード</td><td>33</td><td>134</td><td>4.3倍</td></tr><tr><td>BIP39 12 ワードシード (Tokenlist)</td><td>33</td><td>130</td><td>4倍</td></tr><tr><td>BIP39 24 ワードシード</td><td>160</td><td>180</td><td>1.15倍</td></tr><tr><td>BIP39 24 ワード シード (Tokenlist)</td><td>140</td><td>160</td><td>1.15倍</td></tr><tr><td>エレクトラムシード</td><td>200</td><td>366</td><td>1.8倍</td></tr><tr><td>BIP38 暗号化キー</td><td>0.02</td><td>0.02</td><td>1x (ただし、複数の GPU で適切にスケーリング)</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>この時点で、GPU/OpenCL を有効にすると速度が向上すると単純に仮定しないでください。特に、非常にハイエンドの CPU とローエンドの GPU を使用している場合は… OpenCL/GPU を使用する場合と使用しない場合の両方でコマンドをテストし、–no-eta を使用します。および –パフォーマンスを評価するためのパフォーマンス引数</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>この劇的なパフォーマンスの違いは、特に BIP39 と Electrum シードの回復に関して、プロセスのさまざまな部分がさまざまな程度で CPU にバインドされていることが主な原因です。そのため、より多くの処理を OpenCL に移行し、より効率的なシード ジェネレーターを作成することが、今後の作業領域になります。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/Example_Multi-GPU_with_vastai/">また、この記事では、さまざまな GPU、特にマルチ GPU の状況に関するパフォーマンス情報を見つけることができます。</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="pyopencl-installation">PyOpenCL のインストール</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>GPU/OpenCL アクセラレーションは、OpenCL 1.2 用の PyOpenCL がインストールされているかどうかに依存します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この機能を使用するには、OpenCL をサポートするカードとドライバー (ほとんどの AMD と NVIDIA のカードとドライバーは既に Windows で OpenCL をサポートしています) が必要であり、以下で説明するように必要な Python ライブラリをインストールする必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>GPU アクセラレーションは MacOS でも動作するはずですが、必要な Python ライブラリをインストールする手順は現在、このチュートリアルには含まれていません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="pyopencl-installation-for-windows">Windows への PyOpenCL のインストール</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>これにより、OpenCL をインストールする前に、コンパイル済みの動作バージョンの numpy が手動でインストールされます。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>GPU 用のドライバー パッケージをインストールします。これなしでは何も機能しません。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>OpenCL 1.2 および Python 3 用の PyOpenCL の最新バージョン (インストールした Python のバージョンと一致する 32 ビット バージョンまたは 64 ビット バージョンのいずれか) をここからダウンロードします:&nbsp;&nbsp;<a href="http://www.lfd.uci.edu/~gohlke/pythonlibs/#pyopencl">http://www.lfd.uci.edu/~ gohlke/pythonlibs/#pyopencl</a>&nbsp;.&nbsp;最適な互換性を確保するために、必ず OpenCL 1.2&nbsp;<em>以降</em>&nbsp;のバージョンを選択してください (ファイル名に「cl12」が含まれていることを確認し、Python のバージョンに対応する数字を探します (例: Python 3.8 に一致する「38」)。 (OpenCL 2.0 バージョンはお使いのシステムで動作する可能性があるため、OpenCL 1.2 用の PyOpenCL が利用できない場合は、試してみてください) この記事の執筆時点では、OpenCL 1.2 および Python 3.9 の 32 ビット バージョンと 64 ビット バージョンは名前が付けられています。それぞれ：<code>pyopencl‑2021.1.4+cl12‑cp39‑cp39‑win_amd64.whl pyopencl‑2021.1.4+cl12‑cp39‑cp39‑win32.whl</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コマンド プロンプト ウィンドウを開き、手順 1 でダウンロードしたファイルをダウンロードした場所に移動し、次のように入力して PyOpenCL とその依存関係をインストールします (64 ビット環境で Python3.8 を想定)。<code>pip3 install "pyopencl-2021.1.4+cl12-cp39-cp39-win_amd64.whl</code></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="pyopencl-installation-for-linux">Linux用のPyOpenCLのインストール</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Ubuntu 20.04 での使用</strong>&nbsp;1. NVidia GPU の場合、システム用の Nvidia バイナリ ドライバをインストールします。（Ubuntuでは、これは簡単で、ここで説明されています：https://help.ubuntu.com/community/BinaryDriverHowto/Nvidia#NVIDIA_driver_from_the_Ubuntu_repositories 440バージョンのドライバーメタパックがテストされ、正常に動作します）–現在のAMDを持っていませんただし、AMD ドライバがインストールされている限り、これは正常に動作するはずです... 2. システムに pyOpenCL ライブラリをインストールします。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>    sudo apt install python3-pyopencl
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Linux 環境によっては、APT 経由で入手できる Python ライブラリが非常に古く、正しく動作しない場合があります。この場合、Pip 経由で PyOpenCL をインストールしてビルドする必要がある場合があります。(また、PyOpenCL の特定のバージョンがシステムでビルドされるかどうかは異なる場合があるため、古い PyOpenCL パッケージ バージョンを試すと役立つ場合があります。例: pyopencl==2019.1.1)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>これを超えると、最新の Ubuntu LTS リリース以外のディストリビューションに対して追加のサポートは提供されません。</strong>&nbsp;一般的に言えば、Hashcat の環境をインストールして構成するための手順は、環境をセットアップして動作させるために必要なものをカバーしています…</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="testing-your-system">システムのテスト</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>PyOpenCL のインストールが正しく機能しているかどうかを確認するには、実行する GPU アクセラレーション リカバリのタイプに関連する単体テストを実行できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>ビットコイン コア John-The-Ripper Kernel (JTR)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 -m btcrecover.test.test_passwords -v GPUTests
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>テストが失敗しないと仮定すると、&nbsp;<code>--enable-gpu</code>&nbsp;オプションをコマンド ラインに追加することで GPU サポートを有効にできます。検索パフォーマンスを向上させるために、特定の値とともに指定する必要があるその他の追加オプション、具体的には および があります&nbsp;<code>--global-ws</code>&nbsp;。&nbsp;<code>--local-ws</code>残念ながら、これらのオプションの正確な値は、以下に詳述するように、試行錯誤によってのみ決定できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Blockchain.com、Electrum Wallets &amp; BIP39 Passphrases (または Electrum 'Extra words') 経由の OpenCL_Brute Kernel (Bitcoin コアもサポートしますが、JTR より遅い)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>python3 -m btcrecover.test.test_passwords -v OpenCL_Tests
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>すべてのテストに合格した場合は、コマンド ライン引数に –enable-opencl を追加するだけです。OpenCL プラットフォームの選択とワーク グループ サイズのデフォルトは、適切な結果をもたらすはずです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>BIP39 または Electrum Seed Recovery</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 -m btcrecover.test.test_seeds -v OpenCL_Tests
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>すべてのテストに合格した場合は、コマンド ライン引数に –enable-opencl を追加するだけです。OpenCL プラットフォームの選択とワーク グループ サイズのデフォルトは、適切な結果をもたらすはずです。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="performance-tuning-background">パフォーマンス チューニング: バックグラウンド</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>OpenCL のパフォーマンス チューニングに関して理解しておくべき重要なことは、CPU が命令を処理する方法と GPU との間には根本的な違いがあるということです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>CPU はコマンドを非常に高速に処理できますが、基本的に CPU コアごとに一度に 1 つのタスクしか実行できません。一方、GPU は実際には同じタスクの実行が遅くなる可能性がありますが、違いは、CPU で発生するように次々と実行するのではなく、同時に 1000 のタスクのバッチを同時に実行できる可能性があることです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これが意味することは、GPU にロードする作業のバッチの大きさに応じて、GPU 処理のパフォーマンスに大きな違いが生じる可能性があるということです。（そして、潜在的なバッチサイズを半分だけ埋めるようなことをすると、パフォーマンスが半分になります）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>そのため、Global および Local work-size 引数を設定すると、JTR カーネルに大きな違いが生じる可能性がありますが、workgroup-size コマンドを使用すると、OpenCL_Brute カーネルを使用するときに大きな違いが生じる可能性があります (ただし、OpenCL_Brute カーネルのデフォルトは自動的に機能するはずです)。システムに最適に近いものを出力します)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これは、CPU 処理では問題にならないパフォーマンスのボトルネックが、GPU 処理を使用すると問題になることも意味します。(これがまさに、24 ワード シードのトークンリストが、BIP39 12 ワード シードを使用した標準的な回復ほどパフォーマンスが向上しない理由です)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これが、ある PC でチェックサム付きシード リストを作成し、–savevalidseeds、–savevalidseeds-filesize、–multi-file-seedlist、および –skip-worker-checksum 引数を使用して別の PC にロードすることに利点があることがわかる理由でもあります。 .</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="multi-gpu-systems">マルチ GPU システム</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>デフォルトでは、両方の OpenCL カーネルがシステムで利用可能なすべての GPU を使用しますが、それらの使用方法は少し異なります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>JohnTheRipper カーネル (–enable-gpu 引数が使用されている場合、Bitcoin Core によって使用されます)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>単一の CPU スレッドのみを使用し、すべての GPU を使用しますが、GPU はパフォーマンスに関して同一である必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>OpenCL_Brute カーネル (–enable-opencl 引数で有効化)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>GPU をラウンドロビンでスレッドに割り当てます。(たとえば、3 つの GPU と 3 つの CPU コアがある場合、GPU1-&gt;CPU1、GPU2-&gt;CPU2、GPU3-&gt;CPU3 などを割り当てることになります) GPU があります。(CPU よりも多くの GPU を搭載している仮想通貨採掘リグ以外のシステムは見たことがありませんが) BTCRecover はデフォルトで、論理 CPU コアと同じ数のスレッドを使用しますが、システムのコアが GPU よりも少ない場合、 –threads 引数を使用して、常に手動でスレッド数を指定できます。&nbsp;<strong><em>一般的に言えば、GPU あたり 2 スレッドが、おそらくパフォーマンスに関して最良の出発点になることをお勧めします…</em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>–opencl-devices 引数を使用して、使用する OpenCL デバイスを手動で指定することもできます。ここで GPU を 2 回リストすることもできます。これは、1 つの GPU が他の GPU の 2 倍強力である場合に役立つ可能性があるため、より大きなシェアを割り当てる必要があります。(例: GPU 0 0 1 を指定すると、GPU0 は GPU1 の 2 倍のスレッドに割り当てられます) 上記のように、これらの GPU はラウンド ロビン方式で割り当てられるため、基本的にはスレッドと同じ数のデバイスを指定できます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gpu-performance-tuning-for-bitcoin-core-and-derived-altcoin-wallets-with-the-jtr-kernel">JTR カーネルを使用したビットコイン コアおよび派生アルトコイン ウォレットの GPU パフォーマンス チューニング</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>これらのウォレットの良い出発点は次のとおりです。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/bitcoincore-wallet.dat --performance --enable-gpu --global-ws 4096 --local-ws 256
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>この&nbsp;<code>--performance</code>&nbsp;オプションは、&nbsp;&nbsp;<em>btcrecover</em>&nbsp;に、Ctrl-C が押されるまでパフォーマンスを測定するだけで、特定のパスワードをテストしないように指示します。パフォーマンス テストには、ウォレット ファイル (またはオプション) が必要です&nbsp;<code>--extract-data</code>&nbsp;。この初期テストからベースラインを取得したら、 と のさまざまな値を試して、&nbsp;<code>--global-ws</code>&nbsp;パフォーマンス&nbsp;<code>--local-ws</code>&nbsp;が向上するか低下するかを確認できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>と の適切な値を見つける&nbsp;<code>--global-ws</code>&nbsp;と&nbsp;<code>--local-ws</code>&nbsp;10 倍の改善が得られるため、通常は努力する価値があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>通常、テストするときは、これら 2 つの値を 2 の累乗で増減する必要があります。たとえば、一度に 128 または 256 ずつ増減する必要があります。<code>--global-ws</code>&nbsp;は常に で割り切れる必要がある&nbsp;ことに注意することが重要です&nbsp;<code>--local-ws</code>。そうでない場合、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;エラー メッセージで終了します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この手順は面倒ですが、より大きなトークンリストまたはパスワードリストを使用すると、大きな違いが生じる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="opencl-performance-tuning-for-other-wallets">他のウォレット向けの OpenCL パフォーマンス チューニング</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4 id="limiting-derivation-paths-searched-for-seed-based-wallets">シードベースのウォレットで検索される派生パスの制限</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>デフォルトでは、BTCRecover は特定の暗号通貨のすべての一般的な派生パスを自動的に検索します。(例: ビットコイン BIP44、49、84)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>CPU ベースのリカバリの場合、パフォーマンスが大幅に低下することはありませんが、CPU によっては、&nbsp;&nbsp;&nbsp;OpenCL のパフォーマンスが<strong>半分になる可能性があります。</strong>そのため、検索している派生パスがわかっている場合は、–bip32-path コマンドを使用して手動で指定する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="address-generation-limit-for-seed-based-wallets">シードベースのウォレットのアドレス生成制限</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ビットコインのような暗号通貨は、通常、「受け取る」ことを選択するたびに新しいアドレスを生成します。アドレス生成制限 (–addr-limit 引数) は、BTCRecover が生成し、シードごとに検索するアドレスの数を指定します。（これが、ウォレットから可能な限り早いアドレスを使用したい理由です）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>CPU ベースのリカバリの場合、アドレス生成制限を 10 程度に設定してもパフォーマンスに大きな影響はありませんが、OpenCL ベースのリカバリでは、アドレス生成制限を 10 に設定すると検索パフォーマンスが半分になる可能性があり&nbsp;&nbsp;ます<strong>。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>とはいえ、イーサリアムやリップル ウォレットなどで復元を行う場合、これらのアカウント ベースの暗号は固定の受信アドレスを使用する傾向があるため、通常はアドレス生成制限を 1 のままにしておくことができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>また、住所データベースを使用している場合は、通常、住所生成制限を 1 のままにしておくことができることにも注意してください。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="work-group-size">作業グループのサイズ</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>–opencl-info コマンドを使用すると、OpenCL デバイスとそれに対応する最大ワークグループ サイズのリストが表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>その後、–opencl-workgroup-size コマンドを使用して、ワークグループ サイズを手動で設定してみてください。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>パスワード回復の場合:</strong>&nbsp;ワークグループ コマンドを最大ワークグループ サイズの正確な倍数に設定する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>シード リカバリの場合</strong>&nbsp;シード リカバリが自動的にワークグループ サイズをはるかに大きな値に設定することに気付くでしょう。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これは、生成されるシードの大部分がチェックサムのみであり、完全にハッシュされることはないためです。生成されたシードとハッシュされたシードの比率は、ウォレットの種類とシードの長さによって異なります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一般的に言えば、 * BIP39 12 Word: 16:1 * BIP39 18 Word: 64:1 * BIP39 24 Word: 256:1 * Electrum : 125:1</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これが意味することは、GPU の最大ワークグループ サイズを満たすために、seedgenerator は最大ワークグループ サイズの何倍も大きい可能なシードのチャンクを渡す必要があるということです。(例: ワーク グループのサイズが 1024 の場合、BIP39 の 24 ワードのシードには 262,144 の潜在的なシードが必要になります)</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="5-testing-your-installation">5) インストールのテスト</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover をダウンロードして解凍し、Python と必要なすべてのライブラリをインストールしたら、次のコマンドでプログラムをテストできます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 run-all-tests.py -vv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このコマンドの実行には数分かかりますが、エラーなしで完了するはずです。これは、システムが BTCRecover のすべての機能を使用する準備ができていることを示しています。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="wallet-python-package-requirements">ウォレット Python パッケージの要件</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>すべてのウォレット タイプのすべての要件をインストールする場合は、次のコマンドを使用するだけです。&nbsp;<code>pip3 install -r requirements-full.txt</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以下のリストでウォレットのタイプを見つけ、ウォレットの横にリストされているセクションの指示に従ってください。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>ビットコイン コア – オプション:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit Classic – 推奨:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit HD – オプション:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum (1.x または 2.x) – 推奨:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum 2.8+ 完全に暗号化されたウォレット –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">coincurve</a>、オプション:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-39 ビットコイン パスフレーズ (TREZOR など) –&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">コインカーブ</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-39 Ethereum パスフレーズ (TREZOR など) –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a>&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">コインカーブ</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>OS X 用のハイブ –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#google-protocol-buffers">Google protobuf</a>、オプション:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>mSIGNA (CoinVault) – 推奨:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Blockchain.info – 推奨:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android/BlackBerry バックアップ用のビットコイン ウォレット – 推奨:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android/BlackBerry 支出 PIN 用のビットコイン ウォレット –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#scrypt">scrypt</a>、&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#google-protocol-buffers">Google protobuf</a>、オプション:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android バックアップ用の KnC ウォレット – 推奨:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bither –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">coincurve</a>、オプション:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Litecoin-Qt – オプション:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum-LTC – 推奨:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android 用 Litecoin ウォレット – 推奨:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Dogecoin Core – オプション:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiDoge – 推奨:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android 用 Dogecoin Wallet – 推奨:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SLIP39 ウォレット:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#shamir-mnemonic">shamir-mnemonic</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Py_Crypto_HD_Wallet ベースの BIP39 ウォレット:  <a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#py_crypto_hd_wallet">py_crypto_hd_wallet</a><!-- wp:list -->
<ul><!-- wp:list-item -->
<li>雪崩</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コスモス（アトム）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>水玉模様</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>秘密のネットワーク</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ソラナ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ステラ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>論文</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>トロン</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Helium BIP39 ウォレット:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pynacl">pynacl</a>&nbsp;および&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#bitstring">bitstring</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Eth キーストア ファイル:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#eth-keyfile">eth-keyfile</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Groestlecoin BIP39 ウォレット:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#groestlcoin_hash">groestlcoin_hash</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP38 暗号化秘密鍵:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#ecdsa">ecdsa</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 id="pycryptodome">PyCryptoDome</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Ethereum ウォレットを除いて、PyCryptoDome はどのウォレットにも厳密に必要というわけではありませんが、上記のリストで推奨されているタグを付けたウォレットでは 20 倍の速度向上を提供します。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="py_crypto_hd_wallet">Py_Crypto_HD_Wallet</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>このモジュールは、さまざまな種類のウォレットに必要です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Windows ユーザーの場合、モジュールを正常にインストールするには、Microsoft Visual C++ ビルド ツールもインストールする必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/0LMUf0R9Pi4">これについて説明したビデオ チュートリアルは、https: //youtu.be/0LMUf0R9Pi4</a>にあります。&nbsp;<a href="https://youtu.be/0LMUf0R9Pi4"></a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/0LMUf0R9Pi4"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/0LMUf0R9Pi4
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>MacOS および Linux ユーザーの場合、プラットフォームのこのページのインストール手順に従えば、モジュールは正常にビルド/インストールされます。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="running-btcrecoverpy"><em>btcrecover.py</em>の実行&nbsp;<em></em></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>このチュートリアルはかなり長いので、全部読む必要はありません。ここから始めましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>すでにファイルがある場合は&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;、ステップ 6 に進んでください。そうでない場合、および覚えている小さな断片のさまざまな組み合わせからパスワードを作成するためのサポートが必要な場合は、ステップ 4 から始めてください。パスワードにタイプミスがあると思われる場合、またはほとんどの場合、パスワード全体が何であるかを知っており、パスワードのさまざまなバリエーションを試すだけで済みます。手順 5 をお読みください。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>トークン ファイルのセクション (少なくとも最初の部分) を読んでください。ここでは、&nbsp;&nbsp;<em>btcrecover が</em>&nbsp;覚えている小さな断片から覚えていないパスワード全体を構築する方法について説明しています。完了すると、&nbsp;<code>tokens.txt</code>&nbsp;後で必要になるファイルの作成方法がわかります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>btcrecover が</em> パスワード全体にバリエーションを作成して、さまざまなパスワード推測を作成する方法について説明しているタイプミスのセクションを読んでください 。完了すると、テストするバリエーションを作成するコマンド ライン オプションのリストが表示されます。<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>上記の手順 4 をスキップした場合は、&nbsp;代わりに<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#token-Lists-and-password-or-seed-lists">パスワードリストの</a>簡単な&nbsp;セクションをお読みください。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#running-btcrecover"><em>btcrecover</em></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#running-btcrecover">の実行&nbsp;<em></em></a>セクションを読んで、  これらの部分をまとめる方法と、  コマンド プロンプト ウィンドウで <em>btcrecoverを実行する方法を確認してください。</em><!-- wp:list -->
<ul><!-- wp:list-item -->
<li>(オプション)&nbsp;テスト&nbsp;するパスワードを表示するには、<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#testing-your-config">「構成のテスト」セクションを読んでください。</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>(オプション) 時間がかかる多数の組み合わせをテストする場合は、&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#autosave">自動保存</a>&nbsp;機能を使用して進行状況が失われないようにします。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>(オプションですが、強くお勧めします) パスワードが見つかったら、寄付アドレスに巨額のビットコインを寄付してください。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="bip3944-wallets-with-addressdb">AddressDB を使用した BIP39/44 ウォレット</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BIP39/44 ウォレットからパスフレーズを回復する場合は、探しているアドレスを使用しても、または知らなくても実行できます。詳細については、アドレス データベースを使用した回復を参照してください。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="recovery-with-an-address-database">アドレス データベースを使用した復旧</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="background">バックグラウンド</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BIP39/44 ウォレットを回復しようとするとき、&nbsp;&nbsp;<em>seedrecover.py</em>&nbsp;と&nbsp;<em>btcrecover.py は</em>&nbsp;、入力したシードに基づいて異なる推測を試みます。どのシード推測が正しいかを判断する方法が必要です。通常、各シード推測を使用してマスター公開鍵 ( mpk&nbsp;&nbsp;<em>)</em>を作成し、入力した mpk と比較するか、ビットコイン アドレスを作成して入力したアドレスと比較します。mpk もアドレスもない場合でも、&nbsp;&nbsp;<em>seedrecover.py を</em>使用することは可能です&nbsp;が、より複雑で時間がかかります。&nbsp;<strong>このプロセスの主な時間コストは、ブロックチェーンをダウンロードして AddressDB を生成することです。プロセスの実際のチェック部分は、単一のアドレスに対してテストされているか、600,000 個のアドレスを含む addressDB に対してテストされているかに関係なく、ほぼ同じ速度で実行されます…したがって、ウォレットが使用しているアドレスについて少しでも確信が持てない場合は、AddressDB を使用する価値があります。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これは、上記のようにアドレスを生成し、ブロックチェーン全体で生成された各アドレスを探すことによって機能します。これを行うには、まずブロックチェーンに基づいてアドレスのデータベースを作成する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>AddressDB を生成するには、生のブロックチェーン データを直接解析する方法と、アドレスのリストを含むファイルを処理する方法の 2 つがあります。(このアドレスのリストには、複数のコイン タイプのアドレスを含む、BTCRecover がサポートする任意のアドレス タイプを含めることができます)</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="pre-made-addressdb-files">事前に作成された AddressDB ファイル</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注: AddressDB ファイルは、BTCRecover の Python2 ブランチと Python3 ブランチの間で互換性がありません。正しいものをダウンロードしてください。(この Github の master ブランチはすべて Python3 になりました…)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>サポートされているいくつかのチェーンの AddressDatabases を作成してアップロードしました。定期的に更新します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptoguide.tips/btcrecover-addressdbs/">ここから私のウェブサイトからダウンロードできます…</a></strong>&nbsp;&nbsp;(その後、それらを解凍し、–addressdb を使用してフル パスとファイル名を含め、seedrecover.py または btcrecover.py の場所を指定します)</p>
<!-- /wp:paragraph -->

<!-- wp:image {"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://cryptoguide.tips/btcrecover-addressdbs/AddressDBs%20include%20transactions%20up%20until%20approximately%20the%20file%20modified%20date.txt"><img src="https://cryptoguide.tips/icons/text.gif" alt="[TXT]"/></a></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 id="parameters-to-manage-addressdb-size">AddressDB サイズを管理するパラメータ</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>dblength</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このツールは、事前に最大サイズを指定する必要があるデータベース ファイルを作成します。このアドレスの最大数は 2 のべき乗として与えられます。例: –dblength 30 は、約 2^30 のアドレス用のスペースを作ります。これは 10 億未満です... 基本的に、ブロックチェーンにファイルのスペースよりも多くのアドレスがある場合、プログラムクラッシュするだけなので、再実行して –dblength を 1 増やす必要があるかもしれません。これはデフォルトで 30 に設定されており、これは 2018 年 11 月に ~8GB のファイルを作成し、ビットコイン ブロックチェーンには十分です&nbsp;<strong>。問題は、AddressDB ファイルのサイズは、使用されるアドレスの数ではなく、収容できるアドレスの最大数に依存することです。</strong>&nbsp;これが意味することは、Vertcoin のような小さなブロックチェーン用の addressDB を生成している場合、スペースを節約するために、より小さい dblength を指定することで解決できるということです。デフォルトのままにしておくと、最大 30 MB のファイルが機能したときに 8 GB のファイルになってしまいます。&nbsp;<strong>HDDの空き容量が十分にあれば問題ありませんが、</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2021 年 1 月時点でのブロックチェーン、AddressDB のサイズ、および最適なパラメーターの大まかなガイドは次のとおりです。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>コイン</th><th>ブロックチェーンのサイズ</th><th>AddressDB サイズ</th><th>必要な DBLength</th></tr></thead><tbody><tr><td>ビットコイン</td><td>324GB</td><td>16ギガバイト</td><td>31</td></tr><tr><td>ビットコインキャッシュ</td><td>155GB</td><td>4ギガバイト</td><td>29</td></tr><tr><td>ライトコイン</td><td>90GB</td><td>2GB</td><td>28</td></tr><tr><td>バートコイン</td><td>5GB</td><td>32MB</td><td>22</td></tr><tr><td>モナコイン</td><td>2.5GB</td><td>32MB</td><td>22</td></tr><tr><td>イーサリアム</td><td>該当なし（最大 1 億 2000 万のアドレスを含む BigQuery の AddressList）</td><td>4ギガバイト</td><td>29</td></tr><tr><td>ドージコイン</td><td>該当なし（最大 6,000 万のアドレスを含む BigQuery のアドレスリスト）</td><td>1GB</td><td>27</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><em>疑わしい場合は、完全なブロックチェーンをダウンロードして、その内容を解析してください…デフォルトで問題ありません…</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>AddressDB 作成の日付範囲の制限</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>特定の日付の間に発生した取引の住所のみを含む住所データベースを作成することができます。これは、AddressDB ファイルに必要な追加スペースが少なくて済み、RAM の使用量も大幅に減るという点で便利です。(例: ハードウェア ウォレットを注文した後に使用されたアドレスのみを考慮するように選択できます) これは、YYYY-MM-DD の形式の日付で、–blocks-startdate BLOCKS_STARTDATE および –blocks-enddate BLOCKS_ENDDATE 引数を介して行われます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>AddressDB の作成で X 個のブロック ファイルをスキップする</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>特定のブロックファイルで処理を開始するように AddressDB 作成スクリプトに指示することもできます。これは、より大きなブロックチェーンの処理を高速化するのに役立ちます。(例: 2018 年にビットコインに使用されたアドレスのみが必要な場合) これは –first-block-file FIRST_BLOCK_FILE を介して行われます。FIRST_BLOCK_FILE はブロック ファイルの番号です。&nbsp;<strong>–blocks-startdate を使用すると、開始日以降にブロックのカウントを開始するように指示しても、この機能は警告しません。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="creating-an-addressdb-from-blockchain-data">ブロックチェーン データからの AddressDB の作成</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>次の生のブロックチェーン データを解析することにより、addressDB を生成できます: * ビットコイン * ビットコイン キャッシュ * ライトコイン * バートコイン * モナコイン</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>また、-dbyolo フラグを介して強制しようとすることで、他の「ビットコインのような」ブロックチェーンと連携することもあります。(処理中に見つかったアドレスの数が増えていれば、ブロックチェーンが正常に解析されていることがわかります)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;* Dogecoin * Verge * Zcash および Zencash * Monero * Ethereum で動作<strong>しない</strong>ことをテストして確認しました&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これらのブロックチェーンでは、(Google BigQuery などを介して) アドレスのリストを取得し、このリストから addressDB を生成する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>アルトコイン ブロックチェーン</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このツールは、上記のブロックチェーンで動作するようにテストされています。デフォルトでは、デフォルトの Bitcoin インストール ディレクトリをスキャンして使用します。Bitcoin を別の場所にインストールした場合、または別のブロックチェーンから AddressDB を作成したい場合は、–datadir 引数を使用してその場所を手動で指定する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>どのブロックチェーンを使用したいかという問題は、あなたの個人的な状況に帰着します。とはいえ、ある時点で Litecoin または Vertcoin を保管していたことがわかっている BIP39 ウォレットをお持ちの場合は、完全な BTC ブロックチェーンをダウンロードするよりも、これらのチェーンのいずれかをダウンロードして使用することから始めることをお勧めします。BIP39/44 ウォレットはすべての通貨に同じシードを使用するため、シードの回復にどちらを使用しても問題ありません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>再現する例</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>AddressDB に対していくつかのテストを実行する場合は、&nbsp;&nbsp;このプロジェクトの<a href="https://github.com/demining/CryptoDeepTools/tree/master/btcrecover/test/test-addressdbs">./btcrecover/test/test-addressdbsフォルダーにあるテスト用の DB があります。</a>基本的に、各ブロックからの 24 時間分のアドレスしか含まれていないため、サイズは小さいです。(それらは –blocks-startdate および enddate 引数で作成されました)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次のコマンドを使用して、これらのデータベースのいずれかを使用してテストを実行できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 seedrecover.py --no-dupchecks --addr-limit 2 --bip32-path "m/44'/28'/1'/0" --big-typos 1 --addressdb ./btcrecover/test/test-addressdbs/addresses-VTC-Test.db --wallet-type bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>そして、最初の単語の代わりに数字が 1 の種…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>1 entire sniff tired miracle solve shadow scatter hello never tank side sight isolate sister uniform advice pen praise soap lizard festival connect baby</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/master/btcrecover/test/test_seeds.py">test_seeds.py</a>でカバーされている単体テストで小さな AddressDB を使用するテストの例をさらに見つけることができます&nbsp;&nbsp;。「test_addressdb_」で始まるメソッドを検索するだけで、パラメーターに addressDB の制限、テスト フレーズ、派生パス、使用される AddressDB が一覧表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>ブロックチェーン データから AddressDb を作成する手順:</strong>&nbsp;&nbsp;1. 処理する完全なブロックチェーンに十分なスペースと、最終的に得られる AddressDB サイズの 2 倍に等しい RAM を備えたコンピューターを使用する必要があります (これは非常に寛大な見積もりです)。 、おそらく少なくても問題ありませんが、少なくとも作成したい AddressDB と同じくらいの量が必要です)。64 ビット バージョンの Python がインストールされている必要があります。(他の小さなブロックチェーンでは必要なスペースと RAM が大幅に少なくなります)</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><a href="https://bitcoincore.org/">Bitcoin Core</a>、&nbsp;&nbsp;<a href="https://bitcoinabc.org/">Bitcoin ABC</a>、&nbsp;&nbsp;<a href="https://litecoin.org/">Litecoin Core</a>、&nbsp;&nbsp;<a href="https://vertcoin.org/download-wallet/">Vertcoin</a>、&nbsp;&nbsp;<a href="https://monacoin.org/">Monacoin Core</a>など、選択したブロックチェーン用のフルノード クライアントをインストールします&nbsp;。(Electrum などのライトクライアントはこれには対応していません…)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>フルノード クライアントを起動し、完全に同期させます。インターネット接続とコンピューターによっては、ノードを完全に同期するのに 1 日以上かかる場合があります。<code>bitcoin-qt</code>&nbsp;オプションで(または&nbsp;<code>bitcoind</code>)&nbsp;を開始する&nbsp;<code>-dbcache #</code>&nbsp;と役立ちます。これは、&nbsp;<code>#</code>&nbsp;データベース キャッシュに使用する RAM の量 (MB 単位) です。コンピューターに少なくとも 8 GB の RAM が搭載されている場合は、最大で&nbsp;<code>4000</code>&nbsp;MB を使用すると&nbsp;<code>-dbcache</code>&nbsp;速度が向上します。SSD を搭載したコンピューターに Bitcoin をインストールすることも役に立ちます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>フルノード クライアントが同期されたら、フルノード クライアント ソフトウェアを閉じます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>(OS X では、&nbsp;<code>create-address-db.py</code>&nbsp;スクリプト ファイルの名前を に&nbsp;変更します。)&nbsp;スクリプト ( と同じフォルダー内&nbsp;)<code>create-address-db.command</code>をダブルクリックして、&nbsp;完全に同期されたブロックチェーンを使用して住所データベースを構築します (&nbsp;名前と&nbsp;同じディレクトリに保存されます&nbsp;)。 .&nbsp;このプロセスには約 1 時間かかり、RAM とドライブ容量の両方で約 4 GB を使用します。<code>create-address-db.py</code><code>seedrecover.py</code><code>create-address-db.py</code><code>addresses.db</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Creating_and_Using_AddressDB/#running-seedrecoverpy"><em>「seedrecover.py</em></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Creating_and_Using_AddressDB/#running-seedrecoverpy">の実行&nbsp;<em></em></a>」セクションに記載されている手順に従います&nbsp;&nbsp;。ただし、手順 4 でアドレス入力ウィンドウが表示されたら、[ ] をクリックします&nbsp;<code>Cancel</code>。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>次のステップでは、アドレス生成制限を選択する必要があります。これは、最初に使用したアドレスよりも前に、ウォレットの最初にあると思われる未使用のアドレスの数です。ウォレットの最初のアドレスを使用したことが確かな場合は、&nbsp;<code>1</code>&nbsp;ここで使用できますが、確信が持てない場合は、より高い見積もりを選択する必要があります (ただし、&nbsp;&nbsp;<em>seedrecover.py</em>&nbsp;の実行には時間がかかる場合があります)。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>AddressDB を使用して実行すると、住所データベースを使用して実行している間、AddressDB ファイルのサイズとほぼ同じ量の RAM が使用されることに注意してください。(例: 完全な Bitcoin AddressDB には、2019 年 11 月の時点で約 8.5 GB の RAM が必要です)</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="creating-an-addressdb-from-an-address-list">アドレス一覧からの AddressDB の作成</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>addressDB を作成する別の方法は、アドレスのリストを使用することです。(例: Google BigQuery などからのすべての Eth アドレスのリスト)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>–inputlist パラメーターを使用して入力リストを指定し、使用する dblength を指定するだけです。(それ以外の場合はデフォルトで 30 になり、8 GB のファイルが作成されます) bigquery から Google Cloud Storage にデータをエクスポートするときに自動的に作成されるファイルのリストを自動的に含めることができるように、-multifileinputlist も必要になる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>複数のリストからアドレスを結合したり、アドレスのリストを既存のブロックチェーンで生成された addressDB に追加したりする場合は、-update 引数を使用してこれを行うことができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>約 1,000 万のアドレスを含むファイルを追加するには、約 1 分かかります… (BigQuery Eth データのパフォーマンスに基づく)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="generating-address-lists-from-google-bigquery">Google BigQuery からのアドレス リストの生成</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em><strong>注:</strong>&nbsp;&nbsp;Google BigQuery のデータは 1 ～ 2 か月ごとに更新されますが、更新頻度がそれより低い場合もあります。ウォレットに… (例: 「最終更新日」より前に少なくとも 1 回の取引を行ったこと)</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>便利な Google BigQuery クエリ</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:05c3cbf256dd43a898f5168b94bc66cc">すべての BTC アドレス</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:c6370cf863224be1942ecfdf03e0f0ca">すべての Eth アドレス</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:c130730990e94212bf20b3dea5c4c815">すべての総督住所</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:1cb1a218b17d4498bb3d9103e5b2fb3a">すべての BCH アドレス</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:13e998b9bf864df8b7c0772f4913b28d">すべての LTC アドレス</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="generating-address-lists-using-ethereum-etl">Ethereum-ETL を使用したアドレス リストの生成</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>動作確認済み: * 次のようにインストールされた Geth ノードを備えた Binance スマート チェーン:&nbsp;&nbsp;<a href="https://docs.bnbchain.org/docs/validator/fullnode">https://docs.bnbchain.org/docs/validator/fullnode</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>EVM タイプのチェーン (例: Binance Smart Chain) の場合、別のオプションは Ethereum-ETL ツールを使用することです。これにより、完全なノード (実行中の Geth または Parity、またはこれらのフォーク) に対してクエリを実行し、トランザクションを表す人間が判読できる CSV データを取得できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Geth-Like ノードを実行したら、次のようなコマンドで ETL データを取得できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>ethereumetl export_blocks_and_transactions --start-block STARTBLOCKNUMBER --end-block ENDBLOCKNUMBER --provider-uri http://FULLNODEIP:8545 --blocks-output LOCAL_BLOCKS_CSV_FILE --transactions-output LOCAL_TRANSACTIONS_CSV_FILE</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>トランザクションをエクスポートしたら、&nbsp;&nbsp;このリポジトリ内のフォルダー<code>addrListsFromETLTransactions.py</code>&nbsp;内のファイルを&nbsp;使用して、アドレスのリストを含むファイルを作成できます。<code>utilities</code>これらのアドレス リストを使用して、前に説明したのと同じプロセスを使用して addressDB を作成できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このアプローチで理解しておくべき重要なことは、保存/実行するために数 TB 相当のディスク容量と、完全な Ethereum ETL 出力用に数 TB 相当の追加容量が必要になるということです。(したがって、おそらく約 10 TB のスペースが必要になります…)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="checkingvalidating-addressdbs">AddressDB のチェック/検証</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>check-address-db.py ファイルを使用して、アドレスリスト ファイルに特定のアドレスが含まれているかどうかをテストできます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>たとえば、次のコマンドを使用して、Dogecoin AddressDB (上記でダウンロード可能) にいくつかの特定のアドレスが含まれていることを検証できます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>python3 check-address-db.py --dbfilename "E:\CryptoGuide\OneDrive\AddressDBs (Mega)\addresses-DOGE.db" --checkaddresses DMQ6uuLAtNoe5y6DCpxk2Hy83nYSPDwb5T DFgLZmxFnzv2wR4GAGS3GeHvoEeSkz9ubU DKTHYZwd81xT7qJF33YRi7ftDkvouGdxxN
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>これにより、次の出力が生成されます</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>Starting CheckAddressDB 1.9.0-CryptoGuide
Loading address database ...
Loaded 60750752 addresses from database ...
DMQ6uuLAtNoe5y6DCpxk2Hy83nYSPDwb5T Found!
DFgLZmxFnzv2wR4GAGS3GeHvoEeSkz9ubU Found!
DKTHYZwd81xT7qJF33YRi7ftDkvouGdxxN Found!
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>チェックリスト ファイル</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>BTCRecover リポジトリには、特定の時間間隔で最初にシードされたアドレスが addressDB に含まれていることを確認するために使用できる、いくつかの基本的なアドレス リストがバンドルされています。これらのアドレスはブロックチェーンからランダムに選択され、約 6 か月間隔で配置されています。(そのため、特定の addressDB が必要な日付をほぼカバーするようにするために使用できます)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>たとえば、コマンドを使用して、Dogecoin AddressDB (上記でダウンロード可能) に 2021 年 2 月までのアドレスが含まれていることを検証できます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 check-address-db.py --dbfilename addresses-DOGE.db --checkaddresslist ./addressdb-checklists/DOGE.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>これにより、次の出力が生成されます</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>Starting CheckAddressDB 1.9.0-CryptoGuide
Loading address database ...
Loaded 60750752 addresses from database ...
Loading:  ./addressdb-checklists/DOGE.txt
DMQ6uuLAtNoe5y6DCpxk2Hy83nYSPDwb5T Found! First Seen 2021-01-31
DFgLZmxFnzv2wR4GAGS3GeHvoEeSkz9ubU Found! First seen 2020-06-29
DKTHYZwd81xT7qJF33YRi7ftDkvouGdxxN Found! First seen 2019-12-30
DPPg5BVqn7Ck5YVf6ei7NbXGVPDSzXnCBL Found! First seen 2019-05-17
DBbTFW9PZJj9EsXu5Ji59Tp6ZdKNrTZmWq Found! First seen 2018-12-05
DFJRDVzjk7NPbApWsLDreML7RDawp8UmoF Found! First seen 2018-05-16
D9dWXJjYb4HDrXpdef234GHDDggrnGsfxm Found! First seen 2017-11-05
D6A894uLhQjwSRpEroPMop4MPpUL4BZZHc Found! First seen 2017-05-19
DGVxem7KdNBCJWygpRcypS5pMJgJVRZEXD Found! First seen 2016-12-25
DMPHyer3WdKrSmwmFarXtXCxbbp4BMwo9J Found! First seen 2016-05-22
DRusoAd1Q9PJq3KpkhXjpZAoCqdQzGS6AH Found! First seen 2015-12-29
D6sxvQRSriU4pkozdYxDVRKRmoRYCVmqKv Found! First seen 2015-05-10
DNULsd2gbojENHtRRx45PUWvPgkrbL2vjE Found! First seen 2014-12-15
D5mrYgNeLwVXFyy9t9NhBpTqVaa58gUYAC Found! First seen 2014-04-29
DLAznsPDLDRgsVcTFWRMYMG5uH6GddDtv8 Found! First seen 2013-12-07
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="token-lists-and-password-or-seed-lists">トークン リストとパスワードまたはシード リスト</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>パスワードとシードのどちらの回復方法でも、トークン ファイルとパスワード/シード リスト ファイルの両方を使用できます。パスワードの回復には、これらのうち少なくとも 1 つが必要です。(また、いくつかのタイプのシード回復に必要になる場合があります。たとえば、シード フレーズのスクランブル解除)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>また、パスワード/シード リスト ファイルを使用すると、パスワードを生成するタスクとそれらをテストするタスクを 2 つの別々のステップに分割することができ、ユーザーは PYPY がパスワード生成に提供する高速化 (テストの高速化) を利用できます。また、多数のパスフレーズを複数のサーバーでテストするタスクを分割することも簡単になります。(または、より強力な/高価なシステムでテストするタスクとは別に、パスワードリストを作成するシングルスレッド操作を実行します)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>パスワードリストファイルとトークンファイルの両方に、以下の独自のドキュメントがあります…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/">パスワード/シード リスト ファイル</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/tokenlist_file/">トークン リスト ファイル</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="typos">タイプミス</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover は、</em>&nbsp;さまざまなバリエーションのパスワードを生成して、パスワードを入力したり書き留めたりするときにうっかりしてしまったタイプミスや間違いを見つけることができます。<em>この機能は、 btcrecover を</em>実行するときに 1 つ以上のコマンド ライン オプションを含めることで有効になります&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>追加できるコマンド ライン オプションの具体的な例が必要な場合は、&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Typos_Quick_Start_Guide/">Typos クイック スタート ガイド を</a>参照してください。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>--typos #</code>&nbsp;コマンド ライン オプション (&nbsp;<code>#</code>&nbsp;タイプミスの数に置き換えられます)&nbsp;を使用して&nbsp;、&nbsp;<em>btcrecover</em>&nbsp;に各パスワード (トークン ファイルから生成されたもの、またはパスワード リストから取得されたもの) に追加するタイプミスの数を指定します。上記）。また、生成したいタイプミスのタイプを指定する必要があり、可能なすべての組み合わせを調べます (タイプミスが存在しない可能性を含む)。以下は、タイプミスの基本的なタイプと、それぞれを有効にするコマンドライン オプションの概要です。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>--typos-capslock</code>&nbsp;– Caps Lock をオンにしてパスワード全体を試す</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-swap</code>&nbsp;– 2 つの隣接する文字を入れ替えます</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-repeat</code>&nbsp;– 文字を繰り返す (倍増する)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-delete</code>&nbsp;– 文字を削除します</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-case</code>&nbsp;– 単一文字の大文字/小文字を変更します</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>たとえば、コマンド ラインでオプションを指定すると&nbsp;、&nbsp;&nbsp;(タイプミスなし)、&nbsp;&nbsp;&nbsp;(タイプミス 1 つ: Caps Lock)、&nbsp;&nbsp;&nbsp;(タイプミス 2 つ: 両方の繰り返し)、および&nbsp;&nbsp;(タイプミス 2 つ: 1 つ<code>--typos 2 --typos-capslock --typos-repeat</code>&nbsp;) など、タイプミスが 2 つまでのすべての組み合わせが試行されます。&nbsp;各タイプ）を試してみます。コマンド ラインに多くのタイプミスを追加すると、組み合わせの数が大幅に増加する可能性があり、数を増やすと&nbsp;&nbsp;さらに劇的になる可能性があるため、トークン ファイルやパスワード リストが小さい場合を除き、この機能を使用するときは慎重に行うことをお勧めします。<code>Cairo</code><code>cAIRO</code><code>CCairoo</code><code>cAIROO</code><code>--typos</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>もう少し説明が必要な追加の種類のタイプミスを次に示します。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>--typos-closecase</code>&nbsp;– と同様です&nbsp;<code>--typos-case</code>が、その文字が大文字と小文字が異なる別の文字の隣にある場合、または最初または最後にある場合にのみ、その文字の大文字と小文字を変更しようとします。これにより、試行する組み合わせが少なくなるため、実行が速くなり、誰かが Shift キーを押している時間が長すぎる、または短すぎる可能性が高いインスタンスを引き続きキャッチします。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-replace s</code>&nbsp;– これにより、各文字が指定された文字列 (例では an&nbsp;&nbsp;<code>s</code>) に置き換えられます。文字列は、単一の文字、またはより長い文字列 (この場合、各単一文字が文字列全体に置き換えられます)、または 1 つ以上の拡張ワイルドカードを含む文字列にすることができ&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#expanding-wildcards">ます</a>&nbsp;。たとえば、&nbsp;<code>--typos 1 --typos-replace %a</code>&nbsp;各文字を (一度に 1 つずつ) 小文字に置き換え、考えられるすべての組み合わせを試してみます。ワイルドカードを使用すると、組み合わせの総数が大幅に増加する可能性があります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-insert s</code>&nbsp;– と同様です&nbsp;<code>--typos-replace</code>が、文字を置換する代わりに、文字列の単一のコピー (またはワイルドカード置換) を文字の各ペアの間、先頭と末尾に挿入しようとします。 が 1 より大きい場合でも&nbsp;<code>--typos</code>&nbsp;、&nbsp;<code>--typos-insert</code>&nbsp;通常、同じ位置に文字列の複数のコピーを挿入しようとはしません。たとえば、&nbsp;<code>--typos 2 --typos-insert Z</code>&nbsp;指定すると、&nbsp;<code>CaiZro</code>&nbsp;と など&nbsp;の推測が<code>CZairoZ</code>&nbsp;試みられますが、そうでは&nbsp;<code>CaiZZro</code>&nbsp;ありません。<code>--max-adjacent-inserts #</code>&nbsp;これは、 1 より大きい数値を使用して変更できます&nbsp;。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4 id="typos-map">タイプミスマップ</h4>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>--typos-map typos.txt</code>&nbsp;– これは比較的複雑ですが、柔軟なタイプのタイプミスです。<code>typos.txt</code>詳細を綴る別のファイル (この例では という名前) を使用して、特定の特定の文字を特定の他の特定の文字に置き換えようとします&nbsp;。<code>. ,/; ; [‘/.&nbsp;</code>たとえば、句読点をよく間違えることがわかっている場合は、&nbsp;次の&nbsp;2行を含む<em>タイポス</em>マップ ファイルを作成できます&nbsp;。&nbsp;同じ行にある場合、それぞれを&nbsp;それに続く 4 つの句読点の 1 つに<code>.</code>置き換えようとします。この&nbsp;機能はタイプミス以外にも使用できます。<code>;</code>たとえば、パスワードで「1337」（leet）を話すのが好きな場合は、次の行に沿ってタイポマップを作成できます。<code>aA @ sS $5 oO 0&nbsp;</code><code>a</code>&nbsp;これは、 or&nbsp;のインスタンス<code>A</code>&nbsp;を&nbsp;、&nbsp;&nbsp;or&nbsp;<code>@</code>のインスタンスを&nbsp;&nbsp;a&nbsp;&nbsp;または a&nbsp;などに、オプションで指定されたタイプミスの最大数まで&nbsp;置き換えようとします&nbsp;&nbsp;。たとえば、トークン ファイルに token が含まれていて&nbsp;、&nbsp;と&nbsp;を指定した場合&nbsp;、&nbsp;&nbsp;それぞれ 3 つ以下のタイプミス/置換があるため、両方とも試行されますが、&nbsp; 5&nbsp;つのタイプミス&nbsp;では試行されません。&nbsp;&nbsp;<em>btcrecover</em>パッケージにはいくつかのタイプミスが含まれています-ディレクトリ内のサンプル ファイルをマップします&nbsp;&nbsp;。詳細については、Typos クイック スタート ガイドを参照してください。<code>s</code><code>S</code><code>$</code><code>5</code><code>--typos #</code><code>Passwords</code><code>--typos 3</code><code>P@55words</code><code>Pa$sword5</code><code>P@$$w0rd5</code><em></em><code>typos</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 id="max-typos-by-type">タイプ別の最大タイプミス</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>前述のように、&nbsp;<code>--typos #</code>&nbsp;コマンドライン オプションは、タイプに関係なく、1 回の推測に適用されるタイプミスの総数を制限します。特定の種類のタイプミスにのみ適用される制限を設定することもできます。上記の各&nbsp;<code>--typos-xxxx</code>&nbsp;コマンドライン オプションには、対応するオプションがあります&nbsp;<code>--max-typos-xxxx #</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>たとえば、 の場合&nbsp;<code>--typos 3 --typos-delete --typos-insert %a --max-typos-insert 1</code>、最大 3 つのタイプミスが試行されます。それらはすべて削除のタイプミスである可能性がありますが、挿入のタイプミス (この場合は 1 つの小文字が挿入される) は多くても 1 つだけです。<code>--typos-insert</code>&nbsp;これは、この例のように と をワイルドカードと一緒に使用する場合に&nbsp;特に便利です&nbsp;<code>--typos-replace</code>&nbsp;。試行する必要がある組み合わせの総数を大幅に減らすことができ、テストに時間がかかりすぎる総数をより合理的なものに変えることができるからです。 .</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="typos-gory-details">誤字脱字詳細</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>タイプミス機能の目的は、1 つのパスワード推測に複数のタイプミスを適用する場合でも、一度に 1 つの文字に最大 1 つのタイプミスのみを適用することです。たとえば、 を指定する場合&nbsp;<code>--typos 2 --typo-case --typo-repeat</code>、各パスワード推測には最大 2 つの入力ミスを適用できます (つまり、大文字と小文字の変更が 2 つ、&nbsp;<strong>文字</strong>&nbsp;の繰り返しが 2 つ、&nbsp;大文字<strong>と</strong>&nbsp;小文字の変更が 1 つと文字の繰り返しが 1 つまで)。推測内の 1 文字に、1 回の推測で複数のタイプミスが適用されることはありません。たとえば、1 つの文字が繰り返され、同時に大文字と小文字が変更されることはありません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ただし、この 1 文字につき 1 つのタイプミスの規則にはいくつかの例外があります。1 つは意図的なもので、もう 1 つはソフトウェアの制限によるものです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>タイプ&nbsp;<code>--typos-capslock</code>&nbsp;ミスは、推測中に Caps Lock をオンのままにしておくことをシミュレートします。1 つの入力ミスであっても、パスワードのすべての文字に一度に影響を与える可能性があります。1 文字につき 1 つのタイプミスの規則の例外として、1 つの文字が、&nbsp;&nbsp;&nbsp;Caps Lock のタイプミスと別のタイプミスの同時の影響を受ける<em>可能性があります。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この&nbsp;<code>--typos-swap</code>&nbsp;タイプミスは、1 文字につき 1 つのタイプミスの規則も無視します。隣接する 2 つの文字を入れ替えて (1 つのタイプミスとしてカウント)、入れ替えた文字の一方 (または両方) に 2 つ目のタイプミスを適用できます。これは、設計上の選択というよりもソフトウェアの制限ですが、変更される可能性はほとんどありません。ただし、1 つの文字が 1 回の推測で 2 回以上入れ替わらないことが保証されています。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最後に、タイプミスが適用される前にワイルドカード置換 (拡張と縮小) が発生し、ワイルドカード拡張の結果にタイプミスが適用される可能性があることに注意してください。パスワード作成の正確な順序は次のとおりです。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>すべてのトークン ルール (相互排除、アンカーなど) に従って、1 つ以上のトークンから「ベース」パスワードを作成します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>すべてのワイルドカードの拡張と縮小を適用します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>最大 1 つの Caps Lock のタイプミスを適用します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>0 個以上のスワップ タイプミスを適用します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>0 個以上の文字変更のタイプミスを適用します (これらのタイプミスは、&nbsp; 1 文字につき 1 つのタイプミスの規則に従い<em>ます</em>&nbsp;)。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>0 個以上のタイプミスの挿入を (&nbsp;<code>typos-insert</code>&nbsp;オプションから) 適用します。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>1 回の推測でのタイポの総数が、オプションで要求された数よりも多くなることはありません&nbsp;<code>--typos #</code>&nbsp;(オプションが使用されている場合は、オプションより少なくなることもありません&nbsp;<code>--min-typos</code>&nbsp;)。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="autosave">自動保存</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>試行する必要があるパスワードの数によっては、&nbsp;&nbsp;<em>btcrecover の</em>実行に&nbsp;非常に長い時間がかかる場合があります。テストの途中で中断された場合 (Ctrl-C (下記参照)、再起動、誤ってコマンド プロンプトを閉じるなどの理由で) は、進行状況が失われ、最初から検索をやり直さなければならない場合があります。始まり。<em>これを防ぐために、最初にbtcrecover を</em><code>--autosave savefile</code>&nbsp;起動するときにオプション&nbsp;を追加できます&nbsp;。指定したファイルに約 5 分ごとに進行状況が自動的に保存されます (この場合は名前が付けられています。&nbsp;&nbsp;まだ存在しない限り、任意のファイル名を作成できます)。<em></em><code>savefile</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>中断された場合は、まったく同じオプションを指定して実行するか、このオプションのみを指定してテストを再開できます:&nbsp;&nbsp;<code>--restore savefile</code>.&nbsp;<em>btcrecover は、</em>&nbsp;中断したところから正確にテストを開始します。(トークン ファイルと、typos-map ファイルが使用されている場合は、これが機能するためにまだ存在し、変更されていない必要があることに注意してください。存在しない場合、または変更されている場合、btcrecover は起動を拒否し&nbsp;<em>ます</em>&nbsp;。 .)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在、自動保存機能はパスワードリストではサポートされておらず、トークン ファイルでのみサポートされています。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="interrupt-and-continue">中断して続行</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>&nbsp;テストの途中で btcrecover を中断する必要がある場合は、Ctrl-C (Ctrl キーを押しながら C キーを押す) で中断できます。これにより、次のようなメッセージが返されて終了し<em>ます</em>。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>Interrupted after finishing password # 357449
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>自動保存機能を有効にしていない場合でも、中断したところから手動でテストを開始できます。<em>まったく同じ</em>&nbsp;トークン&nbsp;&nbsp;ファイルまたはパスワード リスト、typos-map ファイル (使用している場合)、およびコマンド ライン オプションと 1 つの追加オプションを使用して&nbsp;<em>btcrecover</em>を開始する必要があります&nbsp;。<em></em><code>--skip 357449</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="unicode-support">ユニコードのサポート</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>パスワードに非<a href="https://en.wikipedia.org/wiki/ASCII#ASCII_printable_code_chart">ASCII</a><code>--utf8</code>&nbsp;(非英語) 文字が含まれている場合は、&nbsp;コマンドライン オプションを&nbsp;追加して Unicode サポートを有効にする必要があります&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>btcrecover</em>へのすべての入力および btcrecover からの出力は、&nbsp;&nbsp;&nbsp;UTF-8 でエンコードする必要があることに注意してください (バイト オーダー マークまたは「BOM」の有無にかかわらず)。そのため、テキスト ファイルを保存するときは、必ずエンコードを UTF-8 に変更してください。たとえば、Windows のメモ帳では、ファイルの&nbsp;<em>エンコード設定は [</em><em>ファイル</em>&nbsp;] -&gt;&nbsp;&nbsp;<em>[名前を付けて保存]ダイアログの</em><em>[保存]</em>&nbsp;ボタン&nbsp;&nbsp;のすぐ隣にあります&nbsp;&nbsp;。<em></em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Windows では (通常、Linux や OS X ではそうではありません)、使用する必要があるコマンド ライン オプションのいずれかに非 ASCII 文字が含まれていると、問題が発生する可能性があります。通常、入力したときにコマンドプロンプトウィンドウに正しく表示されれば、&nbsp;&nbsp;<code>btcrecover.py</code>.&nbsp;正しく表示されない場合は、&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#command-line-options-inside-the-tokens-file">トークン ファイル内にコマンドライン オプションを</a>配置する方法について説明しているセクションをお読みください。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>また、Windows (通常は Linux や OS X ではありません) では、パスワードが見つかった場合、コマンド プロンプト ウィンドウに正しく表示されない場合があります。誤った出力がどのように見えるかの例を次に示します。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>Password found: 'btcr-????-??????'
HTML encoded:   'btcr-&amp;#1090;&amp;#1077;&amp;#1089;&amp;#1090;-&amp;#1087;&amp;#1072;&amp;#1088;&amp;#1086;&amp;#1083;&amp;#1100;'
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ご覧のとおり、Windows コマンド プロンプトでは一部の文字をレンダリングできませんでした (&nbsp;<code>?</code>&nbsp;文字に置き換えられました)。見つかったパスワードを表示するには、その行をコピーしてテキスト ファイルに貼り付け&nbsp;、&nbsp;通常の ではなく で&nbsp;<code>HTML encoded</code>&nbsp;終わる名前で保存します&nbsp;。新しい&nbsp;&nbsp;ファイルをダブルクリックすると、Web ブラウザーで開き、正しいパスワードが表示されます。<code>.html</code><code>.txt</code><code>.html</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>HTML encoded: 'btcr-тест-пароль'
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="running-btcrecover"><em>btcrecover</em>の実行&nbsp;<em></em></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>(クイック スタート セクションも参照してください。) すべての要件 (上記) をインストールし、最新バージョンをダウンロードしたら、次の手順を実行します。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>ファイルを解凍すると&nbsp;<code>btcrecover-master.zip</code>&nbsp;、「btcrecover-master」という名前のディレクトリが 1 つ含まれています。btcrecover-master ディレクトリ内には、Python スクリプト (プログラム) ファイル があります&nbsp;<code>btcrecover.py</code>。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong></strong> を含むディレクトリに <strong>ウォレット ファイルのコピーを作成します</strong><code>btcrecover.py</code>。Windows では、通常、[スタート] メニューをクリックし、[ファイル名を指定して実行] をクリックしてウォレット ファイルを見つけることができます (Windows 8 以降の場合は、Windows キーを押しながら を押します)。次に、次のいずれかのパスを入力して [OK] をクリック <em>し</em> ます <code>r</code>。 . 一部のウォレット ソフトウェアでは、複数のウォレットを作成できます。もちろん、正しいウォレット ファイルをコピーする必要があります。<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>BIP-39 パスフレーズ – 以下の BIP-39 パスフレーズ セクションを参照してください。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ビットコイン コア –&nbsp;&nbsp;<code>%appdata%\Bitcoin</code>&nbsp;(名前は&nbsp;<code>wallet.dat</code>)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;Android/BlackBerry 用ビットコイン ウォレット、支払い用 PIN の紛失 –以下の<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#bitcoin-wallet-for-androidblackberry-spending-pins">Android/BlackBerry 用ビットコイン ウォレットの支払い用 PIN</a>セクションをご覧ください&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bither –&nbsp;&nbsp;<code>%appdata%\Bither</code>&nbsp;(名前は&nbsp;<code>address.db</code>)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Blockchain.com – 通常は という名前です&nbsp;<code>wallet.aes.json</code>。ウォレット ファイルのバックアップがない場合、&nbsp;&nbsp;ウォレット ID (および有効な場合は 2FA) がわかっている場合は、ディレクトリ<code>download-blockchain-wallet.py</code>&nbsp;でツール&nbsp;を実行してダウンロードできます。<code>extract-scripts</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Coinomi –&nbsp;以下の<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#finding-coinomi-wallet-files">「Coinomi ウォレット ファイルの検索」</a>&nbsp;セクションを参照してください。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>エレクトラム –&nbsp;<code>%appdata%\Electrum\wallets</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Litecoin-Qt –&nbsp;&nbsp;<code>%appdata%\Litecoin</code>&nbsp;(名前は&nbsp;<code>wallet.dat</code>)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Metamask (および Binance Chain Wallet、Ronin Wallet などの Metamask クローン) –&nbsp;以下の<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#finding-metamask-wallet-files">「Metamask Wallet ファイルの検索」</a>&nbsp;セクションを参照してください。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit Classic –&nbsp;以下の<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#finding-multibit-classic-wallet-files">「MultiBit Classic Wallet ファイルの検索」</a>&nbsp;セクションを参照してください。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit HD –&nbsp;&nbsp;<code>%appdata%\MultiBitHD</code>&nbsp;(ここのフォルダーの 1 つにあり、名前が付けられています&nbsp;<code>mbhd.wallet.aes</code>)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>mSIGNA –&nbsp;&nbsp;<code>%homedrive%%homepath%</code>&nbsp;(ファイルです&nbsp;<code>.vault</code>&nbsp;)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ファイルがあれば&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;、ほぼ完了です。を含むディレクトリにコピーし&nbsp;<code>btcrecover.py</code>、ファイルをダブルクリックするだけで&nbsp;<code>btcrecover.py</code>&nbsp;、&nbsp;&nbsp;<em>btcrecover が</em>&nbsp;パスワードのテストを開始します。(ファイル内に記載されているファイル名と一致しない場合は、ウォレット ファイルの名前を変更する必要がある場合があります&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;。) ファイルがない場合は&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;、以下を読み続けてください。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>tokens.txt</code>&nbsp;ファイル、または passwordlist ファイルを使用している場合はファイルを、 を含むディレクトリに&nbsp;コピーします&nbsp;<code>btcrecover.py</code>。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#the-token-file">トークン ファイル</a>&nbsp;または&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#the-passwordlist">Passwordlist</a>のどちらを使用しているかに応じて&nbsp;、&nbsp;ウォレット ファイル名と または (FILE はオプションです) を識別するため&nbsp;&nbsp;に&nbsp;&nbsp;、&nbsp;<code>btcrecover.py</code>&nbsp;少なくとも 2 つのコマンドライン オプションを指定して&nbsp;実行する必要があります&nbsp;。<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#typos">Typos</a>&nbsp;または&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#autosave">Autosave</a>を使用している場合は&nbsp;、追加するオプションについて上記のセクションを参照してください。<code>--wallet FILE</code><code>--tokenlist FILE</code><code>--passwordlist FILE</code><code>--passwordlist</code><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#the-token-file"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#the-passwordlist"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#typos"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#autosave"></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Windows と OS X の両方の例を次に示します。システムの詳細は異なります。たとえば、ダウンロード場所が異なる場合や、ウォレット ファイル名が異なる場合があるため、いくつかの変更を加える必要があります。<em>追加のオプションはすべてbtcrecover</em>行の最後に配置されます  。<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>Windows</em>&nbsp;: コマンド プロンプト ウィンドウを開き ([スタート] メニューをクリックして「command」と入力)、以下の 2 行を入力します。<code>cd Downloads\btcrecover-master python3 btcrecover.py --wallet wallet.dat --tokenlist tokens.txt [other-options...]</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>OS X</em>&nbsp;: ターミナル ウィンドウを開き (Launchpad を開いて「ターミナル」を検索します)、以下の 2 行を入力します。<code>cd Downloads/btcrecover-master python3 btcrecover.py --wallet wallet.dat --tokenlist tokens.txt [other-options...]</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>少し遅れて、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;パスワードのテストを開始し、以下に示すように進行状況バーと ETA を表示します。メッセージが表示され、プログレス バーが表示されず、カウントアップだけで止まっているように見える場合は&nbsp;、&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Limitations_and_Caveats/#memory">「メモリの制限」</a>&nbsp;セクション<code>Counting passwords ...</code>&nbsp;をお読みください&nbsp;。それでも問題が解決しない場合は、テストするトークンまたはタイプミスが多すぎて、システムが処理できない組み合わせになっている可能性があります (ただし、この&nbsp;&nbsp;オプションが役立つ場合があります)。<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Limitations_and_Caveats/#memory"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#token-counts"><code>--max-tokens</code></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>Counting passwords ...
Done
Using 4 worker threads
439 of 7661527 &#91;-------------------------------] 0:00:10, ETA:  2 days, 0:25:56
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>組み合わせの 1 つがウォレットの正しいパスワードである場合、最終的にパスワードが表示され、&nbsp;&nbsp;<em>btcrecover</em>&nbsp;の実行が停止します。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>1298935 of 7661527 &#91;####-----------------------] 8:12:42, ETA:  1 day, 16:13:24
Password found: 'Passwd42'
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>すべてのパスワードの組み合わせが試行され、いずれもウォレットに対して正しくない場合、代わりに次のメッセージが表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>7661527 of 7661527 &#91;########################################] 2 days, 0:26:06,
Password search exhausted
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>btcrecover.py</code>&nbsp;この&nbsp;オプションを指定して実行すると、&nbsp;<code>--help</code>&nbsp;使用可能なすべてのコマンドライン オプションの概要が表示されます。そのほとんどは上記のセクションで説明されています。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="testing-your-config">構成のテスト</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>&nbsp;トークン ファイルや選択したタイプミスをテストしたいだけの場合は、以下に示すように、オプション&nbsp;<code>--listpass</code>&nbsp;の代わりにオプションを&nbsp;使用できます&nbsp;。<em>btcrecover は、</em>&nbsp;実際にウォレット ファイルに対してパスワードをテストする代わりに、すべてのパスワードを画面に一覧表示します。<em>これは、他のタイプのウォレットをテストできる別のツールがあり、 btcrecover</em>からテストするパスワードのリストを取得できる場合にも役立ちます&nbsp;。このオプションは非常に多くの出力を生成する可能性があるため、短いトークン ファイルと少数のタイプミス オプションでのみ使用することをお勧めします。<code>--wallet FILE</code><em></em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>    python3 btcrecover.py --listpass --tokenlist tokens.txt  | more
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>最後&nbsp;<code>| more</code>&nbsp;の (&nbsp;<code>|</code>&nbsp;記号はシフトされた&nbsp;<code>\</code>&nbsp;バックスラッシュです) は、1 画面分のパスワードの後に​​一時停止を導入します。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="extracting-yoroi-master-key">ヨロイマスターキーの抽出</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Chrome ベースのブラウザ ウォレット</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>まずヨロイウォレットを開き、ブラウザで開発者ツールを開く必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次に、「アプリケーション」(Chrome) に移動し、「IndexedDB」セクションに移動し、「ヨロイスキーマ」を開いて「キー」セクションに移動する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次に、マスター キーのリストが表示されます。以下に示すように、おそらく最初の暗号化キーが必要です。</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/Yoroi_Extract_MasterKey_Chrome.jpg" alt="Yoroi_Masterkey"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>次に、「ハッシュ」フィールドをクリックして、「コピー」を選択します。<code>--yoroi-master-password</code>&nbsp;この文字列は、引数で使用するものです&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Firefox ブラウザのウォレット</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>拡張子の .sqlite ファイルに直接アクセスすると、データを見つけることができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これは、拡張機能のブラウザー プロファイル フォルダー (この場所は環境によって異なります) にあります。以下のスクリーンショットの一番上に、このファイルが Windows 環境で見つかった例が示されています。</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/Yoroi_Extract_MasterKey_Firefox.jpg" alt="Yoroi_Masterkey"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>次に、テキスト エディターで開き、文字列「Hash」または「isEncrypted」を探すだけで、暗号化されたマスター パスワードがクリア テキストで表示されます。(上のスクリーンショットで緑色で強調表示されている部分)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>--yoroi-master-password</code>&nbsp;この文字列は、引数で使用するものです&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="finding-multibit-classic-wallet-files">MultiBit Classic Wallet ファイルの検索</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover は</em>&nbsp;、MultiBit クラシック ウォレット ファイルを直接操作するのではなく、MultiBit 秘密鍵のバックアップ ファイルを操作します。初めて MultiBit Classic ウォレットにパスワードを追加した後、新しい受信アドレスを追加するか、ウォレットのパスワードを変更するたびに、MultiBit は暗号化された秘密鍵のバックアップ ファイルをウォレット ファイルの近くのディレクトリに作成します&nbsp;<code>key-backup</code>&nbsp;。これらの秘密鍵のバックアップ ファイルは、パスワードの試行がはるかに高速であるため (1,000 倍以上)、&nbsp;&nbsp;<em>btcrecover が</em>&nbsp;それらを使用する理由です。MultiBit を最初にインストールしたときに作成されるデフォルトのウォレットの場合、このディレクトリは次の場所にあります。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>%appdata%\MultiBit\multibit-data\key-backup
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>キー ファイルの名前は&nbsp;<code>walletname-20140407200743.key</code>.&nbsp;追加のウォレットを作成した場合、それらの&nbsp;<code>key-backup</code>&nbsp;ディレクトリは別の場所に配置され、それらを見つけるのはあなた次第です。取得したら、最新の&nbsp;<code>.key</code>&nbsp;ファイルを選択し、それを含むディレクトリにコピーして&nbsp;<code>btcrecover.py</code>&nbsp;使用します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>MultiBit 秘密鍵のバックアップ ファイルの場所の詳細については、https:&nbsp;&nbsp;<a href="https://www.multibit.org/en/help/v0.5/help_fileDescriptions.html" target="_blank" rel="noreferrer noopener">//www.multibit.org/en/help/v0.5/help_fileDescriptions.htmlを参照してください。</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="finding-metamask-wallet-files">Metamask ウォレット ファイルの検索</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Chrome ベースのブラウザーの場合、ブラウザー拡張機能のデータ フォルダーを見つける必要があります。次に、このウォレット フォルダへのパスを –wallet 引数と共に使用します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Metamask の場合: %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\nkbihfbeogaeaoehlefnkodbefgpgknn</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Binance Wallet Extension の場合: %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fhbohimaelbohpjbbldcngcnapndodjp</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Ronin ウォレットの場合: %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fnjhmkhhmkbjkkabndcnnogagogbneec</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最新のウォレット以外のものを復元しようとしている場合は、extract スクリプトを使用して、拡張データ内にある可能性のあるボールトをすべて一覧表示する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Firefox および iOS の場合、https://metamask.zendesk.com/hc/en-us/articles/360018766351-How-to-use-the-Vault-Decryptor で説明されているプロセスを使用して Metamask ボールトを取得する必要があります。 -with-the-MetaMask-Vault-Data</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>モバイル ウォレット (iOS および Android) の場合、BTCRecover に渡す「ウォレット ファイル」はファイルです。&nbsp;<code>persist-root</code>&nbsp;上記のプロセスを使用してファイルを見つけ、BTCRecover で直接使用できます。(vault データのみを抽出したり、余分な&nbsp;<code>\</code>&nbsp;文字を削除したりする必要はありません。これらはすべて自動的に処理されます)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Android デバイスの場合、ほとんどの場合、「ルート化された」電話が必要になります。あなたが求めているファイルは次のとおりです。&nbsp;<code>/data/data/io.metamask/files/persistStore/persist-root</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>その後、vault データを (Firefox または抽出スクリプトから) テキスト ファイルにコピー アンド ペーストし、それを –wallet 引数で直接使用できます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="finding-coinomi-wallet-files">Coinomi ウォレット ファイルの検索</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注: これは、パスワードで保護されているウォレットのみをサポートします。「パスワードなし」、「バイオメトリクス」、または「パスワード + バイオメトリクス」を選択した場合は、携帯電話のキーストアからの情報も必要になります... (取得できない場合があります)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Coinomi の最初のステップは、実行しているプラ​​ットフォームによって異なります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Windows ユーザーの場合は、%localappdata%\Coinomi\Coinomi\wallets に移動するだけで、ウォレット ファイルが見つかります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Android ユーザーの場合、Coinomi の .wallet ファイルにアクセスできるルート化された電話が必要です。(フォルダー data\data\com.coinomi.wallet\files\wallets にあるはずです) 特定の電話で root アクセスを取得する方法は、このドキュメントの範囲外ですが、電話を root 化する方法によっては、工場出荷時設定へのリセットを伴います。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>そこに複数のウォレットがあり、どれが正しいかわからない場合は、各ウォレットの名前がファイルの末尾に平文で表示されます。例として、./btcrecover/test/test-wallets にあるこのリポジトリに含まれるテスト ウォレットを参照してください)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="downloading-dogechaininfo-wallet-files">Dogechain.info ウォレット ファイルのダウンロード</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>これらの種類のウォレット ファイルのダウンロードは、「開発者ツール」機能を使用して、ブラウザ経由で行われます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本的に、(パスワードが間違っていても) ウォレットへのログインを試行し、このプロセスの一環としてダウンロードされたウォレット ファイルを保存する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ブラウザで開発者ツールを開いた状態で dogechain.info ウォレットのログイン ページに移動したら、次の手順を実行する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1) [ネットワーク] タブを選択します</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) ウォレット ID を入力してください</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) プレースホルダーのパスワードを入力します (何でも入力できます)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4) [ログイン] をクリックします (ウォレットの復号化に失敗したと表示されますが、これは正常です)。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) 「回答」を選択</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>6) API アイテムを選択します。(2fa を有効にしている場合、これは少し異なるように見えるかもしれません。このステップでも 2fa を完了する必要があるかもしれません)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>7) ウォレット データのような応答が得られたら、それをコピーしてテキスト ファイルに貼り付けます。これはあなたのウォレットファイルです…</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/download_dogechain_wallet.png" alt="ドッジチェーンウォレットをダウンロード"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="downloading-blockio-wallet-files">block.io ウォレット ファイルのダウンロード</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>これらの種類のウォレット ファイルのダウンロードは、「開発者ツール」機能を使用して、ブラウザ経由で行われます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本的に、ウォレットにログインしてから「設定」画面に移動する必要があります。そこでブラウザで「開発者ツール」を開くことができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1) [ネットワーク] タブを選択します</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) [現在の PIN] フィールドにプレースホルダー PIN を入力します。(「123」など、何でもかまいません)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) [新しいシークレット PIN] フィールドにプレースホルダー パスワードを入力します。(これは何でもかまいませんが、有効である必要があります。例: btcrtestpassword2022)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4) 「シークレット PIN の変更」をクリックします (シークレット PIN が正しくないというエラーが表示されますが、問題ありません…)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) 「回答」を選択</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>6) Initiate_change_secrets ファイルを選択します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>7) ウォレット データのような応答が得られたら、それをコピーしてテキスト ファイルに貼り付けます。これはあなたのウォレットファイルです…</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/download_block_io_wallet.png" alt="ブロック IO ウォレットをダウンロード"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="bitcoin-wallet-for-androidblackberry-spending-pins">Android/BlackBerry 使用 PIN 用のビットコイン ウォレット</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Android/BlackBerry 用のビットコイン ウォレットには、&nbsp;&nbsp;オプションで有効にできる<em>支出 PIN機能があります。</em>支払い PIN を紛失した場合は、&nbsp;&nbsp;<em>btcrecover を</em>使用して&nbsp;回復を試みることができます。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>ビットコイン ウォレット アプリを開き、メニュー ボタンを押して、[安全性] を選択します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>[ウォレットのバックアップ]</em>を選択します&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ウォレットのバックアップ ファイルを保護するためのパスワードを入力し、[OK] を押します。このパスワードは後で覚えておく必要があります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>右下隅にある [アーカイブ] ボタンを押します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ウォレットのバックアップ ファイルを PC と共有する方法を選択します。たとえば、Gmail やドライブを選択できます。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><em>このウォレット バックアップ ファイルは、PC に保存されると、 btcrecover</em>の他のウォレット ファイルと同じように使用できますが、&nbsp;重要な例外が 1 つあります。&nbsp;<em>btcrecover</em>&nbsp;を実行するときは&nbsp;、&nbsp;オプション&nbsp;を追加する&nbsp;<strong>必要があります</strong><code>--android-pin</code>&nbsp;。その場合、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;(手順 3 から) バックアップ パスワードを要求し、使用 PIN の回復を試みます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>通常、PIN には数字だけが含まれているため、トークン ファイルには通常、次のようなものが含まれます (たとえば、最大 6 桁の PIN の場合)&nbsp;&nbsp;<code>%1,6d</code>。&nbsp;(詳細については、<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#expanding-wildcards">ワイルドカード</a>のセクションを参照してください&nbsp;。)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このオプションを含めない場合&nbsp;<code>--android-pin</code>&nbsp;、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;代わりにバックアップ パスワードの回復を試みることに注意してください。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="bip-39-passphrases-electrum-extra-words">BIP-39 パスフレーズとエレクトラム「エクストラワード」</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>一部の&nbsp;<a href="https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki">BIP-39</a>&nbsp;準拠のウォレットは、「25 番目の単語」、「BIP-39 パスフレーズ」、または「もっともらしい否認パスフレーズ」をシード (ニーモニック) に追加する機能を提供します (ほとんどのハードウェア ウォレットは、サポートされていない PIN 機能も提供することに注意してください)。によって&nbsp;<em>btcrecover</em>。)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>シードはわかっているが、このパスフレーズを覚えていない場合は、&nbsp;&nbsp;<em>btcrecover が</em>&nbsp;役立つ場合があります。また、次のいずれかを知る必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>マスター公開鍵/「xpub」（&nbsp;&nbsp;複数のアカウントをサポートしている場合は、ウォレットの&nbsp;<em>最初のアカウント用）、</em><em>または</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ウォレットによって（最初のアカウントで）生成された受信アドレスと、使用したい受信アドレスの前に作成したアドレスの数の適切な見積もり。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>この情報を取得したら、&nbsp;&nbsp;<em>btcrecover を</em>&nbsp;通常どおりに実行します。ただし、&nbsp;&nbsp;上記のオプションを使用してコマンド ラインでウォレット ファイルを指定する代わりに&nbsp;<em>、</em><code>--wallet wallet.dat</code>次のようなオプション&nbsp;を使用します&nbsp;<code>--bip39</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 btcrecover.py --bip39 --tokenlist tokens.txt &#91;other-options...]
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>復元しようとしているアドレス/アカウントが BIP39/44 ウォレットからのもので、ビットコイン以外の通貨の場合は、引数を使用して、seedrecover.py でサポートされているサポートされている BIP39 ウォレット タイプを指定できます&nbsp;<code>--wallet-type</code>&nbsp;。(例: bch、bip39、bitcoinj、dash、digibyte、dogecoin、ethereum、electrum2、groestlecoin、litecoin、monacoin、ripple、vertcoin、zilliqa) を使用して、これらのいずれかと派生スキームを共有するサポートされていないコインで回復を試みることもできます。<code>--bip32-path</code>&nbsp;そのコインの派生パスを持つ引数。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>詳細については、&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/bip39-accounts-and-altcoins/">BIP39 アカウントとアルトコインに関する注意事項を参照してください。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>シードと BIP39 パスフレーズの両方が不明な場合は、seedrecover.py を使用して複数の BIP39 パスフレーズを指定する必要があります。（ただし、これは非常に遅いことに注意してください）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gpu-acceleration-for-bitcoin-core-and-litecoin-qt-wallets">Bitcoin Core および Litecoin-Qt ウォレットの GPU アクセラレーション</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover には</em>&nbsp;、1 つ以上のグラフィックス カードまたは専用のアクセラレータ カードを使用して検索パフォーマンスを向上させるための実験的なサポートが含まれています。&nbsp;これは、Bitcoin Unlimited/Classic/XT/Core または Litecoin-Qt ウォレットを有効にして正しく調整すると、<em>100 倍</em>のパフォーマンスを提供できます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>詳細については、GPU アクセラレーション ガイドを参照してください。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="command-line-options-inside-the-tokens-file">トークン ファイル内のコマンド ライン オプション</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>必要に応じて、コマンドライン オプションをファイル内に直接配置することもできます&nbsp;<code>tokens.txt</code>&nbsp;。これを行うには、トークン ファイルの最初の行を正確に で開始する必要があり&nbsp;<code>#--</code>、この行の残りの部分 (およびこの行のみ) は、追加のコマンド ライン オプションとして解釈されます。たとえば、自動保存、終了前の一時停止、および 1 種類のタイプミスを有効にするトークン ファイルは次のとおりです。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>#--autosave progress.sav --pause --typos 1 --typos-case
Cairo
Beetlejuice Betelgeuse
Hotel_california
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="btcrecover-tokens-autotxt">btcrecover-tokens-auto.txt</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>通常、 btcrecover</em>を実行するときは、&nbsp;&nbsp;トークン ファイルやウォレット ファイルの場所など、少なくともいくつかのオプションを指定して実行する必要があります。<code>--tokenlist</code>&nbsp;または&nbsp;を指定せずに実行すると&nbsp;<code>--passwordlist</code>、現在のディレクトリに指定されたファイルがあるかどうかがチェックされ&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;、見つかった場合はそれが tokenlist に使用されます。&nbsp;必要に応じて tokenlist ファイル内でオプションを指定できるため (上記を参照)、コマンド ラインをまったく使用せずに<em>btcrecover</em>を実行できます&nbsp;。<code>--pause</code>&nbsp;コマンド プロンプト ウィンドウをこの方法で実行する場合は、コマンド プロンプト ウィンドウが実行後にすぐに閉じないようにするオプションを使用することを検討してください&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="limitations-caveats">制限事項と注意事項</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="beta-software">ベータ版ソフトウェア</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>このソフトウェアがウォレット ファイルに損害を与える可能性はほとんどありませんが、&nbsp;<strong>ウォレットのコピーでのみ実行することを強くお勧めします</strong>。特に、このソフトウェアは&nbsp;<strong>無保証で</strong>配布されています。詳細については、付属の GPLv2 ライセンス条件を参照してください。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このソフトウェアはベータ版ソフトウェアであり、他のベータ版ソフトウェアと相互作用するため、ユーザーが正しく設定したパスワードを見つけられない可能性が十分にあります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="additional-limitations-caveats">追加の制限と注意事項</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>これらのトピックの詳細については、個別の制限事項と注意事項のドキュメントを参照してください。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>パスワードの区切り文字、スペース、および特殊記号</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>メモリと CPU 使用率</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>セキュリティ上の問題</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>タイプミスの詳細</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="download">ダウンロード</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/archive/master.zip">https://github.com/demining/CryptoDeepTools/archive/master.zip</a>&nbsp;から&nbsp;<em>btcrecover</em>パッケージ全体をダウンロードできます。&nbsp;<a href="https://github.com/demining/CryptoDeepTools/archive/master.zip"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>抽出スクリプトを 1 つだけダウンロードしたい場合は、以下からお使いのウォレット ソフトウェアを選択し、右クリックして [リンク先を保存] または [対象を保存] を選択してください。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>ビットコインコア –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bitcoincore-mkey.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bitcoincore-mkey.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>バイザー –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bither-partkey.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bither-partkey.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ブロックチェーンのメインパスワード –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-main-data.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-main-data.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ブロックチェーンの 2 番目のパスワード –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-second-hash.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-second-hash.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum 1.x –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum-halfseed.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum-halfseed.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum 2.x –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum2-partmpk.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum2-partmpk.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>mSIGNA –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-msigna-partmpk.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-msigna-partmpk.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>マルチビット クラシック –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-privkey.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-privkey.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>マルチビット HD –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-hd-data.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-hd-data.py</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Windows を使用している場合は、最新バージョンの Python 3.7 以降もインストールする必要があります。その他のウォレットについては、こちらの指示に従って Python をインストールしてください。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="usage-for-bitcoin-core">ビットコインコアの使い方</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>スクリプトをダウンロードしたら、&nbsp;&nbsp;<strong>wallet.dat ファイルのコピーを別のフォルダーに作成します</strong>&nbsp;(簡単にするために、&nbsp;&nbsp;<em>extract-bitcoincore-mkey.py</em>と同じフォルダーに作成します)。Windows の例として、[スタート] メニューをクリックし、[ファイル名を指定して実行] をクリックし、次のように入力して wallet.dat ファイルを含む Bitcoin フォルダーを開きます&nbsp;<code>%appdata%\Bitcoin</code>。ここから、wallet.dat ファイルをコピーして別のフォルダーに貼り付けることができます。次に、コマンド プロンプト ウィンドウを開いて、次のように入力する必要があります (ダウンロードしたスクリプトの場所によって異なります。また、wallet.dat のコピーを同じフォルダーに作成したと仮定します)。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-bitcoincore-mkey.py wallet.dat
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>結果として、次のようなメッセージが表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>Bitcoin Core encrypted master key, salt, iter_count, and crc in base64:
lV/wGO5oAUM42KTfq5s3egX3Uhk6gc5gEf1R3TppgzWNW7NGZQF5t5U3Ik0qYs5/dprb+ifLDHuGNQIA+8oRWA==
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>代わりに、pywallet によって作成された Bitcoin Core ウォレットのダンプ ファイルがある場合は、代わりにextract-bitcoincore-mkey-from-pywallet.py</em>スクリプトを使用することを除いて、同じ手順に従ってください&nbsp;&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>あなた (または他の誰か) が&nbsp;<em>btcrecover を</em>実行して&nbsp;パスワードを検索する場合、ウォレット ファイルは必要なく、&nbsp;&nbsp;<em>extract-bitcoincore-mkey.py</em>からの出力のみが必要です。例を続けるには:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; lV/wGO5oAUM42KTfq5s3egX3Uhk6gc5gEf1R3TppgzWNW7NGZQF5t5U3Ik0qYs5/dprb+ifLDHuGNQIA+8oRWA==
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="bitcoin-core-technical-details">ビットコインコアの技術詳細</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>extract-bitcoincore-mkey.py</em>スクリプト&nbsp;&nbsp;は意図的に短く、Python プログラマーにとって読みやすいものになっています。Python bsddb.db (このモジュールが利用できない場合は Pure Python 実装) または SQLite を使用して wallet.dat ファイルを開き、キー文字列&nbsp;<code>\x04mkey\x01\x00\x00\x00</code>.&nbsp;このキーと値のペアには、Bitcoin Core の「マスター キー」の暗号化されたバージョン (略して mkey) と、mkey の復号化を試みるために必要なその他の情報 (具体的には mkey ソルトと反復回数) が含まれています。この情報は、簡単にコピー/貼り付けできるように base64 形式に変換され、画面に出力されます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>暗号化された mkey はbtcrecover</em>に役立ちます&nbsp;が、Bitcoin アドレスや秘密鍵情報は一切含まれていません。&nbsp;<em>btcrecover は、</em>&nbsp;さまざまなパスワードの組み合わせを試すことで、mkey の解読を試みることができます。成功すると、ウォレット ファイルのパスワードを知ることができますが、ウォレット ファイルの残りの部分がなければ、パスワードと復号化された mkey は役に立ちません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-bither">バイザーの使い方</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>スクリプトをダウンロードした後、&nbsp;<strong>ウォレット ファイルのコピーを別のフォルダーに作成します</strong>&nbsp;(簡単にするために、抽出スクリプトと同じフォルダーにします)。Windows の例として、[スタート] メニューをクリックし、[ファイル名を指定して実行] をクリックしてから、次のように入力して、通常はウォレット ファイルを含むフォルダーを開きます&nbsp;<code>%appdata%\Bither</code>。<code>address.db</code>ここから、ウォレット ファイル (通常は という名前) を別のフォルダーにコピー アンド ペーストできます&nbsp;。次に、コマンド プロンプト ウィンドウを開いて、次のように入力する必要があります (ダウンロードしたスクリプトの場所に応じて、ウォレット ファイルが同じフォルダーにあると仮定します)。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-bither-partkey.py address.db
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>次のようなメッセージが表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>Bither partial encrypted private key, salt, and crc in base64:
YnQ6PocfHvWGVbCzlVb9cUtPDjosnuB7RoyspTEzZZAqURlCsLudQaQ4IkIW8YE=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>あなた (または他の誰か) が&nbsp;<em>btcrecover を</em>実行して&nbsp;パスワードを検索する場合、ウォレット ファイルは必要なく、&nbsp;&nbsp;<em>extract-bither-partkey.py</em>からの出力のみが必要です。例を続けるには:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; YnQ6PocfHvWGVbCzlVb9cUtPDjosnuB7RoyspTEzZZAqURlCsLudQaQ4IkIW8YE=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="bither-technical-details">バイザーの技術詳細</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>extract-bither-partkey.py</em>スクリプト&nbsp;&nbsp;は意図的に短く、Python プログラマーにとって読みやすいものになっています。Bither で暗号化された秘密鍵の長さは 48 バイトです。これには、32 バイトの暗号化された秘密鍵データが含まれ、その後に 16 バイトの暗号化されたパディングが続きます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>秘密鍵の最後の半分のみが抽出されるため、秘密鍵のこの半分を復号化できたとしても (パスワード検索が成功すると仮定して)、秘密鍵を適切に再構築することはできません。パディングの残りの 16 バイトは、復号化されると予測可能であり、これにより、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;それを使用してパスワードをチェックできます。各パスワードでバイトの暗号化を解除しようとし、有効なパディングが得られると、正しいパスワードを見つけたことになります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ウォレット ファイルの残りの部分にアクセスできなければ、復号化されたパディングによって資金が失われることはありません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-blockchaincom">Blockchain.com での使用</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>最初のステップは、Blockchain.com ウォレットのバックアップ ファイルをダウンロードすることです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>extract-scripts</code>&nbsp;このパッケージのフォルダーに移動して実行する必要があります&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 download-blockchain-wallet.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>プロンプトが表示されたら、ウォレット ID を入力し、ウォレットに関連付けられた電子メール アカウントでログイン リクエストを承認します。ログインが承認されると、wallet.aes.json ファイルが PC に保存されます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次に、コマンド プロンプト ウィンドウを開いて、次のように入力する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 extract-blockchain-main-data.py wallet.aes.json
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>もちろん、ウォレットのファイル名を自分のものに置き換える必要があります。結果として、次のようなメッセージが表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>Blockchain first 16 encrypted bytes, iv, and iter_count in base64:
Yms6abF6aZYdu5sKpStKA4ihra6GEAeZTumFiIM0YQUkTjcQJwAAj8ekAQ==
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>あなた (または他の誰か) が&nbsp;<em>btcrecover</em>を実行して&nbsp;パスワードを検索する場合、ウォレット ファイルは必要なく、&nbsp;&nbsp;<em>extract-blockchain-main-data.py</em>からの出力のみが必要です。例を続けるには:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; Yms6abF6aZYdu5sKpStKA4ihra6GEAeZTumFiIM0YQUkTjcQJwAAj8ekAQ==
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="blockchaincom-second-passwords">Blockchain.com の 2 番目のパスワード</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Blockchain.com ウォレットの 2 番目のパスワード機能を有効にしていて、この 2 番目のパスワードを検索する必要がある場合、まだメイン パスワードを持っていない場合は、最初にメイン パスワードを見つける必要があります (上記を参照)。メインのパスワードを取得したら、ウォレットのバックアップ ファイル (通常は という名前&nbsp;<code>wallet.aes.json</code>) を取得し、&nbsp;<strong>そのコピーを別のフォルダーに作成します</strong>&nbsp;(簡単にするために、extract スクリプトと同じフォルダーに作成します)。次に、コマンド プロンプト ウィンドウを開いて、次のように入力する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-blockchain-second-hash.py wallet.aes.json
Please enter the Blockchain wallet's main password:
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>抽出スクリプトが第 1 レベルの暗号化を削除して第 2 レベルの暗号化データにアクセスできるように、プロンプトが表示されたらウォレットのメイン パスワードを入力する必要があります。結果として、次のようなメッセージが表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>Blockchain second password hash, salt, and iter_count in base64:
YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>あなた (または他の誰か) が&nbsp;<em>btcrecover</em>を実行して&nbsp;パスワードを検索する場合、ウォレット ファイルは必要なく、&nbsp;&nbsp;<em>extract-blockchain-second-hash.py</em>からの出力のみが必要です。例を続けるには:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>extract-blockchain-second-hash.py</em>&nbsp;スクリプトを使用するには、AES 復号化ライブラリを含む&nbsp;<em>btcrecover</em>パッケージ全体をダウンロードするか、PyCrypto が既にインストールされている必要があることに注意してください&nbsp;&nbsp;。<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="blockchaincom-technical-details">Blockchain.com の技術的な詳細</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract-blockchain-main-data.py&nbsp;スクリプトは意図的に短く、Python プログラマー<em>にとって</em>&nbsp;読みやすいものにします。このスクリプトは、Blockchain.com ウォレットから暗号化されたデータの最初の 32 バイトを抽出します。そのうちの 16 バイトは AES 初期化ベクトルであり、残りの 16 バイトは最初の暗号化された AES ブロックです。この情報は、簡単にコピー/貼り付けできるように base64 形式に変換され、画面に出力されます。<em>暗号化さ</em>れた 1 つのブロックには秘密鍵情報は含まれませんが、復号化されると機密性の低い文字列 (具体的&nbsp;には文字列「guid」、「tx_notes」、「address_book」、または「double」) が含まれます。&nbsp;パスワードの試行が成功するかどうかをテストします。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>extract-blockchain-second-hash.py&nbsp;スクリプトは少し長くなります<em>が</em>&nbsp;、ほとんどの Python プログラマーが読んで理解できるほど十分に短いはずです。<em>Blockchain.com ウォレットの第 1 レベルの暗号化を解読した後、 btcrecover が</em>&nbsp;パスワード試行の成功をテストするために使用できるパスワード ハッシュとソルトを抽出します&nbsp;。暗号化された秘密鍵は抽出されません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ウォレット ファイルの残りの部分にアクセスしなくても、これらのスクリプトによって抽出された情報だけでは、パスワードの推測と解読が成功した後でも、ビットコインの資金が危険にさらされることはありません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-coinomi">Coinomiの使い方</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注: これは、パスワードで保護されているウォレットのみをサポートします。「パスワードなし」、「バイオメトリクス」、または「パスワード + バイオメトリクス」を選択した場合は、携帯電話のキーストアからの情報も必要になります... (取得できない場合があります)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Coinomi の最初のステップは、実行しているプラ​​ットフォームによって異なります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Windows ユーザーの場合は、%localappdata%\Coinomi\Coinomi\wallets に移動するだけで、ウォレット ファイルが見つかります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Android ユーザーの場合、Coinomi の .wallet ファイルにアクセスできるルート化された電話が必要です。(フォルダー data\data\com.coinomi.wallet\files\wallets にあるはずです) 特定の電話で root アクセスを取得する方法は、このドキュメントの範囲外ですが、電話を root 化する方法によっては、工場出荷時設定へのリセットを伴います。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>そこに複数のウォレットがあり、どれが正しいかわからない場合は、各ウォレットの名前がファイルの末尾にクリア テキストで表示されます。&nbsp;&nbsp;例として、<a href="https://github.com/demining/CryptoDeepTools/tree/master/btcrecover/test/test-wallets">./btcrecover/test/test-wallets にあるこのリポジトリに含まれるテスト ウォレットを参照してください)</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ファイルを取得したら、BTCRecover で直接使用するか、抽出を作成できます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 extract-coinomi-privkey.py ../btcrecover/test/test-wallets/coinomi.wallet.android
Coinomi partial first encrypted private key, salt, n, r, p and crc in base64:
Y246uwodSaelErkb7GIYls3xaeX5i5YWtmh814zgsBCx+y8xgjp7Mul0TQBAAAAIAAEASAgdvw==
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="usage-for-dogechaininfo">Dogechain.info の使用方法</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>次に、以下のようなコマンドを使用して、ダウンロードしたウォレット ファイルから抽出スクリプトを作成できます。(リポジトリの一部であるサンプル ウォレット ファイルを使用します)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>python3 extract-dogechain-privkey.py ../btcrecover\test\test-wallets/dogechain.wallet.aes.json
Dogechain first 16 encrypted bytes, iv, and iter_count in base64:
ZGM6jJzIUd6i9DMEgCFG9JQ1/z4xSamItXAiQnV4AeJ0BwcZznn+169Eb84PFQ3QQ2JGiBMAAGL+4VE=
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="usage-for-electrum">エレクトラムの使い方</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>スクリプトをダウンロードした後、&nbsp;<strong>ウォレット ファイルのコピーを別のフォルダーに作成します</strong>&nbsp;(簡単にするために、抽出スクリプトと同じフォルダーにします)。Windows の例として、[スタート] メニューをクリックし、[ファイル名を指定して実行] をクリックしてから、次のように入力して、インストール後に Electrum によって作成された最初のウォレット ファイルを含むフォルダーを開きます&nbsp;<code>%appdata%\Electrum\wallets</code>。<code>default_wallet</code>ここから、通常は という名前のウォレット ファイルを別のフォルダにコピー アンド ペーストできます&nbsp;。次に、コマンド プロンプト ウィンドウを開いて、次のように入力する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-electrum2-partmpk.py default_wallet
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>上記の例では、Electrum 2.x ウォレットがあることを前提としています。代わりに Electrum 1.x ウォレットの場合は、&nbsp;&nbsp;<em>extract-electrum2-partmpk.pyを</em><em>extract-electrum-halfseed.py</em>&nbsp;に&nbsp;置き換えます。もちろん、ウォレットのファイル名も自分のものに置き換える必要があります。次のようなメッセージが表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>First half of encrypted Electrum seed, iv, and crc in base64:
ZWw6kLJxTDF7LxneT7c5DblJ9k9WYwV6YUIUQO+IDiIXzMUZvsCT
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>または、ウォレットの詳細に応じて、次のようになります。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_17" class="wp-block-code"><code>Electrum2 partial encrypted master private key, iv, and crc in base64:
ZTI69B961mYKYFV7Bg1zRYZ8ZGw4cE+2D8NF3lp6d2XPe8qTdJUz
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>あなた (または他の誰か) が&nbsp;<em>btcrecover</em>を実行して&nbsp;パスワードを検索する場合、ウォレット ファイルは必要なく、&nbsp;&nbsp;<em>extract-electrum-halfseed.py</em>からの出力のみが必要です。例を続けるには:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_18" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; ZWw6kLJxTDF7LxneT7c5DblJ9k9WYwV6YUIUQO+IDiIXzMUZvsCT
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="electrum-1x-technical-details">Electrum 1.x の技術詳細</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract-electrum-halfseed.py&nbsp;&nbsp;スクリプトは意図的に短く、Python プログラマーにとって読みやすいものになっています<em>。</em>Electrum 暗号化シードの長さは 64 バイトです。これには、16 バイトの AES 初期化ベクトルが含まれ、その後に 48 バイトの暗号化されたシード データが続きます。最後の 16 バイトはパディングです (つまり、実際のシード データは 32 バイトだけです)。このスクリプトは、16 バイトの初期化ベクトルと、実際のシード データの最初の 16 バイト (シードの 50%) だけを抽出します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>シードの半分しか抽出されないため、半シードが復号化された後でも秘密鍵を適切に再構築することはできません (パスワード検索が成功したと仮定します)。これらの 16 文字は、復号化されると 16 進数でエンコードされるため、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;それらを単独で使用してパスワードをチェックできます。各パスワードでバイトの復号化を試み、その結果が有効な 16 文字の長さの 16 進数でエンコードされた文字列になると、正しいパスワードが見つかりました。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ウォレット ファイルの残りの部分にアクセスできない場合、パスワードの推測と解読が成功した後でも、これらの 16 文字だけでビットコインの資金が危険にさらされる可能性はほとんどありません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="electrum-2x-technical-details">Electrum 2.x の技術詳細</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract-electrum2-partmpk.py&nbsp;スクリプトは意図的に短く、Python プログラマー<em>にとって</em>&nbsp;読みやすいものにします。Electrum 2.x で暗号化されたマスター秘密鍵 (mpk) の長さは 128 バイトです。これには、16 バイトの AES 初期化ベクトルが含まれ、その後に 112 バイトの暗号化された mpk データが続き、最後のバイトがパディングされます (つまり、111 バイトの実際の mpk データ)。これらの 111 バイトのうち、およそ 18 バイトがヘッダー、次の 44 バイトがチェーンコード、残りの 47 バイトが秘密鍵で構成されます。このスクリプトは、16 バイトの初期化ベクトルと mpk データの最初の 16 バイトのみを抽出します。これらはすべて機密性の低いヘッダー情報です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>復号化されると、これらの 16 文字は常に文字列「xprv」で始まり、残りは base58 でエンコードされます。btcrecover は&nbsp;<em>それら</em>&nbsp;を単独で使用してパスワードをチェックできます。各パスワードでバイトの復号化を試み、結果が期待どおりになると、正しいパスワードが見つかります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ウォレット ファイルの残りの部分にアクセスできなければ、復号化されたヘッダー情報によって資金が失われることはありません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-metamask">メタマスクの使い方</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Metamask には 2 つの抽出スクリプトがあり、拡張機能からすべてのボールト データ (古い上書きされたウォレットを含む) を抽出できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Chrome ベースのブラウザーの場合、ブラウザー拡張機能のデータ フォルダーを見つける必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Metamask の場合: %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\nkbihfbeogaeaoehlefnkodbefgpgknn\</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Binance Wallet Extension の場合: %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fhbohimaelbohpjbbldcngcnapndodjp\</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Ronin ウォレットの場合: %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fnjhmkhhmkbjkkabndcnnogagogbneec\</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>拡張機能データのパスは、他の Chrome ベースのブラウザー (Brave など) では少し異なりますが、一般的な場所と最終的なフォルダー名は同じです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>次に、以下のようなコマンドを使用して、その拡張機能のボールト データをすべて表示できます (ただし、独自のブラウザー拡張データへのパスを使用する必要がある場合を除きます)。</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_19" class="wp-block-code"><code>python3 extract-metamask-vaults.py ../btcrecover/test/test-wallets/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn
===== (Likely) Old Vault Data =====

{"data":"vXOTraxWuDmDrhxZ759NodhTmd4UQkThRG6YLvPt14OdZgnvJo4P5wj+LRupmb+7Vql+fOM5IF33Qb3FQvWro8Ro201M1YOH5zBdSwK6wzYmlFndlwqgOq61HSDUD9Ee1ccUF/iUgqJIngCw9/bRo93kpj11MuVonNOayTFztRc68+/JPCmIe0vqPYShRfJbeI8IBvauJdUxg6VqG0PId0Pw30ZO3f3QXmKFE+ZoibgbO111j7gQ0l7j6KdABeA=","iv":"7hvnbvsoSQmAbWzfvtMkjA==","salt":"13+DUqg893kPM0MiJz3bz2iYGAxPtPisX1JE1+be9IU="}

===== Current Vault Data =====

{"data":"Ny6zeXCgltvFkIWycZU3gYLocIM+gH/2m4fozdKdJxwff2BUHXaxBkaLDuzMs7WtazXJ+3P+XsFFG2W8+7tpNfCv2RCNNHWX9aVEBKeKEwQPUT6MD4rNU2XYykPROAcbdUPHKEVpaAEj+1VlCiMk1m3j7KhIHpt1cI7Qp8rV7lxzCUc5FWAWlc+gxvFTfSXOPJd0k23/F9MgRq0vn2h+UJolmLzpQFvEv2BUuL6CoEbog8Vn2N+ktypbR2pnNMA=","iv":"H82DrVooOndR7fk1SKKGwQ==","salt":"cxp0pRtsgyUBjll6MktU2HySubrtnMaPXAwaBsANA1Y="}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Firefox の場合、https://metamask.zendesk.com/hc/en-us/articles/360018766351-How-to-use-the-Vault-Decryptor-with で説明されているプロセスを使用して、Metamask ボールトを取得する必要があります。 -the-MetaMask-Vault-Data</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ボールト データを取得したら、それをテキスト ファイルに入れ、BTCRecover で直接使用するか、抽出を作成することができます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_20" class="wp-block-code"><code>python3 extract-metamask-privkey.py ../btcrecover/test/test-wallets/metamask.9.8.4_firefox_vault
Metamask first 16 encrypted bytes, iv, and salt in base64:
bXQ6bB5JP1EW0xwBmWZ9vI/iw9IRkorRs9rI6wJCNrd8KUw61ubkQxf9JF9jDv9kZIlxVVkKb7lIwnt7+519MLodzoK0sOw=
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="usage-for-msigna">mSIGNAの使い方</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>スクリプトをダウンロードした後、&nbsp;<strong>ウォレット ファイルのコピーを別のフォルダーに作成します</strong>&nbsp;(簡単にするために、抽出スクリプトと同じフォルダーにします)。Windows の例として、[スタート] メニューをクリックし、[ファイル名を指定して実行] をクリックしてから、次のように入力して、通常はウォレット ファイルを含むフォルダーを開きます&nbsp;<code>%homedrive%%homepath%</code>。<code>.vault</code>&nbsp;ここから、ウォレット ファイル (ファイル) を別のフォルダーにコピー アンド ペーストできます&nbsp;。次に、コマンド プロンプト ウィンドウを開いて、次のように入力する必要があります (ダウンロードしたスクリプトの場所に応じて、ウォレット ファイルに名前が付けられ、&nbsp;<code>msigna-wallet.vault</code>&nbsp;同じフォルダーにあると仮定します)。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_21" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-msigna-partmpk.py msigna-wallet.vault
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>次のようなメッセージが表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_22" class="wp-block-code"><code>mSIGNA partial encrypted master private key, salt, and crc in base64:
bXM6SWd6U+qTKOzQDfz8auBL1/tzu0kap7NMOqctt7U0nA8XOI6j6BCjxCsc7mU=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>あなた (または他の誰か) が&nbsp;<em>btcrecover</em>を実行して&nbsp;パスワードを検索する場合、ウォレット ファイルは必要なく、&nbsp;&nbsp;<em>extract-msigna-partmpk.py</em>からの出力のみが必要です。例を続けるには:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_23" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; bXM6SWd6U+qTKOzQDfz8auBL1/tzu0kap7NMOqctt7U0nA8XOI6j6BCjxCsc7mU=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="msigna-technical-details">mSIGNA 技術詳細</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>extract-msigna-partmpk.py</em>スクリプト&nbsp;&nbsp;は意図的に短く、Python プログラマーにとって読みやすいものになっています。mSIGNA で暗号化されたマスター秘密鍵の長さは 48 バイトです。これには、32 バイトの暗号化された秘密鍵データが含まれ、その後に 16 バイトの暗号化されたパディングが続きます (チェーンコードは個別に保存されます)。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>秘密鍵の最後の半分のみが抽出されるため、秘密鍵のこの半分を復号化できたとしても、ウォレットを適切に再構築することはできません (パスワード検索が成功した場合)。パディングの残りの 16 バイトは、復号化されると予測可能であり、これにより、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;それを使用してパスワードをチェックできます。各パスワードでバイトの暗号化を解除しようとし、有効なパディングが得られると、正しいパスワードを見つけたことになります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ウォレット ファイルの残りの部分にアクセスできなければ、復号化されたパディングによって資金が失われることはありません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-multibit-classic">MultiBit Classic の使用法</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong><em>警告:</em></strong><code>extract-multibit-privkey.py</code>&nbsp;以下で説明するように、MultiBit Classic キー ファイルでスクリプトを&nbsp;&nbsp;使用すると&nbsp;<em>、誤検出につながる可能性</em>があります。<em>btcrecover が</em>&nbsp;パスワードを見つけたが間違っていると報告した&nbsp;場合、偽陽性が発生します&nbsp;。&nbsp;<em>表示されるパスワードは正しくない可能性があります。</em>多数のパスワード (約 100 億 (10,000,000,000) 以上) をテスト&nbsp;<strong>する</strong>&nbsp;場合&nbsp;&nbsp;は&nbsp;<em>、</em>&nbsp;.<em></em><strong></strong><em></em><code>extract-multibit-privkey.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>btcrecover は</em>&nbsp;、MultiBit ウォレット ファイルを直接操作するのではなく、MultiBit 秘密鍵のバックアップ ファイルを操作します。初めて MultiBit ウォレットにパスワードを追加した後、新しい受信アドレスを追加するか、ウォレットのパスワードを変更するたびに、MultiBit は暗号化された秘密鍵のバックアップ ファイルをウォレット ファイルの近くのディレクトリに作成します&nbsp;<code>key-backup</code>&nbsp;。これらの秘密鍵のバックアップ ファイルは、パスワードの試行がはるかに高速であるため (1,000 倍以上)、&nbsp;&nbsp;<em>btcrecover が</em>&nbsp;それらを使用する理由です。MultiBit を最初にインストールしたときに作成されるデフォルトのウォレットの場合、このディレクトリは次の場所にあります。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_24" class="wp-block-code"><code>%appdata%\MultiBit\multibit-data\key-backup
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>キー ファイルの名前は&nbsp;<code>walletname-20140407200743.key</code>.&nbsp;追加のウォレットを作成した場合、それらの&nbsp;<code>key-backup</code>&nbsp;ディレクトリは別の場所に配置され、それらを見つけるのはあなた次第です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>MultiBit 秘密鍵のバックアップ ファイルの場所の詳細については、https:&nbsp;&nbsp;<a href="https://www.multibit.org/en/help/v0.5/help_fileDescriptions.html">//www.multibit.org/en/help/v0.5/help_fileDescriptions.htmlを参照してください。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>正しい MultiBit 秘密鍵のバックアップ ファイルを見つけたら、&nbsp;<strong>それを別のフォルダーにコピーします</strong>&nbsp;(簡単にするために、extract スクリプトと同じフォルダーにコピーします)。Windows の例として、[スタート] メニューをクリックし、[ファイル名を指定して実行] をクリックし、これを入力して、MultiBit が作成する最初のウォレットの秘密鍵バックアップ フォルダーを開きます (ただし、これは必要なフォルダーではない可能性があります)。 :&nbsp;&nbsp;<code>%appdata%\MultiBit\multibit-data\key-backup</code>.&nbsp;ここから、秘密鍵のバックアップ ファイルを別のフォルダーにコピー アンド ペーストできます。次に、コマンド プロンプト ウィンドウを開き、次のように入力する必要があります (ダウンロードしたスクリプトの場所に応じて、秘密鍵ファイルのコピーを同じフォルダーに作成したと仮定します)。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_25" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-multibit-privkey.py multibit-20140407200743.key
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>もちろん、秘密鍵のファイル名を自分のものに置き換える必要があります。結果として、次のようなメッセージが表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_26" class="wp-block-code"><code>MultiBit partial first encrypted private key, salt, and crc in base64:
bWI6sTaHldcBFFj9zlgNpO1szOwy8elpl20OWgj+lA==
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>あなた (または他の誰か) が&nbsp;<em>btcrecover</em>を実行して&nbsp;パスワードを検索する場合、ウォレット ファイルや秘密鍵ファイルは必要なく、&nbsp;&nbsp;<em>extract-multibit-privkey.py</em>からの出力のみが必要です。例を続けるには:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_27" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; bWI6sTaHldcBFFj9zlgNpO1szOwy8elpl20OWgj+lA==
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="multibit-classic-technical-details">MultiBit Classic 技術詳細</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>警告:</strong>&nbsp;&nbsp;MultiBit Classic データ抽出の誤検出率は、約 1/3×10&nbsp;<sup>11</sup>です。詳細については、上記の警告を参照してください。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>extract-multibit-privkey.py&nbsp;スクリプトは意図的に短く、Python プログラマー<em>にとって</em>&nbsp;読みやすいものになっています。このスクリプトは、MultiBit 秘密鍵バックアップ ファイルの最初の秘密鍵から、パスワード ソルトの 8 バイトに加えて、暗号化された base58 でエンコードされた最初の 16 文字 (52 のうち) を抽出します。抽出されるのは 1 つの秘密鍵の 34% 未満であるため、これらの最初の 16 バイトが復号化された後でも (パスワード検索が成功すると仮定して) 秘密鍵自体を適切に再構築することはできません。これらの 16 文字は復号化されると base58 でエンコードされるため、&nbsp;&nbsp;<em>btcrecover は</em>&nbsp;それらを単独で使用してパスワードをチェックできます。各パスワードを使用してバイトの復号化を試み、結果が有効な 16 文字の長さの base58 エンコードされた秘密鍵プレフィックスになると、正しいパスワードが見つかりました。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>秘密鍵のバックアップ ファイルやウォレット ファイルの残りの部分にアクセスできなくても、これらの 16 文字だけで、パスワードの推測と解読が成功した後でも、ビットコインの資金が危険にさらされることはありません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-multibit-hd">MultiBit HD の使用法</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>スクリプトをダウンロードしたら、&nbsp;&nbsp;<strong>mbhd.wallet.aes ファイルのコピーを別のフォルダーに作成します</strong>&nbsp;(簡単にするために、&nbsp;&nbsp;<em>extract-multibit-hd-data.py</em>と同じフォルダーに作成します)。Windows の例として、[スタート] メニューをクリックし、[ファイル名を指定して実行] をクリックして、次のように入力します&nbsp;<code>%appdata%\MultiBitHD</code>。ここからウォレット フォルダーを開き、mbhd.wallet.aes ファイルをコピーして別のフォルダーに貼り付けることができます。次に、コマンド プロンプト ウィンドウを開いて、次のように入力する必要があります (ダウンロードしたスクリプトの場所に応じて、同じフォルダーに mbhd.wallet.aes のコピーを作成したと仮定します)。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_28" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-multibit-hd-data.py mbhd.wallet.aes
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>結果として、次のようなメッセージが表示されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_29" class="wp-block-code"><code>MultiBit HD first 16 bytes of encrypted wallet and crc in base64:
bTI6LbH/+ROEa0cQ0inH7V3thbdFJV4=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>あなた (または他の誰か) が&nbsp;<em>btcrecover</em>を実行して&nbsp;パスワードを検索する場合、ウォレット ファイルは必要なく、&nbsp;&nbsp;<em>extract-multibit-hd-data.py</em>からの出力のみが必要です。例を続けるには:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_30" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; bTI6LbH/+ROEa0cQ0inH7V3thbdFJV4=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="multibit-hd-technical-details">MultiBit HD の技術詳細</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract&nbsp;&nbsp;<em>-multibit-hd-data</em>&nbsp;スクリプトは意図的に短く、Python プログラマーにとって読みやすくなっています。MultiBit HD ウォレット ファイルは完全に暗号化されています。抽出スクリプトは、ウォレット ファイルから最初の 32 バイトを読み取るだけです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これらの 32 バイトはオプションで (MultiBit HD v0.5.0 以降)、16 バイトの AES 初期化ベクトルで始まり、その後に bitcoinj ウォレット ファイルのヘッダー バイト、具体的にはバイト文字列「\x0a?org.bitcoin」が続きます。復号化されると (? には任意のバイトを指定できます)。各パスワードでバイトの復号化を試み、結果が期待どおりになると、正しいパスワードが見つかります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ウォレット ファイルの残りの部分にアクセスできなければ、復号化されたヘッダー情報によって資金が失われることはありません。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/17BTCRecoverCryptoGuide" target="_blank" rel="noreferrer noopener">ソースコード</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">テレグラム: https://t.me/cryptodeeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/imTXE4rGqHw" target="_blank" rel="noreferrer noopener">ビデオ: https://youtu.be/imTXE4rGqHw</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/btc-recover-crypto-guide" target="_blank" rel="noreferrer noopener">ソース: https://cryptoeep.ru/btc-recover-crypto-guide</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1320} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/027-1024x576.png" alt="BTC 回復暗号ガイド" class="wp-image-1320"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
