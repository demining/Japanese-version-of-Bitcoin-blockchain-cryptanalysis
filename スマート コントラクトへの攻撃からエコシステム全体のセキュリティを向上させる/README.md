# スマート コントラクトへの攻撃からエコシステム全体のセキュリティを向上させる

<!-- wp:embed {"url":"https://www.youtube.com/embed/HVh_cbsgSMg","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/HVh_cbsgSMg
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>フロントランニングAKAトランザクション順序依存</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>コンコルディア大学は、フロントランニングを「今後の取引や取引に関する特権的な市場情報に事前にアクセスすることで企業が利益を得る一連の行動」と考えています。市場における将来の出来事に関するこの知識は、搾取につながる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>たとえば、特定のトークンの非常に大きな購入が発生することを知っている悪意のある人物は、事前にそのトークンを購入し、特大の買い注文によって価格が上昇したときにトークンを販売して利益を得ることができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">フロントランニング攻撃は金融市場で長い間問題となっており、ブロックチェーンの透明性により、暗号通貨市場でも問題が再び発生しています。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この問題の解決策は契約ごとに異なるため、防御するのは困難です。考えられる解決策には、トランザクションのバッチ処理と、事前コミット スキームの使用、つまり、ユーザーが後で詳細を送信できるようにすることが含まれます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/doc/SoK_Transparent_Dishonesty_Front-Running_Attacks_on_Blockchain.pdf" target="_blank" rel="noreferrer noopener"><strong>PDF: SoK: 透過的な不誠実: ブロックチェーンに対する最前線の攻撃</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>前走</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>すべてのトランザクションは、実行される前に mempool で短時間表示されるため、ネットワークのオブザーバーは、アクションがブロックに含まれる前にアクションを確認して反応することができます。これがどのように悪用されるかの例は、買い注文トランザクションを見ることができ、最初のトランザクションが含まれる前に 2 番目の注文をブロードキャストして実行できる分散型取引所です。特定の契約自体に帰着するため、これを防ぐことは困難です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>フロントランニングは、もともと伝統的な金融市場のために造られたもので、混乱を勝者の利益に導くための競争です。金融市場では、情報の流れが仲介者を生み出しました。仲介者は、最初に情報を知り、反応することで利益を得ることができました。これらの攻撃は、主に株式市場の取引や、whois ゲートウェイなどの初期のドメイン レジストリ内で行われていました。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>フロントランニング (/ˌfrəntˈrəniNG/)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>名詞</em>: フロントランニング。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><em>STOCK MARKET</em>ブローカーや投資アナリストから提供された事前情報を、クライアントに提供される前にマーケット メーカーが取引する慣行。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 id="taxonomy">分類法</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://arxiv.org/abs/1902.05164">分類法</a>を定義し&nbsp;&nbsp;、各グループを別のグループと区別することで、問題について話し合い、各グループの解決策を見つけやすくなります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">フロントランニング攻撃の次のカテゴリを定義します</a>。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>変位</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>挿入</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>抑制</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4 id="displacement">変位</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>最初のタイプの攻撃である&nbsp;<em>置換攻撃</em>では、&nbsp;&nbsp;マロリー (敵対者) が関数を実行した後にアリス (ユーザー) の関数呼び出しを実行することは<strong>重要ではありません。</strong>Alice は孤立したり実行されたりしても、意味のある影響はありません。変位の例には次のものがあります。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>アリスはドメイン名を登録しようとし、マロリーは最初に登録しました。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>アリスはバウンティを受け取るためにバグを送信しようとし、マロリーはそれを盗んで最初に送信しました。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>アリスがオークションで入札を試み、マロリーがそれをコピーします。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>この攻撃は通常、&nbsp;<code>gasPrice</code>&nbsp;ネットワーク平均よりも高くすることによって実行され、多くの場合、10 倍以上の乗数で行われます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="insertion">挿入</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>このタイプの攻撃では、&nbsp;&nbsp;元の関数呼び出しがトランザクションの後に実行されることが攻撃者にとって<strong>重要です。</strong>挿入攻撃では、マロリーが関数を実行した後、コントラクトの状態が変更され、この変更された状態でアリスの元の関数を実行する必要があります。たとえば、アリスが最良のオファーよりも高い価格でブロックチェーン資産に購入注文を出した場合、マロリーは 2 つのトランザクションを挿入します。マロリーは最良のオファー価格で購入し、同じ資産をアリスのわずかに高い購入価格で売りに出します。 .&nbsp;その後、アリスの取引が実行された場合、マロリーは資産を保持する必要なく価格差で利益を得ることができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>置換攻撃と同様に、これは通常、ガス価格オークションでアリスの取引を上回ることによって行われます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>取引順序依存</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Transaction Order Dependence は、スマート コントラクトの競合状態に相当します。例: 1 つの関数が報酬パーセンテージを設定し、withdraw 関数がそのパーセンテージを使用する場合。その後、トランザクションの取り消しは、最終的に取り消される金額に影響を与える変更報酬関数呼び出しによってフロントランできます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-114">SWC-114</a>を参照&nbsp;<a href="https://swcregistry.io/docs/SWC-114"></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="suppression">抑制</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>ブロック スタッフィング</em>攻撃とも呼ばれる抑制攻撃では&nbsp;&nbsp;、マロリーが関数を実行した後、アリスが関数を実行するのを遅らせようとします。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これは、「Fomo3d」ゲームやその他のオンチェーン ハッキングの最初の勝者に当てはまります。攻撃者は、&nbsp;<code>gasPrice</code>&nbsp;すべて&nbsp;<code>gasLimit</code>&nbsp;のガスを消費してブロックの&nbsp;<code>gasLimit</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>バリアント</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">これらの各攻撃には、&nbsp;<em>非対称</em>&nbsp;と&nbsp;<em>バルク</em>の 2 つのバリアントがあります。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>場合によっては、アリスとマロリーが異なる操作を実行しています。たとえば、アリスがオファーをキャンセルしようとしていて、マロリーが最初にオファーを実行しようとしているとします。<em>これを非対称変位</em>と呼びます&nbsp;。他のケースでは、マロリーは大規模な一連の機能を実行しようとしています。たとえば、アリスと他の人は、ブロックチェーンで会社が提供する限定された株式のセットを購入しようとしています。<em>これをバルク変位</em>と呼びます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="mitigations">緩和策</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>フロントランニングは、イーサリアムなどのパブリック ブロックチェーンに蔓延する問題です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最善の改善策は、&nbsp;主にトランザクションの順序や時間の重要性を取り除くことによって、<strong>アプリケーションのフロントランニングの利点を取り除くことです。</strong>たとえば、市場では、バッチ オークションを実装する方がよいでしょう (これは、高頻度の取引の懸念からも保護します)。もう 1 つの方法は、事前コミット スキームを使用することです (「詳細は後で提出します」)。3 番目のオプションは、取引の最大または最小の許容価格範囲を指定することでフロントランニングのコストを軽減し、それによって価格のずれを制限することです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>トランザクションの順序付け:</strong><code>gasPrice</code>&nbsp;Go-Ethereum (Geth) ノードは、&nbsp;アドレスナンス&nbsp;に基づいてトランザクションを順序付けます&nbsp;。ただし、これにより、ネットワーク内の参加者間でガスオークションが行われ、現在採掘されているブロックに含まれるようになります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>機密性:</strong>&nbsp;もう 1 つのアプローチは、トランザクションの可視性を制限することです。これは、「コミットして明らかにする」スキームを使用して行うことができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>簡単な実装は、最初のトランザクションでデータの keccak256 ハッシュを保存し、次にデータを明らかにして、2 番目のトランザクションでハッシュに対して検証することです。ただし、トランザクション自体が意図を漏らし、場合によっては担保の価値を漏らすことに注意してください。より安全な強化されたコミットおよび公開スキームがありますが、機能するためにはより多くのトランザクションが必要です。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>ブロック ガス制限による DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>イーサリアム ブロックチェーンでは、すべてのブロックにガス制限があります。ブロック ガス制限の利点の 1 つは、攻撃者が無限のトランザクション ループを作成するのを防ぐことですが、トランザクションのガス使用量がこの制限を超えると、トランザクションは失敗します。これは、いくつかの異なる方法で DoS 攻撃につながる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><a href="https://github.com/allpaca/smart-contract-attack-vectors/blob/master/attacks/dos-gas-limit.md#unbounded-operations"></a>無制限の操作</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ブロックガス制限が問題になる可能性がある状況は、アドレスの配列に資金を送信する場合です。悪意がなくても、これは簡単に失敗する可能性があります。支払うユーザーの数が多すぎると、ガス制限が上限に達し、トランザクションが成功しなくなる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この状況も攻撃につながる可能性があります。悪意のある人物が大量のアドレスを作成することを決定し、各アドレスにはスマート コントラクトから少額の資金が支払われるとします。効果的に行われた場合、トランザクションは無期限にブロックされ、それ以上のトランザクションが実行されなくなる可能性さえあります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この問題に対する効果的な解決策は、現在のプッシュ決済システムよりもプル決済システムを使用することです。これを行うには、各支払いを独自のトランザクションに分割し、受信者に関数を呼び出してもらいます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>なんらかの理由で、長さが指定されていない配列をループする必要がある場合は、少なくとも複数のブロックを使用する可能性があることを想定し、複数のトランザクションで実行できるようにします。次の例を参照してください。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>struct Payee {
    address addr;
    uint256 value;
}

