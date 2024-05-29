# コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します

<!-- wp:embed {"url":"https://www.youtube.com/embed/NrQ3oNxlrlU","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/NrQ3oNxlrlU
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>前回の記事<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">「ブロックチェーン攻撃ベクトルとスマート コントラクトに対する脆弱性」では、ブロックチェーンに対するすべての既知の攻撃を確認しました。この記事では、暗号の脅威について再度説明し、コールド</a><a href="https://cryptodeeptech.ru/cold-and-hot-wallets" target="_blank" rel="noreferrer noopener">ウォレットとホット ウォレットの脆弱性の特定</a>について説明します。<a href="https://cryptodeeptech.ru/cold-and-hot-wallets" target="_blank" rel="noreferrer noopener">財布</a>。ブロックチェーンは、分散型台帳で構成される基礎となる技術レイヤーであり、コンセンサス アルゴリズムに参加する分散ノードが多数存在するため、非常に安全なデータ構造です。ブロックチェーンをハッキングするために、ハッカーは多くの分散ノードの脆弱性を悪用する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ブロックチェーンの基本的なセキュリティの前提は、非常に多くのノードをハッキングしてブロックチェーンの状態を変更することは不可能だということです。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2><strong>ブロックチェーン技術が非常に安全である場合、どのようにハッキングされる可能性があるでしょうか?</strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>このテクノロジーのアキレス腱は、クライアントのために大量の暗号資産 (お金) を管理する機関ユーザーの集中型の性質であり、お金とハッカーの間に残る唯一のものは秘密鍵&nbsp;<em>です</em>。秘密鍵は、従来の小切手に署名するために手動署名を使用できるのと同じ方法で、ブロックチェーン トランザクションに署名するために使用する必要があります。誰かが機関の秘密鍵を盗んだ場合、その機関に代わってトランザクションを作成し、お金を盗むことができます。銀行システムとは異なり、ハッキングされたトランザクションが作成されると元に戻す方法はありません。お金は文字通り盗まれます。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>秘密鍵を保管して保護することが重要なのはなぜですか?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>秘密鍵を保持する人は誰でも、その鍵に関連付けられた資産を完全に制御できます。ブロックチェーン トランザクションは瞬時に取り消せないため、ユーザーは自分の秘密鍵を秘密にしようとします。秘密鍵は 1 回しか生成されないため、秘密鍵を置き忘れると、そのアドレスに関連付けられたすべての暗号資産が事実上役に立たなくなります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最適な保管シナリオはまだ定義されていませんが、秘密鍵の管理が最優先事項であることは議論の余地がありません。実際、秘密鍵は本質的に実物資産です。その固有の特性と力は、例外なく真に保護する方法がないことを意味します。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>コールドウォレット</strong>&nbsp;「機関カストディアンの金庫」は、ビットコインやその他の暗号通貨を最初に保管するハードウェアデバイスであり、インターネットから分離されたデバイスです。理論的には、コールド ウォレット ソリューションは、暗号通貨を保管する最も安全な方法であると報告されています。<a href="https://cryptodeeptech.ru/cold-and-hot-wallets/#/news-room/what-is-asset-management/">一部の暗号通貨ユーザーは、デジタル資産を</a>物理的な「ウォレット」に保管することを好みます&nbsp;&nbsp;。ほとんどの場合、USB スティックのようなデバイスです。コンピューターに直接接続することによってのみアクセスでき、ユーザーが暗号通貨の資金にアクセスして移動するにはインターネット接続が必要です。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1804} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-vs-cold-wallet-1-1024x916.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1804"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Trezor、Ledger Nano S などの商業用の人気のあるコールド ウォレットがいくつかあります。また、企業や機関投資家向けには、以下の組み合わせを使用する他のデバイスもあります。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>USB</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>イーサネット</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SDカード</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>外付けサムドライブ</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>HSM を備えた専用のエア ギャップ マシン</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>上記のハードウェアに関連する問題は使いやすさであり、暗号資産にアクセスするには、コールドウォレットをコンピューターに接続する必要があるため、インターネットに公開されます.&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">そうすることで、インターネット接続を介してコールド ウォレット システムが侵害され、潜在的な攻撃ベクトル</a>にさらされ、最終的には潜在的なサイバー盗難にさらされることになります。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>コールド ウォレット ストレージを使用することは、特に大量のビットコインやその他の暗号資産を扱う場合に必要なセキュリティ対策です。たとえば、仮想通貨取引所や仮想通貨ファンドのカストディアンは、通常、即時の引き出しを提供し、何十万ものビットコインやその他の仮想資産を管理している可能性があります。ハッカーがセキュリティ違反で準備金全体を盗む可能性を最小限に抑えるために、金融サービス事業者は標準的なプロトコルに従い、準備金の大部分をコールド ストレージに保管し、日常的に利用できる資産の割合を少なくし&nbsp;<em>ます</em>。貿易活動。&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本的に、彼らはデジタル資産の秘密鍵の大部分をサーバーやその他の接続されたコンピューターに保存しません。サーバーに保持される唯一の金額は、予想される顧客の引き出しをカバーするために必要な最小額です。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>デジタル資産の秘密鍵を保護するために使用される方法:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>強力なパスワードでウォレットを保護するデータ暗号化</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コンピュータのクラッシュや詐欺に備えたデジタルウォレットのバックアップ</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>コールドウォレットは、ある時点で資金を送信する必要があり、そうすることで双方向通信に依存し、インターネットに接続されるため、真に安全ではありません.&nbsp;これは、侵害されて悪意のあるデータに感染し、<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">攻撃に対して非常に脆弱になる</a>可能性がある場合です。したがって、すべてのコールド ウォレットはホット ウォレットになり、機関のカストディアンに対する完全なセキュリティの理論は払拭されます。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>今日、ホットウォレットは</strong>&nbsp;資金への簡単なアクセスと自動取引の処理を可能にする重要な役割を担っていますが、ホットウォレットの秘密鍵は常にインターネットに接続されている必要がある方法で保管されています。秘密鍵の保管方法が異なるさまざまなタイプのホットウォレットがあります。数学的な観点では、異なる参加者間で秘密鍵を複製するものもあれば、参加者間で秘密鍵を分割するものもあります。言い換えれば、今日のホット ウォレットは、秘密鍵を配布することでセキュリティ リスクに対処しています。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ホット ウォレットの参加者は秘密鍵の管理を維持するため、ホット ウォレット内の暗号通貨資産は保持者の管理下に置かれます。ただし、理論的には、コンピューターやスマートフォンにアクセスできる悪意のある人物やグループは、秘密鍵へのアクセスを介してウォレットを流出させる可能性があるため、資産はハッキングに対して脆弱なままです.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ホットウォレットの主な利点は、自動で高速なアクセス取引に使用できることです。仮想通貨資産で実際に購入しようとしている個人は、たとえば、ホットウォレットの使用を選択する可能性があります。そのウォレットの保有物はインターネット経由で転送可能であり、一般に、仮想通貨の数は十分に高い価値があるためです。ハッカーが盗むために投資する時間とお金の価値はありません。一方、ホットウォレットはインターネットに継続的にアクセスしているため、セキュリティ侵害に対して確実に脆弱です.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>さまざまな種類のホット ウォレットはすべて、インターネットに接続されたアプリケーションに秘密鍵を保存します。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>Basic Hot wallet – インターネット上での秘密鍵の直接接続&nbsp;</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>マルチシグ ネイティブ ウォレット – 秘密鍵を複製 – アクセスするには、2 人の参加者を侵害するだけで済みます</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>マルチパーティ計算 (MPC) – 秘密鍵を 2 ～ 5 人の参加者に配布します</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>特定のトランザクションを確認しなければならない 2 ～ 3 人またはエンティティがある場合でも、マルチシグ方式を見ると、ハッカー グループは機関の標的に数百万ドルを費やし、セキュリティを侵害するために 3 つのうち 2 つの攻撃ベクトルのみを必要とします<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">。</a>ハッカーグループは、盗まれた暗号資産で数億ドルを獲得する立場にあるため、喜んでこれを行います.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>MPC 手法でさえ、さまざまな攻撃ベクトルに対して脆弱です。MPC アプローチでは、複数の非信頼コンピューターがそれぞれ、より大きなデータ セットの独自のフラグメントに対して計算を実行し、1 つのノードが他のフラグメントの詳細を知らなくても、望ましい共通の結果を集合的に生成できます。トランザクションを実行する秘密鍵は、集合的に生成された値です。MPC の支持者は、単一のコンピューターが実際のキーを担当することは決してないと主張しています。&nbsp;<a href="https://cryptodeeptech.ru/cold-and-hot-wallets/#/product/">MPC ベースのウォレットは、</a>&nbsp;市場に出回っているハードウェアまたは<a href="https://en.bitcoin.it/wiki/Multisignature">&nbsp;マルチシグ ウォレット</a>&nbsp;に対するより優れたソリューションであると言われています。それらはより安全で完全にオフチェーンであることが数学的に証明されており、柔軟性が高く、一般的に台帳に依存しません。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>残念ながら、複数のデバイスにフラグメントが存在する場合でも、完全に安全なソリューションとは言えません。巧妙なハッカーがマシンのクラスター内に長く留まり、キーを追跡して再構築できる可能性があるからです。1 台の従業員のマシンまたはサーバーを侵害できた場合、ネットワーク内を横方向に移動して、署名方法の一部である他のデバイスを侵害することができます。したがって、ハッカーグループはこの方法の脆弱性を見つけるのに十分なほど洗練されており、数十億ドルを盗むために数百万ドルを費やすことを厭わないため、これは誤りであることが証明される可能性があります.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>上記のソリューションを使用すると、不正な従業員がオンサイト、冷蔵施設、または会社によって完全に管理されているハードウェア デバイスからキーを盗むことを基本的に防ぐことができます。攻撃者や不正な従業員が単一のネットワークに侵入し、承認して違法なトランザクションに署名するために必要なすべての暗号化情報を収集することを制限しようとする mpc ウォレット プロバイダーがありますが、このソリューションも 100% 安全ではなく、単に数十億ドルが危機に瀕している場合、<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">攻撃ベクトルを軽減する</a>ことは選択肢ではありません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2><strong>なぜ業界は気にする必要があるのですか？&nbsp;</strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>この記事を書いている時点で、仮想通貨の時価総額は 2,180 億ドルを超えており、現在では 10 年目を迎えています。この 10 年間で、注目に値するハッキングが数多く発生しました。大量の暗号資産を保管しているすべての機関は、投資家に対して、最も堅牢なセキュリティ オプションが企業全体に展開されるようにする責任があります。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>さらに、ハッキングは他のさまざまなサイバー被害にもつながります</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>資産の盗難 - 取り返しのつかない</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>風評被害</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>個人顧客データの盗難</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>失業</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>事業の閉鎖</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>違う記事だけど…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>市場には FOMO やメディアの誇大宣伝に一部起因するボラティリティがたくさんありますが、主要な要因はデジタル資産のセキュリティであり、これが暗号通貨の価値や交換資産の評価に影響を与える可能性があることを認識することが重要です。生態系全体を根本的に変えます。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>重要ポイント:</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>ホットウォレットは常にインターネットに接続されています。そのため、オンライン攻撃を受けやすくなりますが、日常的な使用にはより便利です。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ほとんどの場合、コールド ウォレットはインターネットに接続されていません。そのため、オンライン攻撃を受ける可能性は低くなりますが、通常の使用にはあまり便利ではありません.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ウォレットを選択するときは、セキュリティ、利便性、手数料、サポートされているコイン、および保険の要素を考慮する必要があります。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>デジタル アセットの購入を計画している場合、それらを保存する方法と場所を決定することはオプションではなく、必須です。法定通貨とは異なり、&nbsp;<a href="https://www.coingecko.com/" target="_blank" rel="noreferrer noopener">暗号通貨は</a><a href="https://www.coingecko.com/learn/what-is-a-blockchain" target="_blank" rel="noreferrer noopener">ブロックチェーン</a>&nbsp;上に存在し&nbsp;&nbsp;、ウォレットと呼ばれる適切なストレージ プラットフォームが必要です。<a href="https://www.coingecko.com/learn/what-are-public-and-private-keys" target="_blank" rel="noreferrer noopener">これらのウォレットを使用すると、公開鍵と秘密鍵</a>を使用して暗号資産にアクセスできます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>公開鍵を使用して暗号通貨を送受信し、秘密鍵を使用してトランザクションを確認し、暗号ウォレットの所有権を証明します。公開鍵は銀行口座番号、秘密鍵は暗証番号と考えることができます。ホット ウォレットとコールド ウォレットの主な違いは、前者はプライベート キーをオンラインで保存し、後者はオフラインで保存することです。&nbsp;&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この記事では、ホット ウォレットとコールド ウォレットの議論、ウォレットを選択する際の考慮事項、ホット ウォレットとコールド ウォレットの両方を使用して仮想通貨ポートフォリオを管理する方法について詳しく説明します。&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="1">ホットウォレットとは？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ホットウォレットは、公開鍵と秘密鍵をオンラインで保管するソフトウェアウォレットです。インターネットに接続しているパソコンやスマートフォンからアクセスできます。ホットウォレットは、使用するためにプラグを差し込んだり抜いたりする必要がないため、毎日の使用に便利です。必要なのはインターネット接続だけです。また、通常は無料でダウンロードして使用でき、誰でも簡単に始められるユーザー フレンドリーなインターフェイスを備えています。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ホット ウォレットは公開鍵と秘密鍵をオンラインで保存するため、&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">攻撃に対して脆弱であり、フィッシングやその他の</a><a href="https://www.coingecko.com/learn/complete-guide-to-bitcoin-scams" target="_blank" rel="noreferrer noopener">詐欺など</a>のリスクにさらされます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>ホットウォレットの種類</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ホット ウォレットには 2 つのタイプがあります。ユーザーが、ユーザーの資金の管理者として機能する集中型取引所で口座を開設する取引所ベースと、非管理型ソフトウェア ホット ウォレットです。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="2">取引所ベースのウォレット</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>取引所ベースのウォレットは、集中型取引所の一部です。集中型取引所は、ユーザーのアドレスへの秘密鍵を保持する保管機関です。これは、そのような保管金融プラットフォームの顧客は、資産が機関によって保持されているホットウォレットとコールドウォレットに預け入れられているため、資産を完全に保管していないことを意味します.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>残念ながら、これにより、2022 年 11 月の FTX の場合に見られるように、取引所が特定の活動に従事し、その結果、顧客の資金が失われるリスクにユーザーがさらされます。<a href="https://www.coingecko.com/learn/what-is-proof-of-reserves-por" target="_blank" rel="noreferrer noopener">Proof of Reserves</a>の導入により、保管機関に顧客のトークンの責任を負わせます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>集中型の取引所活動は全体的に減少していますが、取引所ベースのウォレットは、ユーザーが法定通貨で暗号通貨を簡単に売買できるため、特に個人投資家の間で依然として人気があります。また、ログイン情報を紛失した場合は、取引所のカスタマー サービスに連絡することで、ウォレットへのアクセスを復元できます。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1786} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/Main-Table-4-1024x673.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1786"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="3">非カストディアル ソフトウェア ホット ウォレット</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>非カストディアル ソフトウェア ホット ウォレットには、モバイル、ブラウザ、またはデスクトップ アプリケーションからアクセスできます。ほとんどの場合、これらは 3 つすべてで利用できます。これらのホット ウォレットの場合、ユーザーは自分の秘密鍵を管理し、資金を完全に管理できます。これは、資金が管理機関に保管されていないため、銀行が取り付けられた場合でも資金が安全であることを意味しますが、シード フレーズを失うと、ウォレットとその中に保管されている暗号にアクセスできなくなります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="4">シードフレーズとは？</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>シード フレーズは、リカバリ フレーズとも呼ばれます。これは、オンチェーンの暗号資産を回復するためのマスター キーとして使用できる 12、18、または 24 語のランダムなリストです。シード フレーズは秘密鍵を生成し、それを使用して公開鍵を生成します。通常、ウォレット ソフトウェアはシード フレーズを生成し、安全に保管する前にそれを書き留めるようにユーザーに指示します。シード フレーズは、ユーザーのウォレットへのアクセスをロック解除するためのマスター キーとして機能するため、安全に保管し、オンラインにしないようにする必要があります。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>シード フレーズを保存する場合は、時間の経過とともに色あせたり、水や火によって破壊される可能性のある紙に書き留めたりしないでください。代わりに、暗号鋼を使用してシード フレーズを録音し、バックアップとして複数のコピーを作成します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>シード フレーズをパスワード マネージャーやオンラインまたはデバイスに保存しないでください。これには、写真を撮ったり、Google ドキュメントやメモに入れたりしないことも含まれます。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1788} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/content_Main_Table_12.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1788"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 id="5">ホットウォレットの例</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>MetaMask – イーサリアム エコシステムの探索に最適&nbsp;</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://www.coingecko.com/learn/complete-beginners-guide-to-metamask" target="_blank" rel="noreferrer noopener">MetaMask は</a>&nbsp;、暗号空間で最も人気のあるホット ウォレットの 1 つであり、すべての&nbsp;<a href="https://www.coingecko.com/learn/ethereum-virtual-machine-evm" target="_blank" rel="noreferrer noopener">EVM 互換</a>&nbsp;トークンをサポートしています。使い方は簡単で、デスクトップとモバイル デバイスで利用できます。さらに、暗号の交換、送信、受信、および&nbsp;ネットワーク全体での<a href="https://www.coingecko.com/en/nft" target="_blank" rel="noreferrer noopener">非代替トークン (NFT) の</a>収集のための追加の組み込み機能があります&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>取引所ベースのウォレット – 簡単なフィアット オンランプ</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Exchange ベースのホット ウォレットは MetaMask に似ており、主にデスクトップおよびモバイル デバイスをサポートしています。取引所ベースのウォレットは、ほとんどの銀行に接続して簡単なオンボーディングを保証し、新しい暗号ユーザーがブローカーの代わりに銀行口座を使用して暗号を直接購入できるようにします。ウォレット サービスを使用するには、取引所でアカウントを開設する必要がある場合もあれば、開設しない場合もあります。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ただし、前述のように、これらの取引所ベースのウォレットはカストディアルです。つまり、取引所は本質的にあなたの秘密鍵とコインを保持し、必要なときにコインを引き出すことができることを約束します.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Exodus – デスクトップに最適</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://www.exodus.com/" rel="noreferrer noopener" target="_blank">Exodus</a>&nbsp;は、高いトランザクション速度、使いやすさ、多様なクライアント機能を備えているため、デスクトップに最適なホット ウォレットです。これは、暗号空間で最も視覚的に魅力的で直感的なウォレットの 1 つです。デスクトップ専用のウォレットとして始まりましたが、モバイル デバイスをサポートするように拡張されました。ただし、Windows、Linux、および Mac オペレーティング システム用の Exodus デスクトップ アプリは、依然としてウォレットの主要な製品です。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="6">コールドウォレットとは？&nbsp;</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>コールドウォレットまたはハードウェアウォレットは、秘密鍵をオフラインで保存する物理デバイスで、50 ドルから 250 ドルの費用がかかります。コールドウォレットは、インターネットに接続されていないため、ハッカーによって侵害される可能性が低いため、最も安全なタイプの暗号ウォレットです (秘密鍵とハードウェアウォレットにアクセスできない限り)。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ハードウェア ウォレットは、USB スティックやハード ドライブに似た物理デバイスであり、デバイス自体にパス コード、PIN、秘密鍵を保存することで機能します。実際、コンピュータがマルウェアに感染したとしても、秘密鍵がインターネットに接続されることのないチップに保持されているため、コールド ウォレットは安全なままです。そのため、コンピューターがハッキングされたり、オンライン ウォレットが危険にさらされたりしても、パスコードとデバイスが盗まれない限り、コインは安全です。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ただし、コールドウォレットは物理的なオブジェクトであるため、不注意な取り扱いによる損失のリスクにもさらされています。暗号ハードウェア ウォレットが紛失または盗難にあった場合、シード フレーズを使用して秘密鍵を再生成できます。そのため、シード フレーズを安全に、オフラインで、ハード コピーに保管することを忘れないでください。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>コールド ウォレットは長期的な仮想通貨の保管に理想的であるため、取引資金よりも仮想通貨の保管に適しています。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1790} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/Main-Table-9-1024x673.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1790"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="7">&nbsp;</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>元帳</h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1792} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/content_image_265.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1792"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>出典：レジャーナノX</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://gcko.io/ledger">Ledger</a>&nbsp;は最も人気のある暗号ハードウェア ウォレット プロバイダーの 1 つで、Ledger Nano X、Ledger Nano S、Ledger Nano S plus ウォレットを提供しています。これらのデバイスは、Blockchain Open Ledger Operating System と呼ばれる Ledger オペレーティング システム上で実行されるサム ドライブほどの大きさです。また、内蔵の透明なOLEDディスプレイ画面インターフェースと、トランザクションを確認するための2つのナビゲーションボタンも備えています.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Ledgerには、Ledger Liveモバイルアプリと、暗号データ​​の保存に使用されるセキュアエレメントチップによる高レベルのセキュリティが備わっています。同社の主力モデルである Ledger Nano X は、5,500 を超えるトークンの暗号通貨互換性を提供します。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>安全</h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1793} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/10712964857906.jpg" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1793"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://shop.trezor.io/product/trezor-model-t?offer_id=15&amp;aff_id=1143">Trezor は</a>&nbsp;、Trezor One と Trezor Model T を提供するもう 1 つの有名なハードウェア ウォレットです。Trezor Model T は、1,456 のコインとトークンとの互換性を提供し、デスクトップ、ブラウザー、および Android Trezor Suite が付属しています。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Trezor Suite は、暗号通貨の検索と購入、保有管理、暗号通貨の安全な送信を可能にするユーザー インターフェースです。これによりユーザー エクスペリエンスが向上しますが、インターネット対応デバイスを使用しているため、セキュリティの脆弱性が生じる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="8">ウォレットを選択する際の考慮事項</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>必要に応じて、ホット ウォレット、コールド ウォレット、またはその両方を選択できます。上記の 3 種類のウォレットの比較を次の表にまとめました。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1794} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/Main-Table-11-1024x436.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1794"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>安全</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>セキュリティは、暗号ウォレットを選択する際のコア機能です。ブロックチェーン技術は、その安全で不変の性質で知られています。ウォレットが最高のセキュリティ機能を備えていることを確認する必要があります。コールド ウォレットは、常にインターネットに接続されているとは限らず、フィッシングやその他のハッキングや詐欺などの潜在的なサイバーセキュリティ リスクにさらされているわけではないため、ホット ウォレットよりも安全です。さらに、資産への不正アクセスを防ぐために、ウォレットに 2 要素認証 (2FA) 機能があることを確認してください。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>快適&nbsp;</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>コールド ウォレットは秘密鍵をオフラインで保存するため、物理デバイスを接続し、ウェブベースのアカウントにリンクして資金を転送する必要があります。一方、ホットウォレットはオンラインに存在します。そのため、デイトレードなどの日常の取引にはるかに簡単に使用できます。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>追加取引手数料</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>使用しているウォレットに関係なく、引き続きガス料金が発生します。ただし、取引所ベースのウォレットには、ガス価格から派生した追加料金が含まれる場合がありますが、取引所のネイティブ トークンを保持またはステーキングしている場合、この料金は免除される場合があります。ウォレットをダウンロードまたは購入する前に、まずサービス料金を確認してください。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>対応コイン</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>使用する予定のウォレットは、投資したいコインをサポートしていない可能性があります。一部のウォレットでは、1 つのコインしかサポートされていません。たとえば、<a href="https://wallet.mycelium.com/" rel="noreferrer noopener" target="_blank">Mycelium</a>を考えてみましょう&nbsp;。優れた機能を備えているにもかかわらず、ビットコインのみをサポートしています。したがって、失望を避けるために、ウォレットを使用する前に、サポートされているコインとトークンのリストを必ず確認してください。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>保険</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>一部のカストディアンは、技術的な問題や盗難によって損失を被ったユーザーに資産保険を提供しています。カストディアンによって保険契約は異なりますが、金融機関と協力して資産を保証するものを選択することをお勧めします。たとえば、Binance は、米国の顧客に対して最大 250,000 ドルの米ドル預金に対する保険を提供しています。&nbsp;このポリシーを実施するために、<a href="https://www.fdic.gov/" rel="noreferrer noopener" target="_blank">連邦預金保険公社 (FDIC)</a>と提携しています&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="9">ホットウォレットとコールドウォレットを使用して暗号ポートフォリオを管理する</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ホットウォレットは、コールドウォレットよりも日常使いに便利です。一方、コールド ウォレットは、ホット ウォレットよりも最大限のセキュリティを保証します。どちらのウォレットも、幅広い暗号通貨をサポートしています。したがって、ウォレットを定期的に使用する利便性よりも資金の安全性を優先するかどうかによって、理想的なウォレットが決まります。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>両方の方法を組み合わせることで、両方のメリットを享受できます。たとえば、取引目的で資金のごく一部をホット ウォレットに保持し、残りの資金を長期投資としてコールド ウォレットに保持することができます。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ブロックチェーンネットワークの参加者として、当事者はいわゆる「ウォレット」に依存して、アカウントとブロックチェーンとのやり取りを管理できます。パーティーには複数のキーがあります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>問題</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>パーティのウォレットは、鍵の盗難につながる<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">悪意のある攻撃に対して脆弱です。</a>侵害された場合、攻撃者はキーを使用して、その当事者の ID でトランザクションを発行できます。キーの侵害を防ぐ方法は?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>力:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>セキュリティ – 特にインターネットに接続している場合、キーはデバイスに保存されているときにハッキングされる可能性があります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ユーザビリティ – 一部のキーはブロックチェーンの参加者によって頻繁に使用される場合がありますが、他のキーはあまり使用されないか、バックアップとして機能する可能性があります。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>解決</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>ユーザーは、ホット ウォレット</em>&nbsp;と&nbsp;<em>コールド ウォレット</em>の 2 種類のウォレットにキーを格納することを選択できます&nbsp;。ホット ウォレットは、通常、インターネットに接続されているブロックチェーン ゲートウェイを指します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://i0.wp.com/research.csiro.au/blockchainpatterns/wp-content/uploads/sites/249/2020/06/hot-cold.png?ssl=1"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="caption-attachment-311">ホットウォレットとコールドウォレットの収納パターン</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ホットウォレットを通じて、ユーザーはブロックチェーンに直接トランザクションを発行できます。したがって、通常、ホット ウォレットには頻繁に使用されるキーが保持されます。コールド ウォレットとは、潜在的な攻撃を最小限に抑えるためにオフラインで保持されるキー ストレージを指します。したがって、クラウド ウォレットには通常、めったに使用されないキーが含まれます。コールド ウォレットは、インターネットから切断された任意のデバイスである場合もあれば、エンティティのキ​​ーを記録した紙である場合もあります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>トランザクションに署名するためにコールド ウォレットに保存されているキーが必要な場合、ユーザーはコールド ウォレット デバイスをコンピュータに接続し、該当するフィールドにキーをコピー アンド ペーストする必要があります。使用頻度に基づいて、2 つのウォレット間でキーの移行を自動化することもできます。また、特定のキーをクリティカルとしてマークして、主にコールド ウォレットに保管することもできます。トランザクションに署名する必要がある場合は、ホット ウォレットにコピーできます。ただし、トランザクションが署名されるとすぐに、ホット ウォレットから削除する必要があります。特定のアプリケーション設定、ブロックチェーン プラットフォーム、およびウォレットの実装では、コールド ウォレットで完全にトランザクションに署名し、ホット ウォレットを使用して署名済みトランザクションをブロックチェーンに発行/中継することも可能です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>利点</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>安全な保管 – コールド ウォレットはインターネットから隔離されています。したがって、キーの安全な保管場所を提供してください。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>使いやすさ – このような安全なストレージは、キーの使いやすさも維持します。コールド ウォレットがインターネットに (直接またはミドルウェア経由で) 接続されると、関係者はそれらのキーを利用できるようになります。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>欠点</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>セキュリティ – ホット ウォレットは自分の秘密鍵をオンラインで保存するため、盗難に対してより脆弱です。コールド ウォレットは、キーをコピー/移行するためにホット ウォレットに接続されるとすぐに脆弱になります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>使いやすさ - コールド ウォレットはホット ウォレットよりも安全ですが、ユーザーがコールド ウォレットに接続する必要があるため、使いやすさは劣ります。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>関連パターン</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://research.csiro.au/blockchainpatterns/master-sub-key/">マスターキーとサブキーの生成</a>パターンでは、&nbsp;&nbsp;マスターキーをコールドウォレットに保管し、サブキーをホットウォレットに保管できます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://research.csiro.au/blockchainpatterns/general-patterns/self-sovereign-identity-patterns/key-management-patterns/key-sharding/">キー シャーディング</a>&nbsp;パターンをウォレット アプリケーションで使用して、キーを分割およびマージし、その侵害を最小限に抑えることができます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ウォレット アプリケーションに統合されると、&nbsp;<a href="https://research.csiro.au/blockchainpatterns/general-patterns/self-sovereign-identity-patterns/update-by-delegates/">デリゲート リスト</a>&nbsp;パターンの事前定義されたデリゲートが、侵害されたキーのキー所有権を置き換えることができます。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>既知の用途</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.myetherwallet.com/">MyEtherWallet は</a>&nbsp;、イーサリアムでの即時支払いと引き出しのためのグラフィカル インターフェイスを備えたホット ウォレットです。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://trezor.io/">Trezor</a>&nbsp;は、ユーザーのコイン、パスワード、およびその他のデジタル キーを格納および暗号化するように設計された暗号通貨ハードウェア ウォレットです。すべての個人データを保存するための独立したメモリを備えた専用コンピューターです。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.ledger.com/">Ledger は</a>&nbsp;、ユーザーの秘密鍵を安全なハードウェア デバイスに格納し、暗号通貨を保護するためのハードウェア ウォレット製品を提供します。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="0391">さまざまな暗号ストレージ オプションを調べる</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":1796} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-72-1024x576.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1796"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p id="df6c"><strong>各ウォレットの長所と短所は何ですか</strong>?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="3fd8">ホットウォレットとは、インターネットに接続された暗号通貨ウォレットを指します。一般に、ホット ウォレットはセットアップ、アクセス、およびより多くのトークンの受け入れが簡単です。<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">しかし、ハッカーの攻撃</a>、規制の可能性、その他の技術的な脆弱性に対しても脆弱です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="fa90">コールド ストレージとは、インターネットに接続されていない暗号通貨ウォレットを指します。全体として、コールド ウォレットはより安全ですが、ホット ウォレットほど多くの暗号通貨を受け入れません。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="2ad2">コールドウォレットを取得する必要がありますか?</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p id="5080">ビットコイン、イーサリアム、または 100 ドル以上の価値があるその他の暗号通貨を所有する場合は、今すぐコールド ウォレットを購入できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="c451">「ビットコインは、あなた自身の銀行になるこの機会を与えてくれる」と人々が言うのを聞いたことがあるかもしれません。この責任には、長所と短所があります。一般に、暗号通貨は仲介手数料が少なく、銀行規制が煩雑ではありません。それでも、資産の安全性を確保するのはあなたの責任です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="45fe">全体として、原則として、従来の革製の財布をポケットに入れるのと同じくらい、ホット ウォレットにお金を入れておく必要があります。泥棒があなたの通常の財布を盗もうとしている場合、銀行口座のお金ではなく、ポケットにあるお金だけを失うことになると考えてください。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="45b5">簡単に言えば、ここであなたを助けてくれる類推があります。ホットウォレットは、街を歩くポケットウォレットと考えることができます。コールドウォレットは銀行預金です。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="7996">ホットウォレットの長所と短所</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":1} -->
<h1 id="ef48">ホットウォレットを使用すると、次の利点が得られます。</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>暗証番号とアクセス番号をウォレットに入力することで、コインにすばやくアクセスできます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>投資コストは低くなります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ホットウォレットとして機能するアプリケーションまたはソフトウェアの広範なポートフォリオがあります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ご利用には暗証番号または暗証番号の設定が必要です。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>あらゆるプラットフォームに接続できるため、操作と取引が可能です。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="d294">これらのウォレットのいずれかを使用すると、次の欠点が生じる場合があります。</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>お金はクラウドに保存され、サイバー犯罪者に対してより脆弱であるため、盗難のリスクが高くなります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>常にインターネットに接続している必要があります。そうしないとサポートできないので、インターネット接続が途絶えると大変なことになります。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="d041">コールドウォレットの長所と短所</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":1} -->
<h1 id="2510">このウォレットを使用すると、次の利点が得られます。</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>このタイプのウォレットはインターネットなしで機能し、多くの盗難がインターネット上で行われるため、高いレベルのセキュリティを提供します.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コールド ウォレットは、ERC20 またはその他のトークン標準をサポートしており、無制限の数のトークンをサポートできます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ご利用には暗証番号または暗証番号の設定が必要です。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>デバイスをどこにでも持ち運べます。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="c4a5">これらのウォレットのいずれかを使用すると、次の欠点が生じる可能性があります。</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>デバイスを紛失するリスクがあります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>これらのタイプのデバイスとは取引できません。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>それを手に入れるには、約100ドルを投資する必要があります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>他の物理デバイスと同様に、障害、破損、または読み取りの問題が発生する傾向があります。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p id="a37a">取引したい場合は、ホットウォレットがより良い選択肢であることを覚えておいてください.&nbsp;それでも、可能な限り暗号化し、最も重要なセキュリティのために最適なソフトウェアを選択することをお勧めします.&nbsp;一方、トレーディングを行わない投資家で、最高レベルの保護が必要な場合は、コールド ウォレットの方が適しています。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>ホット ウォレットとコールド ウォレットは、暗号資産を安全に保管するために必要です。前者が暗号トークンの送受信に使用される場合、後者は蓄積された暗号通貨を脆弱性なしで安全に保持します。ホットウォレットは、トークンを送受信するためにインターネット接続を必要とするため、非常に高価であることが証明されている暗号攻撃のリスクに大きくさらされています.&nbsp;そのため、大量のトークンを保持することはできません。ここでコールドウォレットの出番です。ホット ウォレットとコールド ウォレットの両方を利用することは、仮想通貨の脆弱性管理において安全な方法であり、攻撃者に抜け穴を残すことはありません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ホット ウォレットとコールド ウォレットのアーキテクチャと、脆弱性のリスクを軽減するためにどのように設定する必要があるかを理解しましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#What-are-hot-wallets?">ホットウォレットとは？</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#What-are-cold-wallets?">コールドウォレットとは？</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#Hot-wallet-vs-Cold-Wallet-Differences">ホットウォレットとコールドウォレットの違い:</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#Hot-and-cold-wallet-setupns?">ホットウォレットとコールドウォレットのセットアップ</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#How-does-hot-and-cold-wallet-interact?">ホットウォレットとコールドウォレットはどのように相互作用しますか?</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#How-do-hot-and-cold-wallet-setups-in-big-systems-work?">大規模システムでのホット ウォレットとコールド ウォレットのセットアップはどのように機能しますか?</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="What-are-hot-wallets?">ホットウォレットとは？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ホット ウォレットは、常にインターネットに接続されている暗号化ウォレットであり、コールド ウォレットよりもユーザーが簡単にアクセスできます。それらはモバイル、デスクトップ、またはウェブベースのウォレットであり、ユーザーフレンドリーで、暗号ユーザー間の通貨の簡単な転送を容易にします。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>秘密鍵は、アプリ自体のホット ウォレットに保管および暗号化され、オンラインで保存されます。隠れた脆弱性があり、ハッカーはそれを標的にしてシステムに侵入することができます。その使いやすさから、暗号通貨の購入と取引、またはしばらくしてから資産を現金化するための最も好ましいウォレットです。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>ホットウォレットストレージはどのように機能しますか?</strong></h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1798} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-wallet-storage-work.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1798"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>ホットウォレットストレージをコンピューターまたはデバイスにインストールすると、暗号資産を実際に保持することなく、暗号資産を購入、送受信できます。むしろ、ユーザーがトランザクションを開始できる秘密鍵を保持します。これは、資産を保存するブロックチェーンと相互作用するため可能です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Metamask は、現在入手可能な最も人気のあるホットウォレットの 1 つです。そこで、メタマスクを使ったホットウォレットの仕組みについて説明します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Metamask は、ブロックチェーン、特に Ethereum とブラウザーの間のブリッジとして機能する Web ブラウザー拡張機能として利用できます。Metamask をダウンロードしてインストールし、ブラウザの拡張機能として追加すると、「ウォレットのインポート」または「ウォレットの作成」のいずれかを求められます。ウォレットのインポートでは、秘密の復元フレーズを入力して既存のウォレットを追加できますが、後者では新しい暗号ウォレットを作成できます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>新しいウォレットを作成する場合は、新しいメタマスク パスワードを設定して、デバイス上のアプリまたはプラットフォームを保護する必要があります。このパスワードは、秘密の回復フレーズの代わりに、文字列、顔認識、またはアプリにアクセスするために定期的に使用できる指紋にすることができます.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>パスワードを作成したら、秘密のバックアップ フレーズをコピーして貼り付けるか、安全な場所に書き留めておく必要があります。Metamask ウォレットにあるアカウントごとに、秘密鍵が提供されます。この秘密鍵を使用して暗号通貨のロックを解除できます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="What-are-cold-wallets?">コールドウォレットとは？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>コールド ウォレットはハードウェア ベースであり、オフラインで存在します。コールド ウォレットはホット ウォレットほど便利ではありませんが、はるかに安全です。このオフライン ウォレットを使用すると、鍵をオンラインのハッカーから完全に保護できます。コールド ウォレットは、ペーパー ウォレットまたはハードウェア デバイスです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ペーパー ウォレットは、秘密鍵と公開鍵を紙に書き留めたり印刷したりする従来の方法です。フィッシング攻撃を受けにくいため、鍵を安全に保管する方法です。ハードウェア ウォレットは、キーを格納する USB または Bluetooth デバイスの形をした外部デバイスです。コールドウォレットは流動性が低いため、暗号資産を購入して長期間保持することを計画している人に最適です.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>オフラインのコールド ウォレットとオンラインのホット ウォレットの間で取引を行うには、プラグを使用してハードウェア デバイスをインターネットにアクセスできる別のデバイス (主にコンピューター) に接続し、必要な金額をコールド ウォレットからホット ウォレットに転送する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>コールドウォレットストレージはどのように機能しますか?</strong></h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1800} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-wallet-storage-work-1.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1800"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>コールド ウォレットは、単独ではブロックチェーンに接続してトランザクションを完了することができません。ユーザーが取引にコールド ウォレットを使用する場合、インターネット接続のあるデバイスに接続する必要があります。ただし、これによって秘密鍵がセキュリティ上の脅威にさらされることはありません。それがどのように機能するか見てみましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>コールド ウォレット ストレージは、コールド ウォレット コアとコールド ゲートウェイの 2 つのコンポーネントに大別できます。コールド ウォレット コアにはインターネット アクセスがなく、完全にエアギャップされていますが、コールド ゲートウェイはインターネットに接続されています。トランザクションはコールド ウォレットのコールド ゲートウェイで作成され、オフラインのコールド ウォレット コアで署名されます。したがって、ユーザーが x 個のトークンを別のウォレットに送信したい場合、トランザクションはインターネット接続のあるコールド ゲートウェイで作成されますが、トランザクションの署名はオフラインで行われます。トランザクションが署名された後、コールド ウォレット コアでオンラインで開示またはブロードキャストされます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これをよりよく理解するために、コールドウォレット ELLIPAL の例を見てみましょう。ELLIPAL はエア ギャップ ハードウェア ウォレットであり、本質的に安全なコールド ウォレットです。インターネットから完全に分離されており、不正アクセス、ハッキング、マルウェア、その他のオンライン攻撃を防ぐように設計されています。そのため、トランザクションを開始するには、ブロックチェーンに接続するためのプロキシとして機能する ELLIPAL モバイル アプリをインストールする必要があります。ELLIPAL ウォレットを介した取引の全プロセスは、次のステップに要約できます。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>ユーザーがアプリでトランザクションを開始します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>アプリはコールド ウォレットからの確認を求めます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ハードウェア ウォレットは、秘密鍵を介してトランザクションに署名します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>承認後、アプリはトランザクションを完了します</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="Hot-wallet-vs-Cold-Wallet-Differences">ホットウォレットとコールドウォレットの違い:</h2>
<!-- /wp:heading -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th scope="col"></th><th scope="col"><strong>ホットウォレット</strong></th><th scope="col">コールドウォレット</th></tr></thead><tbody><tr><td><strong>インターネット接続</strong></td><td>オンライン</td><td>オフライン</td></tr><tr><td><strong>アクセシビリティ</strong></td><td>アクセスしやすい</td><td>アクセシビリティの低さ</td></tr><tr><td><strong>有形性</strong></td><td>ソフトウェアベースのウォレット;&nbsp;だから、無形</td><td>物理的な財布;&nbsp;だから、具体的な</td></tr><tr><td><strong>種類</strong></td><td>モバイル、ウェブ、またはデスクトップのウォレット</td><td>ペーパーウォレットまたはハードウェアウォレット</td></tr><tr><td><strong>安全性</strong></td><td>ハッキングや攻撃を受けやすい。したがって、安全性が低くなります。</td><td>ハッキングや攻撃による脅威が少なくなります。だから、より安全に</td></tr><tr><td><strong>快適</strong></td><td>簡単便利</td><td>不便</td></tr><tr><td><strong>料金</strong></td><td>より安価な</td><td>もっと高い</td></tr><tr><td><strong>使いやすさ</strong></td><td>少量の暗号を保管するのに最適</td><td>大量の暗号通貨を保管するのに最適</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 id="Hot-and-cold-wallet-setupns?">ホットウォレットとコールドウォレットのセットアップ</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>トランザクションにホットウォレットを使用することは簡単で便利ですが、セキュリティ上の脅威のために多数の暗号通貨を保持するために使用することはできません.&nbsp;マルウェア攻撃やフィッシングなどのセキュリティの脅威に対する脆弱性が最も少ないため、大量の暗号通貨をコールド ウォレットに保管することをお勧めします。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>リスクを回避するためにウォレットを設定する重要な方法の 1 つは、ホット ウォレットとコールド ウォレットの両方を組み合わせて、資金のオンライン露出を減らすことです。この中で、各ウォレットは異なる目的のために設定されています。ホット ウォレットは、受信側のウォレットと送信側のウォレットとして機能します。受信側のウォレットは取引所に送られる資金を管理し、送信側のウォレットは取引と取引のために暗号を送信するために使用されます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>送信ウォレットと受信ウォレットの両方がオンラインサーバーでホストされるため、両方のウォレットに保持される資金の数を最小限に抑えて、暗号の脆弱性のリスクを軽減する必要があります。残りの暗号はコールド ウォレットに保管する必要があります。これを行うことで、セキュリティが侵害された場合でも、ほとんどの資産を安全に保つことができます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="How-does-hot-and-cold-wallet-interact?">ホットウォレットとコールドウォレットはどのように相互作用しますか?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>送金されたすべての資金が受取側のウォレットに送られるため、受取側のウォレットに暗号が蓄積され、暗号の脆弱性が生じる可能性があります。そのため、そのほとんどをコールド ウォレットに送信し、一部を送信側ウォレットに送信する必要があります。暗号が足りなくなったら送信ウォレットに送金するには、受信ウォレットに最小限の金額が必要です。これにより、必要なときにいつでも送信ウォレットに十分な暗号があることが保証されます。しかし、資金が確実に受信側のウォレットに送られず、送信側のウォレットが緊急に通貨を必要としているとします。その場合、必要な金額をコールド ウォレットから送信側ウォレットに転送できます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="Content:HotandColdWalletArchitecture-Howtomitigatecryptovulnerability?">暗号の脆弱性を緩和するには?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>合計で 200 ETH を所有していて、常に資金の 30% 以上を危険にさらすことを避けたいとします。この計算に基づいて、ウォレットごとに最大しきい値と最小しきい値を設定して、マルウェア攻撃の重大度を下げる必要があります。したがって、受け取り側のウォレットには、最小で 10 ETH、最大で 20 ETH が必要です。同様に、送信側のウォレットには、少なくとも 20 ETH、最大 40 ETH が必要です。残りの資産はコールド ウォレットに保管する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ウォレットの送受信にしきい値を設定する場合は、それを遵守し、設定された金額が制限を超えたり下回ったりしないようにしてください。余剰資金は脆弱になりやすく、限度額を下回ると必要なときに必要な量を生産できません。そのため、常に十分な資金を維持してください</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="How-do-hot-and-cold-wallet-setups-in-big-systems-work?">大規模システムでのホット ウォレットとコールド ウォレットのセットアップはどのように機能しますか?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ホット ウォレットとコールド ウォレットのセットアップはさまざまで、各セットアップは開発者の要件と思考プロセスに基づいて設計されています。以下のインフォグラフィックを通じて、大規模なシステムでホット ウォレットとコールド ウォレットのセットアップがどのように設計されているかを理解しましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1802} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-and-cold-wallet-setups-in-big-systems-work-696x1024.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1802"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>上記のインフォグラフィックでは、ある人が x 個のトークンを別のユーザーに送信したい場合、アプリケーションのフロントエンドでリクエストを入力し、API レイヤーまたはアプリのバックエンドで取得します。バックエンドは、入力リクエストをウォレット サーバーに転送します。典型的なウォレット アーキテクチャでは、ウォレット サーバーは、ノード、データベース、API、トランザクション サービスの管理など、複数のマイクロサービスを処理します。この場合、ユーザー入力はトランザクション サービスに関連しているため、要求はこのマイクロサービスに送信されます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>その後、トランザクション サービスは、ウォレットに関連するすべてのサービスを処理するウォレット マイクロサービスにリクエストを送信します。ウォレット マイクロサービスは、プラットフォームごとに異なる場合があります。上記のインフォグラフィックでは、ウォレット マイクロサービスには次のものが含まれます。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>ホット ウォレットの資金管理 –&nbsp;</strong>暗号資産のオーバーフローや赤字が発生することなく常にしきい値を維持し、リスクにさらされるのを防ぎます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>ホワイトリストに登録された IP –&nbsp;</strong>ドメインまたはサーバーにアクセスできる人の数を、許可された少数の信頼できる IP アドレスに制限します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>トークン –&nbsp;</strong>&nbsp;x 個の ETH や x 個の SOL など、トークンを管理および追跡します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>サービスの監視 –&nbsp;</strong>このマイクロサービスは、すべてのサービスが問題なく動作しているかどうかをチェックします。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>しきい値 -&nbsp;</strong>これらは、ウォレットに必要な金額があること、または他の人に送金しないことを保証します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>2 段階認証 –&nbsp;</strong>ウォレット エコシステムにアクセスする前に、身元を 2 回確認する必要があるセキュリティ プロセスです。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>通知 –&nbsp;</strong>トランザクションの完了通知などの重要な事項についてユーザーに警告します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>KMS –&nbsp;</strong>キー管理システムまたは KMS は、キーを安全に作成、保存、および管理するのに役立ちます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>ホットウォレットをローテーション&nbsp;</strong></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>トランザクション入力がトランザクション サービスからウォレット マイクロサービスに転送されると、上記のすべてのマイクロサービスが実行されます。すべてのサービスが完了し、ホット ウォレットに十分な数のトークンがあることが確認されると、x 個のトークンが受信者に送信されます。その後、トランザクションは正常に完了したと言われます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>結論</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ホット ウォレットとコールド ウォレットの両方を統合することで、ユーザーとサービス プロバイダーの両方に対する暗号攻撃のリスクを軽減できます。1つは暗号取引に使用され、もう1つは暗号を安全に保持するために使用されます。仮想通貨が出現した当初はホット ウォレットのみが人気でしたが、最近ではコールド ウォレットの使用がより一般的になっています。さらに、ホット ウォレットとコールド ウォレットの混合は、その大きなメリットにより、仮想通貨の専門家やサービス プロバイダーの間で徐々に注目を集めています。したがって、1 つのウォレットだけを使用することは時代遅れであり、人々は追加のセキュリティ対策としてホット ウォレットとコールド ウォレットの両方を組み合わせることの利点を徐々に認識しています。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/Cold-and-Hot-Wallets" target="_blank" rel="noreferrer noopener">GitHub</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">テレグラム: https://t.me/cryptodeeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/NrQ3oNxlrlU" target="_blank" rel="noreferrer noopener"><strong>ビデオ: https://youtu.be/NrQ3oNxlrlU</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/cold-and-hot-wallets" target="_blank" rel="noreferrer noopener">ソース: https://cryptodeeep.ru/cold-and-hot-wallets</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1817} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/030-1-1024x576.png" alt="コールド ウォレットとホット ウォレットは脆弱性を発見し、ブロックチェーンに対するさまざまな攻撃を排除します" class="wp-image-1817"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
