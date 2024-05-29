# secp256k1 楕円曲線の便利で効率的なアルゴリズム

<!-- wp:embed {"url":"https://www.youtube.com/embed/gFbiBCNPsFk","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/gFbiBCNPsFk
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;この記事では、次の短いワイエルシュトラス方程式によって与えられる&nbsp;体&nbsp;<strong><em>GF(p)上の楕円曲線</em></strong><strong><em>E</em></strong>に対するいくつかの有用で効率的なアルゴリズムを検討します。&nbsp;<strong><em></em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>у^2&nbsp;= х^3&nbsp;+ Ах + В</code>&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>&nbsp;<strong><em>曲線E</em>上の点を生成するアルゴリズム&nbsp;<em></em></strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>ポイントを追加するアルゴリズム</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>倍加点アルゴリズム</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>整数倍点を求めるアルゴリズム</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>整数倍点を求めるアルゴリズム（スカラー倍算）</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>&nbsp;指定されたサイズ&nbsp;<em>d</em>の&nbsp;サポート&nbsp;<em>supp(D)</em>を使用して、&nbsp;曲線&nbsp;<em>E</em>上の除数&nbsp;<em>Dを構築するためのアルゴリズム</em><em></em><em></em><em></em></strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong><em><sub></sub></em><em></em></strong><em>supp(D)</em>&nbsp;&nbsp;∩ {P, O} = ∅<strong>&nbsp;となる&nbsp;除数</strong><strong><em>D</em></strong><strong>&nbsp;から&nbsp;ヴェイユ関数</strong><strong><em>f&nbsp;&nbsp;</em></strong><strong><em><sub>n, P</sub></em></strong><strong>の値を計算するミラーのアルゴリズム&nbsp;</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>ペアリング</strong>&nbsp;<em>・ヴェイユ</em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>有限体 (またはガロア体) でのモジュラー演算 (整数)</h4>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><em>x mod n は</em>&nbsp;「x を割った余り n」を意味します。言い換えれば、&nbsp;&nbsp;<em>x = an + b</em>&nbsp;かつ a, b ∈ integer で、0 ≤ b ≤ n − 1 の場合、&nbsp;&nbsp;<em>x mod n = b</em>です&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>逆</strong>&nbsp;:&nbsp;&nbsp;<em>ax = 1 mod n</em>の場合&nbsp;、&nbsp;&nbsp;<em>aは</em><em>x mod n</em>&nbsp;の逆数です&nbsp;&nbsp;。一般的な解法が&nbsp;<em>2</em>つあります&nbsp;。 •&nbsp;<strong><em>方法 1</em></strong><em>&nbsp;: xa mod n = 1</em>&nbsp;である限り、&nbsp;&nbsp;<em>a &lt; n</em>&nbsp;の各値を試します&nbsp;&nbsp;。 •&nbsp;<strong><em>方法 2</em></strong>&nbsp;&nbsp;: 大きな整数の逆問題を解くために通常使用されるユークリッド法なので、推奨方法 1 を使用して、小さい整数の逆問題を解く。<em></em><strong><em></em></strong></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>楕円曲線ポイント操作</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>&nbsp;楕円曲線&nbsp;<em>E</em>上の点&nbsp;<em>P(x&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;, y&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;)</em>は&nbsp;、その&nbsp;<em>x&nbsp;&nbsp;</em><em><sub>0</sub></em>&nbsp;および&nbsp;<em>y&nbsp;&nbsp;</em><em><sub>0</sub></em>座標が&nbsp;体の要素であり、&nbsp;&nbsp;<em>x&nbsp;&nbsp;</em><em><sub>0</sub></em>&nbsp;および&nbsp;<em>y&nbsp;&nbsp;</em><em><sub>0</sub></em>座標&nbsp;が式を満たすことを意味します。<em></em><em><sub></sub></em><em><sub></sub></em><em><sub></sub></em><em><sub></sub></em></p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><strong>楕円曲線上の点の追加</strong>&nbsp;:&nbsp;&nbsp;<em>P、Q</em>&nbsp;&nbsp;、&nbsp;&nbsp;<em>R</em>&nbsp;を楕円曲線上の 3 点とします。ポイントの追加 P + Q = R.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>楕円曲線上の点を 2 倍にする</strong>&nbsp;:&nbsp;&nbsp;<em>P, Q</em>&nbsp;を楕円曲線上の 2 点とします。ポイントを倍増 P + P = 2P = Q</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>ドット乗算</strong> :  <em>Pを曲線</em><em>E</em> 上の点とし  、式で定義されます。<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>ドット乗算&nbsp;<em>nP は、</em><em>nP = P + P + P + ... + P</em>&nbsp;&nbsp;(&nbsp;&nbsp;<em>n</em>&nbsp;回)&nbsp;&nbsp;として定義されます&nbsp;。ここで、&nbsp;<em>n</em>&nbsp;は整数です。&nbsp;<em>nPも同じ</em><em>E</em>カーブ&nbsp;上のポイントです&nbsp;&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>aP = O</em>である最小の自然数 a を&nbsp;<strong><em>P</em></strong><strong>の次数と&nbsp;<em></em></strong>&nbsp;呼びます&nbsp;&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ドット乗算は、楕円曲線暗号システムで広く必要とされています。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>分周器</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>除数</strong>&nbsp;(除数)&nbsp;&nbsp;曲線&nbsp;<em>E上の</em><em>D は</em>&nbsp;、正式な和として書かれた<strong><em>E</em></strong><strong>上の点の集合&nbsp;</strong>&nbsp;を表す便利な方法です。&nbsp;<em></em><strong><em></em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/0b1/3e2/fbe/0b13e2fbec01a2ea5635bbcb1a36ade1.png" alt="secp256k1 楕円曲線の便利で効率的なアルゴリズム" title=""/></figure>
<!-- /wp:image -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>E</em>上のすべての約数の集合は&nbsp;<em>Div&nbsp;&nbsp;<sub>F q</sub>&nbsp;&nbsp;(E)</em>&nbsp;で表され&nbsp;&nbsp;、約数の追加が自然なグループを形成します。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><sub>ゼロ除数: これはすべての n P</sub>&nbsp;= 0の除数です&nbsp;&nbsp;。ゼロ除数&nbsp;<em>は 0 ∈ Div&nbsp;&nbsp;<sub>F q</sub>&nbsp;&nbsp;(E)</em>です&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>フィールド&nbsp;<em>F&nbsp;&nbsp;<sub>q</sub></em>が特定されていない場合は、&nbsp;除数グループを示すために省略して<em>Div(E)</em>&nbsp;と簡単に書くことができます&nbsp;。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>関数 f を E で割った値</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>関数&nbsp;<em>f</em>&nbsp;の&nbsp;<em>Eによる除数は、関数</em><em>f</em>&nbsp;と&nbsp;<em>E</em>&nbsp;の交点 (およびそれらの多重度) を表すために使用されます&nbsp;&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>ペアリング・ヴェイユ</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>e&nbsp;&nbsp;<sub>m</sub></em>で表されるワイルペアリングは&nbsp;&nbsp;、点のペア P, Q ∈ E[m] を入力として取り&nbsp;<em>、&nbsp;<sub></sub></em>&nbsp;出力として&nbsp;<em><sup>e&nbsp;&nbsp;<sub>m</sub></sup><sub>&nbsp;(</sub>&nbsp;&nbsp;P , Q)のルート _m</em><em><sub>を生成します</sub></em>&nbsp;。ワイルペアリングの双線形性は、次の式で表されます。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;+ P&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;, Q) = e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;, Q) * e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P2, Â),</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;+ Q&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;) = e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;) * e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;)。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>ヴェイユの&nbsp;</strong>ペア&nbsp;<em>P</em>&nbsp;と&nbsp;<em>Q</em>&nbsp;は数</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/5eb/b85/30f/5ebb8530fd881d89d3f396460464af79.png" alt="secp256k1 楕円曲線の便利で効率的なアルゴリズム" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>ここで、&nbsp;&nbsp;<em>S ∈ E は</em>&nbsp;、条件&nbsp;<em>S ∉ {O, P, −Q, P − Q}</em>を満たす任意の点です&nbsp;。(これにより、右辺のすべての量が定義され、ゼロでないことが保証されます。)&nbsp;&nbsp;<em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P,Q)の値が</em><em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;、&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>Q</sub></em>&nbsp;、&nbsp;および&nbsp;<em>S</em>&nbsp;の選択に依存しないこと&nbsp;を確認できます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>効率的な Weil Pairing 計算アルゴリズム</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>E</em>を&nbsp;&nbsp;楕円曲線とし、P = (x&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;,y&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;) と Q = (x&nbsp;&nbsp;<sub>Q</sub>&nbsp;&nbsp;, y&nbsp;&nbsp;<sub>Q ) を</sub><em>E</em>&nbsp;上の非ゼロ点とします&nbsp;&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>P</em>&nbsp;と&nbsp;<em>Q</em>&nbsp;を結ぶ直線の傾き&nbsp;、または<em>P =</em>&nbsp;Q&nbsp;の場合は P における&nbsp;<em>E</em>&nbsp;の接線の傾きを&nbsp;λ&nbsp;&nbsp;とします (直線が垂直の場合、&nbsp;&nbsp;<em>λ</em>&nbsp;&nbsp;= ∞ とします) 関数 g&nbsp;&nbsp;<sub>P, Q</sub><em>を</em>&nbsp;定義&nbsp;します。&nbsp;<em>E</em>&nbsp;次のとおりです。<em></em><em></em><em></em><em></em><em></em><sub></sub><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/dbc/8cd/efc/dbc8cdefc33de28911b8e41530a16687.png" alt="secp256k1 楕円曲線の便利で効率的なアルゴリズム" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>それから</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>div(g&nbsp;&nbsp;<sub>P, Q</sub>&nbsp;&nbsp;) = [P] + [Q] — [P + Q] —&nbsp;&nbsp;&nbsp;[&nbsp;<em>O</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>ミラーのアルゴリズム</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>m ≥</em>とし&nbsp;、&nbsp;<em>m</em>&nbsp;の 2 進拡張を&nbsp;&nbsp;次のように記述します。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>m = m&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;+ m&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;* 2 + m&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;* 2&nbsp;&nbsp;<sup>2</sup>&nbsp;&nbsp;+···+ m&nbsp;&nbsp;<sub>n — 1</sub>&nbsp;&nbsp;2&nbsp;&nbsp;<sup>n — 1</sup></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>m&nbsp;&nbsp;<sub>i</sub>&nbsp;&nbsp;∈ {0, 1}</em>&nbsp;および&nbsp;<em>m&nbsp;&nbsp;<sub>n_1</sub>&nbsp;&nbsp;≠ 0</em>の場合&nbsp;&nbsp;。&nbsp;次のアルゴリズムは、除数が条件を満たす関数&nbsp;<em>f&nbsp;&nbsp;<sub>Pを返します。</sub></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>div(&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;) =&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;] — [&nbsp;&nbsp;<em>mP</em>&nbsp;&nbsp;] — (&nbsp;&nbsp;<em>m — 1</em>&nbsp;&nbsp;) [&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;],</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;ここで、アルゴリズムで使用される関数&nbsp;<em>g&nbsp;&nbsp;<sub>T, T</sub></em>&nbsp;および&nbsp;<em>g&nbsp;&nbsp;<sub>T, P は(a) で定義されます。</sub></em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/bc1/d75/c60/bc1d75c6060123845b0b7f4b153096b0.png" alt="secp256k1 楕円曲線の便利で効率的なアルゴリズム" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>特に、&nbsp;&nbsp;<em>P ∈ E[m]</em>の場合&nbsp;、div(&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;) =&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;] −&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;] です。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>要件</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Python 3.5</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>numpy</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/04AlgorithmsForSecp256k/

pip3 install numpy</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>├── Curves.py             &lt;- Набор данных эллиптических кривых
├── Divisor.py            &lt;- Создать делитель
├── EllipticCurve.py      &lt;- Классы эллиптической кривой и точки на эллиптической кривой
├── EuclideanAlg.py       &lt;- Расширенный алгоритм Евклида
├── Helper.py             &lt;- Вспомогательные функции (обратные биты, мощность по модулю) 
├── Pairing.py            &lt;- Спаривания Вейля, а так же Алгоритм Миллера
├── Tests.py              &lt;- Модульные тесты для функций
├── Tonelli_ShanksAlg.py  &lt;- Алгоритм Тонелли – Шенкса
├── main.py               &lt;- main
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3></h3>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/04AlgorithmsForSecp256k" target="_blank" rel="noreferrer noopener">ソース</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>テレグラム:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>動画素材：&nbsp; https:&nbsp;<a href="https://youtu.be/gFbiBCNPsFk" target="_blank" rel="noreferrer noopener">//youtu.be/gFbiBCNPsFk</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/gFbiBCNPsFk","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/gFbiBCNPsFk
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