Payee&#91;] payees;
uint256 nextPayeeIndex;

function payOut() {
    uint256 i = nextPayeeIndex;
    while (i &lt; payees.length &amp;&amp; msg.gas &gt; 200000) {
      payees&#91;i].addr.send(payees&#91;i].value);
      i++;
    }
    nextPayeeIndex = i;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3><a href="https://github.com/allpaca/smart-contract-attack-vectors/blob/master/attacks/dos-gas-limit.md#block-stuffing"></a>ブロックスタッフィング</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>状況によっては、指定されていない長さの配列をループしていなくても、コントラクトがブロック ガス制限で攻撃される可能性があります。攻撃者は、十分に高いガス価格を使用してトランザクションを処理する前に、いくつかのブロックを埋めることができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この攻撃は、非常に高いガス価格で複数のトランザクションを発行することによって行われます。ガスの価格が十分に高く、トランザクションが十分なガスを消費する場合、ブロック全体がいっぱいになり、他のトランザクションの処理が妨げられる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>イーサリアム トランザクションでは、送信者がスパム攻撃を抑止するためにガスを支払う必要がありますが、状況によっては、そのような攻撃を実行する十分なインセンティブが存在する可能性があります。たとえば、ブロック スタッフィング攻撃は、ギャンブル Dapp である Fomo3D で使用されました。アプリにはカウントダウンタイマーがあり、ユーザーがキーを購入するたびにタイマーが延長されることを除いて、ユーザーは最後にキーを購入することでジャックポットを獲得できました.&nbsp;攻撃者はキーを購入し、次の 13 ブロックと 1 行を詰め込んでジャックポットを獲得しました。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>このような攻撃の発生を防ぐには<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">、時間ベースのアクションをアプリケーションに組み込むことが安全かどうかを慎重に検討することが重要です。</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>サービス拒否</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="dos-with-unexpected-revert">(予期しない) 復帰による DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>簡単なオークション コントラクトを考えてみましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>// INSECURE
contract Auction {
    address currentLeader;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt; highestBid);

        require(currentLeader.send(highestBid)); // Refund the old leader, if it fails then revert

        currentLeader = msg.sender;
        highestBid = msg.value;
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>攻撃者が支払いを元に戻すフォールバック機能を持つスマート コントラクトを使用して入札した場合、攻撃者は任意のオークションに勝つことができます。古いリーダーに返金を試みた場合、返金に失敗すると元に戻ります。これは、悪意のある入札者がリーダーになる可能性があることを意味しますが、そのアドレスへの払い戻しは&nbsp;<em>常に</em>&nbsp;失敗します。このようにして、他の誰かが&nbsp;<code>bid()</code>&nbsp;関数を呼び出すのを防ぎ、永久にリーダーであり続けることができます。&nbsp;前述のように、代わりに<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">プル支払いシステム</a>を設定することをお勧めします&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>もう 1 つの例は、コントラクトがユーザー (クラウドファンディング コントラクトのサポーターなど) に支払うために配列を反復処理する場合です。各支払いが成功することを確認したいのはよくあることです。そうでない場合は、元に戻す必要があります。問題は、1 つの呼び出しが失敗した場合、支払いシステム全体が元に戻ってしまうことです。つまり、ループは決して完了しません。1 つのアドレスがエラーを強制しているため、誰も支払われません。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>address&#91;] private refundAddresses;
mapping (address =&gt; uint) public refunds;

// bad
function refundAll() public {
    for(uint x; x &lt; refundAddresses.length; x++) { // arbitrary length iteration based on how many addresses participated
        require(refundAddresses&#91;x].send(refunds&#91;refundAddresses&#91;x]])) // doubly bad, now a single failure on send will hold up all funds
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">繰り返しになりますが、推奨される解決策は、プル オーバー プッシュ ペイメントを優先する</a>ことです&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-113">SWC-113</a>を参照&nbsp;<a href="https://swcregistry.io/docs/SWC-113"></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="dos-with-block-gas-limit">ブロック ガス制限による DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>各ブロックには、消費できるガスの量に上限があり、したがって、実行できる量の計算があります。これがブロックガス制限です。消費されたガスがこの制限を超えると、トランザクションは失敗します。これにより、いくつかのサービス拒否ベクトルが発生する可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-a-contract-via-unbounded-operations">無制限の操作によるコントラクトの Gas Limit DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>前の例で別の問題に気付いたかもしれません。一度に全員に支払うことで、ブロック ガスの制限に達するリスクがあります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これにより、意図的な攻撃がない場合でも問題が発生する可能性があります。ただし、攻撃者が必要なガスの量を操作できる場合は特に悪い.&nbsp;前の例の場合、攻撃者は多数のアドレスを追加する可能性があり、それぞれが非常に少額の払い戻しを受ける必要があります。したがって、攻撃者の各アドレスに返金するための Gas コストは、最終的に Gas 制限を超えてしまい、返金トランザクションがまったく行われなくなる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">これは、プッシュ決済よりもプル決済を好む</a>もう 1 つの理由です&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>未知のサイズの配列を絶対にループする必要がある場合は、複数のブロックを使用する可能性があるため、複数のトランザクションが必要になることを計画する必要があります。次の例のように、どこまで行ったかを追跡し、その時点から再開できるようにする必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>struct Payee {
    address addr;
    uint256 value;
}

Payee&#91;] payees;
uint256 nextPayeeIndex;

function payOut() {
    uint256 i = nextPayeeIndex;
    while (i &lt; payees.length &amp;&amp; gasleft() &gt; 200000) {
      payees&#91;i].addr.send(payees&#91;i].value);
      i++;
    }
    nextPayeeIndex = i;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>関数の次の繰り返しを待っている間に他のトランザクションが処理されても、何も悪いことが起こらないことを確認する必要があります&nbsp;<code>payOut()</code>&nbsp;。したがって、絶対に必要な場合にのみ、このパターンを使用してください。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-the-network-via-block-stuffing">ブロック スタッフィングによるネットワーク上のガス リミット DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>コントラクトに無限ループが含まれていない場合でも、攻撃者は十分に高いガス価格で計算集約型のトランザクションを配置することで、他のトランザクションが数ブロックにわたってブロックチェーンに含まれるのを防ぐことができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これを行うために、攻撃者は、次のブロックがマイニングされるとすぐに含まれる十分に高いガス価格で、ガス制限全体を消費するいくつかのトランザクションを発行できます。ガスの価格はブロックに含まれることを保証するものではありませんが、価格が高ければ高いほど、その可能性は高くなります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>攻撃が成功した場合、他のトランザクションはブロックに含まれません。攻撃者の目的は、特定の時間の前に特定のコントラクトへのトランザクションをブロックすることである場合があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この攻撃は&nbsp;&nbsp;、ギャンブル アプリである Fomo3D に対して<a href="https://solmaz.io/2018/10/18/anatomy-block-stuffing/">行われました。</a>このアプリは、「キー」を購入した最後のアドレスに報酬を与えるように設計されています。キーを購入するたびにタイマーが延長され、タイマーが 0 になるとゲームが終了しました。攻撃者によって送信されたトランザクションは、各ブロックで 790 万のガスを消費したため、ガス制限により、いくつかの小さな「送信」トランザクション (それぞれ 21,000 ガスを消費) は許可されましたが、関数への呼び出しは許可されませんでした (300,000 ガス以上の費用がかかります)&nbsp;&nbsp;<code>buyKey()</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ブロック スタッフィング攻撃は、特定の期間内にアクションが必要な契約に対して使用できます。ただし、他の攻撃と同様に、期待される報酬がコストを上回った場合にのみ利益があります。この攻撃のコストは、詰める必要があるブロックの数に正比例します。他の参加者のアクションを阻止することで高額の報酬が得られる場合、あなたのコントラクトはそのような攻撃の対象となる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>(予期しない) 復帰による DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>DoS (サービス拒否) 攻撃は、ユーザーに資金を送ろうとすると機能で発生する可能性があり、その機能はその資金転送の成功に依存しています。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これは、悪意のあるアクターによって作成されたスマート コントラクトに資金が送信された場合に問題になる可能性があります。これは、すべての支払いを元に戻すフォールバック機能を簡単に作成できるためです。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>例えば：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>// INSECURE
contract Auction {
    address currentLeader;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt; highestBid);

        require(currentLeader.send(highestBid)); // Refund the old leader, if it fails then revert

        currentLeader = msg.sender;
        highestBid = msg.value;
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>この例でわかるように、攻撃者がすべての支払いを元に戻すフォールバック機能を備えたスマート コントラクトから入札した場合、それらは決して返金されないため、誰もより高い入札を行うことはできません。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これは、攻撃者が存在しない場合にも問題になる可能性があります。たとえば、配列を繰り返し処理してユーザーの配列に支払いをしたい場合、もちろん、各ユーザーが適切に支払われるようにしたい場合があります。ここでの問題は、1 つの支払いが失敗した場合、関数が元に戻され、誰も支払われないことです。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>address&#91;] private refundAddresses;
mapping (address =&gt; uint) public refunds;

// bad
function refundAll() public {
    for(uint x; x &lt; refundAddresses.length; x++) { // arbitrary length iteration based on how many addresses participated
        require(refundAddresses&#91;x].send(refunds&#91;refundAddresses&#91;x]])) // doubly bad, now a single failure on send will hold up all funds
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>この問題に対する効果的な解決策は、現在のプッシュ決済システムよりもプル決済システムを使用することです。これを行うには、各支払いを独自のトランザクションに分割し、受信者に関数を呼び出してもらいます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>contract auction {
    address highestBidder;
    uint highestBid;
    mapping(address =&gt; uint) refunds;

    function bid() payable external {
        require(msg.value &gt;= highestBid);

        if (highestBidder != address(0)) {
            refunds&#91;highestBidder] += highestBid; // record the refund that this user can claim
        }

        highestBidder = msg.sender;
        highestBid = msg.value;
    }

    function withdrawRefund() external {
        uint refund = refunds&#91;msg.sender];
        refunds&#91;msg.sender] = 0;
        (bool success, ) = msg.sender.call.value(refund)("");
        require(success);
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1>サービス拒否</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="dos-with-unexpected-revert">(予期しない) 復帰による DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>簡単なオークション コントラクトを考えてみましょう。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>// INSECURE
contract Auction {
    address currentLeader;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt; highestBid);

        require(currentLeader.send(highestBid)); // Refund the old leader, if it fails then revert

        currentLeader = msg.sender;
        highestBid = msg.value;
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>攻撃者が支払いを元に戻すフォールバック機能を持つスマート コントラクトを使用して入札した場合、攻撃者は任意のオークションに勝つことができます。古いリーダーに返金を試みた場合、返金に失敗すると元に戻ります。これは、悪意のある入札者がリーダーになる可能性があることを意味しますが、そのアドレスへの払い戻しは&nbsp;<em>常に</em>&nbsp;失敗します。このようにして、他の誰かが&nbsp;<code>bid()</code>&nbsp;関数を呼び出すのを防ぎ、永久にリーダーであり続けることができます。&nbsp;前述のように、代わりに<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">プル支払いシステム</a>を設定することをお勧めします&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>もう 1 つの例は、コントラクトがユーザー (クラウドファンディング コントラクトのサポーターなど) に支払うために配列を反復処理する場合です。各支払いが成功することを確認したいのはよくあることです。そうでない場合は、元に戻す必要があります。問題は、1 つの呼び出しが失敗した場合、支払いシステム全体が元に戻ってしまうことです。つまり、ループは決して完了しません。1 つのアドレスがエラーを強制しているため、誰も支払われません。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>address&#91;] private refundAddresses;
mapping (address =&gt; uint) public refunds;

// bad
function refundAll() public {
    for(uint x; x &lt; refundAddresses.length; x++) { // arbitrary length iteration based on how many addresses participated
        require(refundAddresses&#91;x].send(refunds&#91;refundAddresses&#91;x]])) // doubly bad, now a single failure on send will hold up all funds
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">繰り返しになりますが、推奨される解決策は、プル オーバー プッシュ ペイメントを優先する</a>ことです&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-113">SWC-113</a>を参照&nbsp;<a href="https://swcregistry.io/docs/SWC-113"></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="dos-with-block-gas-limit">ブロック ガス制限による DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>各ブロックには、消費できるガスの量に上限があり、したがって、実行できる量の計算があります。これがブロックガス制限です。消費されたガスがこの制限を超えると、トランザクションは失敗します。これにより、いくつかのサービス拒否ベクトルが発生する可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-a-contract-via-unbounded-operations">無制限の操作によるコントラクトの Gas Limit DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>前の例で別の問題に気付いたかもしれません。一度に全員に支払うことで、ブロック ガスの制限に達するリスクがあります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これにより、意図的な攻撃がない場合でも問題が発生する可能性があります。ただし、攻撃者が必要なガスの量を操作できる場合は特に悪い.&nbsp;前の例の場合、攻撃者は多数のアドレスを追加する可能性があり、それぞれが非常に少額の払い戻しを受ける必要があります。したがって、攻撃者の各アドレスに返金するための Gas コストは、最終的に Gas 制限を超えてしまい、返金トランザクションがまったく行われなくなる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">これは、プッシュ決済よりもプル決済を好む</a>もう 1 つの理由です&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>未知のサイズの配列を絶対にループする必要がある場合は、複数のブロックを使用する可能性があるため、複数のトランザクションが必要になることを計画する必要があります。次の例のように、どこまで行ったかを追跡し、その時点から再開できるようにする必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>struct Payee {
    address addr;
    uint256 value;
}

Payee&#91;] payees;
uint256 nextPayeeIndex;

function payOut() {
    uint256 i = nextPayeeIndex;
    while (i &lt; payees.length &amp;&amp; gasleft() &gt; 200000) {
      payees&#91;i].addr.send(payees&#91;i].value);
      i++;
    }
    nextPayeeIndex = i;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>関数の次の繰り返しを待っている間に他のトランザクションが処理されても、何も悪いことが起こらないことを確認する必要があります&nbsp;<code>payOut()</code>&nbsp;。したがって、絶対に必要な場合にのみ、このパターンを使用してください。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-the-network-via-block-stuffing">ブロック スタッフィングによるネットワーク上のガス リミット DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>コントラクトに無限ループが含まれていない場合でも、攻撃者は十分に高いガス価格で計算集約型のトランザクションを配置することで、他のトランザクションが数ブロックにわたってブロックチェーンに含まれるのを防ぐことができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>これを行うために、攻撃者は、次のブロックがマイニングされるとすぐに含まれる十分に高いガス価格で、ガス制限全体を消費するいくつかのトランザクションを発行できます。ガスの価格はブロックに含まれることを保証するものではありませんが、価格が高ければ高いほど、その可能性は高くなります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>攻撃が成功した場合、他のトランザクションはブロックに含まれません。攻撃者の目的は、特定の時間の前に特定のコントラクトへのトランザクションをブロックすることである場合があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この攻撃は&nbsp;&nbsp;、ギャンブル アプリである Fomo3D に対して<a href="https://solmaz.io/2018/10/18/anatomy-block-stuffing/">行われました。</a>このアプリは、「キー」を購入した最後のアドレスに報酬を与えるように設計されています。キーを購入するたびにタイマーが延長され、タイマーが 0 になるとゲームが終了しました。攻撃者によって送信されたトランザクションは、各ブロックで 790 万のガスを消費したため、ガス制限により、いくつかの小さな「送信」トランザクション (それぞれ 21,000 ガスを消費) は許可されましたが、関数への呼び出しは許可されませんでした (300,000 ガス以上の費用がかかります)&nbsp;&nbsp;<code>buyKey()</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ブロック スタッフィング攻撃は、特定の期間内にアクションが必要な契約に対して使用できます。ただし、他の攻撃と同様に、期待される報酬がコストを上回った場合にのみ利益があります。この攻撃のコストは、詰める必要があるブロックの数に正比例します。他の参加者のアクションを阻止することで高額の報酬が得られる場合、あなたのコントラクトはそのような攻撃の対象となる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1>外部コール</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4 id="use-caution-when-making-external-calls">外線発信の際はご注意ください</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>信頼されていないコントラクトを呼び出すと、いくつかの予期しないリスクやエラーが発生する可能性があります。<em>外部呼び出しは、そのコントラクトまたは</em>&nbsp;それが依存する他のコントラクトで悪意のあるコードを実行する可能性があります&nbsp;。そのため、すべての外部呼び出しは、潜在的なセキュリティ リスクとして扱う必要があります。外部コールを削除できない場合、または削除することが望ましくない場合は、このセクションの残りの推奨事項を使用して、危険を最小限に抑えます。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="mark-untrusted-contracts">信頼できないコントラクトをマークする</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>外部コントラクトと対話するときは、変数、メソッド、およびコントラクト インターフェイスに名前を付けて、それらとの対話が潜在的に安全でないことを明確にします。これは、外部コントラクトを呼び出す独自の関数に適用されます。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>// bad
Bank.withdraw(100); // Unclear whether trusted or untrusted

function makeWithdrawal(uint amount) { // Isn't clear that this function is potentially unsafe
    Bank.withdraw(amount);
}

// good
UntrustedBank.withdraw(100); // untrusted external call
TrustedBank.withdraw(100); // external but trusted bank contract maintained by XYZ Corp

function makeUntrustedWithdrawal(uint amount) {
    UntrustedBank.withdraw(amount);
}
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="avoid-state-changes-after-external-calls">外部呼び出し後の状態変更を避ける</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>raw 呼び出し</em>&nbsp;(形式&nbsp;<code>someAddress.call()</code>) または&nbsp;<em>コントラクト呼び出し</em>&nbsp;(形式&nbsp;) のどちらを使用する場合でも&nbsp;<code>ExternalContract.someMethod()</code>、悪意のあるコードが実行される可能性があると想定してください。悪意がない場合でも&nbsp;、呼び出し<em>た</em><code>ExternalContract</code>&nbsp;コントラクトによって悪意のあるコードが実行される可能性があります&nbsp;&nbsp;。<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1 つの特定の危険性は、悪意のあるコードが制御フローをハイジャックし、再入可能性による脆弱性につながる可能性があることです。(&nbsp;&nbsp;この問題の詳細については、<a href="https://consensys.github.io/smart-contract-best-practices/attacks/reentrancy/">再入可能性を参照してください)。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>信頼されていない外部コントラクトを呼び出す場合は、&nbsp;<em>呼び出し後に状態が変化しないようにしてください</em>。<a href="http://solidity.readthedocs.io/en/develop/security-considerations.html?highlight=check%20effects#use-the-checks-effects-interactions-pattern">このパターンは、checks-effects-interactions パターン</a>と呼ばれることもあります&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-107">SWC-107</a>を参照&nbsp;<a href="https://swcregistry.io/docs/SWC-107"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="dont-use-transfer-or-send"><code>transfer()</code>&nbsp;または を&nbsp;使用しないでください&nbsp;<code>send()</code>。</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>.transfer()</code><code>.send()</code>&nbsp;正確に 2,300 ガスを受信者に転送します&nbsp;。&nbsp;このハードコード化された Gas stipend の目的は、&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/attacks/reentrancy/">再入可能性の脆弱性</a>を防ぐことでしたが、これは Gas コストが一定であるという仮定の下でのみ意味があります。最近、&nbsp;&nbsp;<a href="https://eips.ethereum.org/EIPS/eip-1884">EIP 1884 が</a>&nbsp;イスタンブールのハードフォークに含まれました。EIP 1884 に含まれる変更の 1 つは、操作のガス コストの増加であり&nbsp;<code>SLOAD</code>&nbsp;、コントラクトのフォールバック機能に 2300 ガス以上のコストがかかります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>.transfer()</code>&nbsp;and の&nbsp;使用をやめ、<code>.send()</code>&nbsp;代わりに を使用する&nbsp;ことをお勧めします&nbsp;<code>.call()</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>// bad
contract Vulnerable {
    function withdraw(uint256 amount) external {
        // This forwards 2300 gas, which may not be enough if the recipient
        // is a contract and gas costs change.
        msg.sender.transfer(amount);
    }
}

// good
contract Fixed {
    function withdraw(uint256 amount) external {
        // This forwards all available gas. Be sure to check the return value!
        (bool success, ) = msg.sender.call.value(amount)("");
        require(success, "Transfer failed.");
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>.call()</code>&nbsp;は再入攻撃を軽減するものではないため、他の予防策を講じる必要があることに注意してください&nbsp;。<a href="https://solidity.readthedocs.io/en/develop/security-considerations.html?highlight=check%20effects#use-the-checks-effects-interactions-pattern">再入攻撃を防ぐには、 checks-effects-interactions パターン</a>を使用することをお勧めします&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="handle-errors-in-external-calls">外部呼び出しでエラーを処理する</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Solidity は、未加工のアドレスで機能する低レベルの呼び出しメソッドを提供します:&nbsp;&nbsp;<code>address.call()</code>、&nbsp;&nbsp;<code>address.callcode()</code>、&nbsp;&nbsp;<code>address.delegatecall()</code>、および&nbsp;<code>address.send()</code>。これらの低レベル メソッドは例外をスローすることはありませんが、&nbsp;<code>false</code>&nbsp;呼び出しで例外が発生した場合は戻ります。一方、&nbsp;<em>コントラクト呼び出し</em>&nbsp;(例:&nbsp;&nbsp;<code>ExternalContract.doSomething()</code>) は自動的にスローを伝播します (たとえば、&nbsp;&nbsp;&nbsp;if&nbsp;スロー<code>ExternalContract.doSomething()</code>&nbsp;も伝播します&nbsp;&nbsp;)。<code>throw</code><code>doSomething()</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>低レベルの呼び出しメソッドを使用する場合は、戻り値を確認して、呼び出しが失敗する可能性を確実に処理してください。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>// bad
someAddress.send(55);
someAddress.call.value(55)(""); // this is doubly dangerous, as it will forward all remaining gas and doesn't check for result
someAddress.call.value(100)(bytes4(sha3("deposit()"))); // if deposit throws an exception, the raw call() will only return false and transaction will NOT be reverted

// good
(bool success, ) = someAddress.call.value(55)("");
if(!success) {
    // handle failure code
}

ExternalContract(someAddress).deposit.value(100)();
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-104">SWC-104</a>を参照&nbsp;<a href="https://swcregistry.io/docs/SWC-104"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="favor-pull-over-push-for-external-calls">&nbsp;外部コールの<em>プル</em>&nbsp;オーバー&nbsp;<em>プッシュ</em>を優先&nbsp;</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>外部呼び出しは、偶発的または故意に失敗する可能性があります。このような障害による損害を最小限に抑えるには、多くの場合、各外部呼び出しを、呼び出しの受信者が開始できる独自のトランザクションに分離することをお勧めします。これは、ユーザーに自動的に資金をプッシュするよりも資金を引き出す方がよい支払いに特に関係します。<a href="https://consensys.github.io/smart-contract-best-practices/attacks/denial-of-service/">(これにより、ガス制限の問題</a>が発生する可能性も減少します&nbsp;。) 1 つのトランザクションで複数のイーサ転送を組み合わせることは避けてください。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>// bad
contract auction {
    address highestBidder;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt;= highestBid);

        if (highestBidder != address(0)) {
            (bool success, ) = highestBidder.call.value(highestBid)("");
            require(success); // if this call consistently fails, no one else can bid
        }

       highestBidder = msg.sender;
       highestBid = msg.value;
    }
}

// good
contract auction {
    address highestBidder;
    uint highestBid;
    mapping(address =&gt; uint) refunds;

    function bid() payable external {
        require(msg.value &gt;= highestBid);

        if (highestBidder != address(0)) {
            refunds&#91;highestBidder] += highestBid; // record the refund that this user can claim
        }

        highestBidder = msg.sender;
        highestBid = msg.value;
    }

    function withdrawRefund() external {
        uint refund = refunds&#91;msg.sender];
        refunds&#91;msg.sender] = 0;
        (bool success, ) = msg.sender.call.value(refund)("");
        require(success);
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-128">SWC-128</a>を参照&nbsp;<a href="https://swcregistry.io/docs/SWC-128"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="dont-delegatecall-to-untrusted-code">信頼できないコードに呼び出しを委譲しない</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>この&nbsp;<code>delegatecall</code>&nbsp;関数は、呼び出し側コントラクトに属しているかのように、他のコントラクトから関数を呼び出すために使用されます。したがって、呼び出し先は呼び出し元アドレスの状態を変更できます。これは安全でない可能性があります。以下の例は、使用が&nbsp;<code>delegatecall</code>&nbsp;契約の破棄とその残高の損失につながる可能性があることを示しています。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>contract Destructor
{
    function doWork() external
    {
        selfdestruct(0);
    }
}

contract Worker
{
    function doWork(address _internalWorker) public
    {
        // unsafe
        _internalWorker.delegatecall(bytes4(keccak256("doWork()")));
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>Worker.doWork()</code>&nbsp;デプロイされたコントラクトのアドレスを&nbsp;<code>Destructor</code>&nbsp;引数として&nbsp;呼び出された場合&nbsp;、<code>Worker</code>&nbsp;コントラクトは自己破壊します。信頼できるコントラクトのみに実行を委譲し、ユーザー提供のアドレスには委譲しないでください。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>フロントランニングは、イーサリアム DApps に蔓延する問題です。DApp 開発者は、必ずしもフロントランニングを念頭に置いて DApp を設計するという考え方を持っているわけではありません。これは、この問題を提起し、この種の攻撃に対する認識を高めるための試みです。これらの攻撃を緩和するために、いくつかの DApp レベルのアプリケーション ロジックを構築することもできますが、さまざまな DApp カテゴリにまたがって遍在していることから、ブロックチェーン レベルでの緩和がおそらくより効果的であることが示唆されます。私たちはこれを重要な研究分野として強調しています。フロントランニングとは、企業が今後の取引や取引に関する特権的な市場情報に事前にアクセスすることで利益を得る一連の行動であると考えています。フロントランニングは、1970 年代以降の金融商品市場における問題でした。ブロックチェーン技術の出現により、フロントランニングは私たちがここで探求する新しい形で再浮上しました.&nbsp;ブロックチェーンの分散型で透過的な性質によって引き起こされます。このホワイト ペーパーでは、イーサリアム ブロックチェーンにデプロイされた上位 25 の最もアクティブな分散型アプリケーション (DApps) に散在する一連の知識とフロント ランニングのインスタンスから引き出します。さらに、Status.im のイニシャル コイン オファリング (ICO) の詳細な分析を実施し、トークンの先行購入を示す異常なマイナーの行動の証拠を示します。最後に、フロントランニングに提案されたソリューションを有用なカテゴリにマッピングします&nbsp;私はイニシャル コイン オファリング (ICO) を行っており、トークンの先行購入を示す異常なマイナーの行動の証拠を示しています。最後に、フロントランニングに提案されたソリューションを有用なカテゴリにマッピングします&nbsp;私はイニシャル コイン オファリング (ICO) を行っており、トークンの先行購入を示す異常なマイナーの行動の証拠を示しています。最後に、フロントランニングに提案されたソリューションを有用なカテゴリにマッピングします</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/Improving-Overall-Security" target="_blank" rel="noreferrer noopener">GitHub</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">テレグラム: https://t.me/cryptodeeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/HVh_cbsgSMg" target="_blank" rel="noreferrer noopener"><strong>ビデオ: https://youtu.be/HVh_cbsgSMg</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/improving-overall-security" target="_blank" rel="noreferrer noopener">ソース: https://cryptodeeep.ru/improving-overall-security</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1999} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2023/03/035-1-1024x576.png" alt="スマート コントラクトへの攻撃からエコシステム全体のセキュリティを向上させる" class="wp-image-1999"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
