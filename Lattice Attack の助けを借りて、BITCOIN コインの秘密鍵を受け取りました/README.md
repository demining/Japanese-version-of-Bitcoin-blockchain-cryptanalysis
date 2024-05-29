# Lattice Attack の助けを借りて、BITCOIN コインの秘密鍵を受け取りました

<!-- wp:embed {"url":"https://www.youtube.com/embed/YP4Xj6gUcf4","type":"rich","providerNameSlug":"","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/YP4Xj6gUcf4
</div></figure>
<!-- /wp:embed -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>グリッド攻撃について私たちは何を知っていますか?</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>まず、&nbsp;<em>楕円曲線デジタル署名アルゴリズムは、</em>&nbsp;<code>(ECDSA)</code>&nbsp;多くのコード レビューで見られる一般的なデジタル署名スキームです。これにはいくつかの望ましい特性がありますが、秘密の nonce の 1 ビット未満しか明らかにしないサイドチャネル攻撃で秘密鍵を回復するのは非常に脆弱な場合もあります。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>ECDSA</code>&nbsp;デジタル署名アルゴリズムの特別な形式です&nbsp;<code>(DSA)</code>。&nbsp;<code>DSA</code>&nbsp;はかなり一般的なデジタル署名スキームであり、鍵生成、署名、および検証の 3 つのアルゴリズムによって定義されます。&nbsp;<em>鍵生成アルゴリズムは、秘密鍵と公開鍵を生成します。</em>&nbsp;<em>秘密鍵は署名の作成を担当します。</em>&nbsp;<em>公開鍵は署名の検証を担当します。</em>&nbsp;署名アルゴリズムは、メッセージと秘密鍵を入力として受け取り、署名を生成します。検証アルゴリズムは、メッセージ、署名、および公開鍵を入力として受け取り、署名が有効かどうかを示す<code>true</code>&nbsp;または の&nbsp;値を返します&nbsp;。<code>false</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><code>DSA</code>&nbsp;は任意の数学的グループに対して定義されており、このスキームは離散対数問題がそのグループにとって難しい限り安全です。一般的に使用されるグループは、素数 p を法とする整数です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>このグループに加えて、グループ ジェネレータ g といくつかの暗号的に安全なハッシュ</em>&nbsp;関数&nbsp;があります&nbsp;<code>H</code>。私たちはそれを仮定することができ&nbsp;<code>p , g</code>&nbsp;、&nbsp;<code>H</code>&nbsp;常識になるでしょう。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>x</code>&nbsp;鍵生成は、最初にモジュロ整数から&nbsp;値をランダムに選択することによって機能します&nbsp;<code>p</code>&nbsp;。次に、値が計算されます&nbsp;<code>y = g^x mod p</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>署名の秘密鍵は&nbsp;<code>x</code>&nbsp;、公開鍵は です&nbsp;<code>y</code>&nbsp;。署名キーは、署名を作成できるようにするものであるため、秘密にしておく必要があります。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>署名アルゴリズムは、メッセージ&nbsp;<code>m</code>&nbsp;と秘密鍵 x から署名を作成します。まず、乱数群の要素が生成されます&nbsp;<code>k</code>&nbsp;。これはナンスとして知られており、攻撃に関しては重要です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>次に、値が計算され&nbsp;<code>r = g^k mod p</code>&nbsp;、&nbsp;<code>s = ( k^-1 ( H ( m ) + xr )) mod p</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ここで&nbsp;<code>k^- 1</code>&nbsp;、 は逆群で、 は&nbsp;<code>H ( m )</code>&nbsp;ハッシュ m を計算し、その結果を p を法とする整数として解釈した結果です。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>署名は のペアとして定義されます&nbsp;<code>( r , s )</code>。(注:&nbsp;<code>r</code>&nbsp;または&nbsp;のいずれかの値<code>s</code>が と等しい&nbsp;場合<code>0</code>、アルゴリズムは の新しい値で再開されます&nbsp;<code>k</code>&nbsp;)。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>( r , s )</code>検証アルゴリズムは、署名、メッセージ、&nbsp;および公開鍵 yを入力として&nbsp;受け取ります<code>m</code>&nbsp;。とする&nbsp;<code>ŝ = s^-1</code>&nbsp;と、アルゴリズムは true を返すのは、 の場合のみです&nbsp;<code>r , s ≠ 0 и r = ( g H ( m ) y r ) ŝ</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>この検証チェックが機能する理由は&nbsp;<code>g^H( m ) y^r = g^H(m)+ xr = g^ks</code>、したがって&nbsp;<code>(g^H(m)y^r)^ŝ = g^k = r</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>デジタル署名方式は、偽造できない場合、安全であると見なされます。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>不変性には正式な暗号化の意味がありますが、大まかに言えば、秘密鍵を知らなければ署名を作成できないことを意味します (秘密鍵から作成された既存の署名をコピーした場合を除く)。<code>DSA</code>離散ログの仮定の下で偽造することは不可能であることが証明されています&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>デジタル署名は、数学グループに対して定義されます。<code>DSA</code>&nbsp;この数学的グループとして楕円曲線のグループで使用される&nbsp;場合&nbsp;、それを と呼びます<code>ECDSA</code>。&nbsp;<em>楕円曲線グループは</em>、&nbsp;ある の&nbsp;<code>( x , y )</code>方程式を満たす&nbsp;&nbsp;のペアである楕円曲線ポイントで構成されます&nbsp;&nbsp;。&nbsp;このブログ投稿で知っておく必要があるのは、楕円曲線を使用して有限群を定義できるということです。つまり、群生成器 (楕円曲線の点) と、これとまったく&nbsp;&nbsp;同じよう<em><u>に</u></em>加算演算とドット乗算演算が得られることを意味&nbsp;<em>し</em>ます&nbsp;<em><u>。</u></em>整数を使用できます。それらは有限群、ジェネレータ、<code>y^2 = x^3 + ax + b</code><code>a , b</code><code>g</code>&nbsp;<em></em><em><u></u></em><em><u></u></em><code>g</code>&nbsp;、有限次数、 になります&nbsp;<code>p</code>。<em>このブログ投稿では、これらの楕円曲線</em>演算がどのように機能するかを説明したり、知っている必要はありません&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>秘密鍵は、</em>&nbsp;<code>x</code>&nbsp;整数を法とするランダムな値のままです&nbsp;<code>p</code>&nbsp;。<code>ECDSA</code>&nbsp;と同じように機能します&nbsp;<code>DSA</code>が、グループが異なります。&nbsp;g が楕円曲線上の点であることを除いて、公開鍵&nbsp;<code>y</code>&nbsp;は引き続き として計算されます&nbsp;。<code>y = g^x</code>これは、y も楕円曲線上の点になることを意味します (以前は、y は p を法とする整数でした)。もう 1 つの違いは、 r の値を計算する方法です。以前と同様に、p を法とする整数としてランダムなナンス k を生成します。を計算します&nbsp;<code>g^k</code>&nbsp;が、<code>g</code>&nbsp;は楕円曲線の点であり、したがって、&nbsp;<code>g^k</code>&nbsp;も同様です。したがって、 を計算&nbsp;<code>( x^k , y^k ) = g^k</code>&nbsp;して設定&nbsp;できます<code>r = x^k</code>&nbsp;。もう意味は&nbsp;<code>s</code>&nbsp;は以前と同じように計算でき、&nbsp;以前と同じように を<code>( r , s )</code>法とする整数のままである&nbsp;signature を取得します<code>p</code>&nbsp;。確認するには、計算方法が&nbsp;<code>r</code>&nbsp;少し異なっていたという事実を修正する必要があります。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>したがって、前と同様に の&nbsp;&nbsp;値を&nbsp;<em>計算します</em><code>( g^H(m)y^r)^ŝ</code>&nbsp;が、その値は楕円曲線上の点であるため、その点の座標を取得し&nbsp;<code>x</code>、それを の値と比較します&nbsp;<code>r</code>&nbsp;。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>&nbsp;再利用されたナンスからの&nbsp;<u>秘密鍵</u>の回復&nbsp;</em><code>NONCES</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>それが何であり、どのように機能するかを理解したので&nbsp;、その<em><u>脆弱性</u></em><code>ECDSA</code>&nbsp;を示しましょう&nbsp;.&nbsp;<em>繰り返しますが、これはデジタル署名スキームであるため、秘密鍵</em>&nbsp;はメッセージに署名した人以外には絶対に明かされないようにする必要があります&nbsp;。<em><u></u></em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ただし、署名者が署名を発行し、使用されたノンスも発行した場合、&nbsp;<em>攻撃者はすぐに</em><em><u>秘密鍵</u></em>&nbsp;を復元できます&nbsp;。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><code>( r , s )</code>&nbsp;メッセージの&nbsp;署名を解放し&nbsp;<code>m</code>&nbsp;、誤って nonce を使用していることを発見したとしましょ&nbsp;う<code>k</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s = ( k^-1 ( H ( m ) + xr )),</code>&nbsp;秘密鍵は簡単に計算できるので&nbsp;:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s = (k^-1(H(m) + xr))</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>ks = H(m) + xr</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>ks – H(m) = xr</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>x = r^-1(ks – H(m))</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>したがって、署名者は自分の&nbsp;<em><u>秘密鍵を</u></em>秘密にしておく必要があるだけでなく、これまでに生成したすべての nonce を秘密にする必要があります。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>署名者が各&nbsp;<em><u>ナンスを&nbsp;</u></em><code>NONCES</code>秘密にしていても、誤って 1 つの&nbsp;<em><u>ナンス</u></em>&nbsp;<code>NONCES</code>を繰り返した場合&nbsp;(異なるメッセージであっても)、&nbsp;<em><u>秘密鍵</u></em><strong>もすぐに復元</strong>&nbsp;できます&nbsp;。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>&nbsp;メッセージと&nbsp;&nbsp;(それぞれ) 同じ nonce から&nbsp;&nbsp;作成された 2 つの署名とします&nbsp;<code>( r , s 1 )</code>&nbsp;。&nbsp;同じ&nbsp;&nbsp;nonce を持っているため、r の値は同じになり、攻撃者がこれを検出するのは非常に簡単です。<code>( r , s 2 )</code><code>m 1</code><code>m 2</code><code>k</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s1 = k^-1(H(m1) + xr) and s2 = k^-1(H(m2) + xr)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s1 – s2 = k^-1(H(m1) – H(m2))</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>k(s1 – s2) = H(m1) – H(m2)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>k = (s1 – s2)^-1(H(m1) – H(m2))</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>上記の式を使用してノンスを回復したら&nbsp;<code>k</code>&nbsp;、前述の攻撃を実行して秘密鍵を回復できます。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading">ちょっと消化してみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em><u>署名ナンス&nbsp;</u></em><code>NONCES</code>&nbsp;が明らかになった&nbsp;場合&nbsp;、<em>秘密鍵はすぐに</em><em><u>回復</u></em>でき&nbsp;、&nbsp;<strong><u>署名スキーム全体が壊れます</u></strong>。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>また、2 つの nonce が繰り返される場合、メッセージが何であれ、&nbsp;<em>攻撃者は</em>&nbsp;これを簡単に検出し、すぐに&nbsp;<strong>秘密鍵を復元して</strong>、スキーム全体を破ることができます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>かなり脆くて軽い攻撃</em>ばかり&nbsp;！</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;しかし、非常に詳細に説明されている&nbsp;<em>新しい</em>&nbsp;<strong><a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">ラティス アット タック</a></strong><a href="https://youtu.be/YP4Xj6gUcf4"><strong>が</strong></a>あります&nbsp;<a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener"><em>(Joachim Breitner と Nadia Heninger)。</em></a><code>Йоахим Брайтнер и Надя Хенингер</code><a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">&nbsp;<em></em></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ドキュメント&nbsp;<a href="https://eprint.iacr.org/2019/023.pdf" target="_blank" rel="noreferrer noopener">[PDF]</a>&nbsp;:&nbsp;&nbsp;<em>Biased Nonce Sense: 暗号通貨の弱い ECDSA 署名に対する格子攻撃</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2 class="wp-block-heading">ビットコイン ブロックチェーンで、特定のトランザクションが見つかりました。</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>トランザクション:&nbsp;&nbsp;<a href="https://www.blockchain.com/btc/tx/08d917f0fee48b0d765006fa52d62dd3d704563200f2817046973e3bf6d11f1f" target="_blank" rel="noreferrer noopener">08d917f0fee48b0d765006fa52d62dd3d704563200f2817046973e3bf6d11f1f</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ビットコインアドレスの場合:&nbsp;&nbsp;<a href="https://www.blockchain.com/btc/address/15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E" target="_blank" rel="noreferrer noopener">15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E</a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>そして、偽の署名を増やしてグリッドを適用することができました</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong>GOOGLE COLAB</strong>&nbsp;にパッケージをインストールして&nbsp;<em>Python スクリプト</em>&nbsp;<a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">algorithmLLL.py</a>を使用する場合&nbsp;<strong></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>インストール &gt;&gt; SAGE + ECDSA + BITCOIN + アルゴリズム LLL</strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>&nbsp;で 1 つの脆弱なトランザクションから&nbsp;なんとか<code>Private Key</code>&nbsp;取得&nbsp;できました&nbsp;。<code>Bitcoin Wallet</code><code>ECDSA</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/777/37e/84b/77737e84bb453449fd6956a39c4eb195.png" alt="インストール" title="インストール"/><figcaption class="wp-element-caption">インストール</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ae2/0b3/747/ae20b37475bfff1ce38f81cc206a93f3.png" alt="Bash スクリプトを実行します：lattice.sh" title="Bash スクリプトを実行します：lattice.sh"/><figcaption class="wp-element-caption">Bash スクリプトを実行します：lattice.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/722/89e/9da/72289e9dab54d5aa568438a94a4c90a6.png" alt="HEX形式の結果 秘密鍵が見つかりました！" title="HEX形式の結果 秘密鍵が見つかりました！"/><figcaption class="wp-element-caption">HEX形式の結果 秘密鍵が見つかりました！</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/469/217/84b/46921784bb73f1218ded9e16bc0f8abd.png" alt="ファイル: ONESIGN.txt (ECDSA 署名 R、S、Z 値)" title="ファイル: ONESIGN.txt (ECDSA 署名 R、S、Z 値)"/><figcaption class="wp-element-caption">ファイル: ONESIGN.txt (ECDSA 署名 R、S、Z 値)</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8cb/e22/f9c/8cbe22f9cd364064a8e005ac8ea4e99e.png" alt="Python スクリプト algorithmLLL.py の偽の署名を広めました" title="Python スクリプト algorithmLLL.py の偽の署名を広めました"/><figcaption class="wp-element-caption">Python スクリプト algorithmLLL.py の偽の署名を広めました</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/83f/750/d81/83f750d81ba83309039189495a10680a.png" alt="ファイル: PRIVATEKEY.txt" title="ファイル: PRIVATEKEY.txt"/><figcaption class="wp-element-caption">ファイル: PRIVATEKEY.txt</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/202/982/105/2029821051232d8a95744863eaa65049.png" alt="ファイル: ADDRESS.txt" title="ファイル: ADDRESS.txt"/><figcaption class="wp-element-caption">ファイル: ADDRESS.txt</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a>を開いて確認しましょう&nbsp;&nbsp;：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4ce/93f/dd1/4ce93fdd168a7acc734929d342c8949c.png" alt="bitaddress の Web サイトで秘密鍵を確認する" title="bitaddress の Web サイトで秘密鍵を確認する"/><figcaption class="wp-element-caption">bitaddress の Web サイトで秘密鍵を確認する</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em><u>秘密鍵が見つかりました！</u></em></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E
</div></figure>
<!-- /wp:embed -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/00c/be7/072/00cbe70723846c402c4da47bcb6d47b3.png" alt="0.001BTC" title="0.001BTC"/><figcaption class="wp-element-caption">0.001BTC</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E
WIF:  5JCAmNLXeSwi2SCgNH7wRL5qSQhPa7sZvj8eDwxisY5hJm8Uh92
HEX:  31AFD65CAD430D276E3360B1C762808D1D051154724B6FC15ED978FA9D06B1C1 </code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/lattice-attack" target="_blank" rel="noreferrer noopener"><strong>このビデオは、 CRYPTO DEEP TECH</strong></a>ポータル向けに作成されたもので、&nbsp;&nbsp;ビットコイン暗号通貨の脆弱な ECDSA 署名に対するデータと secp256k1 楕円曲線暗号の財務セキュリティを確保します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>&nbsp;<a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">https://youtu.be/YP4Xj6gUcf4</a></strong>&nbsp;–<strong>動画素材</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>cryptodeeptech@gmail.com – すべての質問はメールで</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeep_tech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeep_tech</a>&nbsp;– Telegram による技術サポート</strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/YP4Xj6gUcf4","type":"rich","providerNameSlug":"","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/YP4Xj6gUcf4
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
