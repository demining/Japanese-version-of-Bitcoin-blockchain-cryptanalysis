# LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します

<!-- wp:embed {"url":"https://www.youtube.com/embed/CzaHitewN-4","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/CzaHitewN-4
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru//doc/Hidden-Number-Problems.pdf" target="_blank" rel="noreferrer noopener">私たちの初期の作品では、 HNP [Hidden Number 問題] の</a></strong>完全な解決策として<a href="https://cryptodeeptech.ru/lattice-attack" target="_blank" rel="noreferrer noopener"><strong>「LATTICE ATTACK」</strong></a>というトピックに関する記事を公開しましたが、最近新たな攻撃<a href="https://cryptodeeptech.ru/polynonce-attack" target="_blank" rel="noreferrer noopener"><strong>「POLYNONCE ATTACK」</strong></a>が出現したため、以下を使用して記事を補足することにしました。。<strong><a href="https://cryptodeep.ru//doc/Hidden-Number-Problems.pdf" target="_blank" rel="noreferrer noopener"></a></strong><a href="https://cryptodeeptech.ru/polynonce-attack" target="_blank" rel="noreferrer noopener"><strong></strong></a><code>79 signatures ECDSA</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>多項式を取得した前の記事に基づいて、<code>128 bits</code>実際の署名数の増加により、多項式の値を にします<code>249 bits</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>私たちに必要なのは、隠された数字の問題を解決することだけです。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3357} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-285.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3357"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この記事では、ビットコイン ブロックチェーンの暗号解析の 5 つの独立した例を分析します。<strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/21LatticeAttack" target="_blank" rel="noreferrer noopener">すべてのサンプルはGitHub</a></strong>リポジトリにアップロードされます。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">理論的基礎として、次の資料を使用します。</h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://attacksafe.ru/lattice-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener">「ビットコインに対する格子攻撃」</a></h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3352,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-284.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3352"/><figcaption class="wp-element-caption"><code><a href="https://attacksafe.ru/lattice-attack-on-bitcoin" target="_blank" rel="noreferrer noopener">https://attacksafe.ru/lattice-attack-on-bitcoin</a></code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ビットコイン アドレスの例を考えてみましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/address/19mJofzRwwwx4VmXuAXgX6pgM3qzJqi25z" target="_blank" rel="noreferrer noopener"><strong>19mJofzRwwwx4VmXuAXgX6pgM3qzJqi25z</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3074} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-160.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3074"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/tx/6a941396b28a72ac834d922165995e6685a760f884dbb9e8b6dea95b01f0aae8" target="_blank" rel="noreferrer noopener"><strong>6a941396b28a72ac834d922165995e6685a760f884dbb9e8b6dea95b01f0aae8</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3079} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-165-1024x638.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3079"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">RawTX</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3080} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-166-1024x371.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3080"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>"hex": 010000000afa0765dc83c2e04b53a03ad9f5e7603f974c5a70e7a486bc957e72809facab7b2d0000006a4730440220746bd0443317a77c069bddae306dc658ec740bb1a6312bdcb4ce666bae42e988022066c34dd48f0e34ae4aefd28564f46fb7473d0b49d55adb716b9f04e663d0a9890121033ee89b98b1d6e71285314e1d1c753003a7a80c17f46146a91077006c76e25e7affffffff................................</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>公式ウェブサイトにアクセスしましょう:&nbsp;&nbsp;<strong><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">https://colab.research.google.com</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><strong>「ノートブックをアップロード」</strong><em>オプションを選択します&nbsp;</em><strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2709} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-50.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-2709"/></figure>
<!-- /wp:image --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>ファイルをダウンロードします:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/LATTICE_ATTACK_249bits.ipynb" target="_blank" rel="noreferrer noopener"><strong>LATTICE_ATTACK_249bits.ipynb</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2711} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-52.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-2711"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>HEX</code>ユーティリティを通じてデータをダウンロードし<code>wget</code>&nbsp;、ファイル<strong>RawTX.txtに保存します。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://raw.githubusercontent.com/demining/CryptoDeepTools/main/21LatticeAttack/example1/HEX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3081} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-167-1024x279.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3081"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>コードを実行して必要な部分を取得しましょう<code><strong>RawTX</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>with open("HEX.txt") as myfile:

    listfile="\n".join(f'{line.rstrip()&#91;:+298]}' for line in myfile)


f = open("RawTX.txt", 'w')
f.write("" + listfile + "" + "\n")
f.close()</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3083} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-169-1024x346.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3083"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>攻撃を実行するには、ソフトウェアを使用します。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;<strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener">攻撃安全なソフトウェア</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":705,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-14.png" alt="Frey-Rück 攻撃を実行して秘密鍵「K」(NONCE) を取得します" class="wp-image-705"/></a><figcaption class="wp-element-caption"><strong><code>www.attacksafe.ru/software</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">アクセス権：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!chmod +x attacksafe</code></pre>
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

<!-- wp:image {"id":3089} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-172.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3089"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">応用：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -help</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3091} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-173.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3091"/></figure>
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
<pre class="wp-block-code"><code>!./attacksafe -version</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3093} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-174.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3093"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Version 5.3.4. &#91;ATTACKSAFE SOFTWARE, © 2023]</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>"ATTACKSAFE SOFTWARE"</code>&nbsp;ビットコインに対する一般的な攻撃がすべて含まれます。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2 class="wp-block-heading">すべての攻撃のリストを実行してみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -list</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3097} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-175.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3097"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>選びましょう<code>&nbsp;-tool: lattice_attack</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>署名の特定の<code>HEX</code>値を取得するために、以前に&nbsp;ユーティリティを通じてデータをテキスト ドキュメントに追加し&nbsp;、ファイルとして保存しました。&nbsp;<code>&nbsp;R,S,Z</code><code>ECDSA</code><code>RawTX</code><code>echo</code><code>RawTX.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3101} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-176-1024x140.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3101"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><code>-tool lattice_attack</code>&nbsp;ソフトウェアを使用して&nbsp;起動する&nbsp;<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -tool lattice_attack -open RawTX.txt -save SignatureRSZ.csv</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3104} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-179-1024x462.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3104"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この攻撃は次から開始され&nbsp;<code>-tool lattice_attack</code>&nbsp;、結果はファイルに保存されました。&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>成功した結果を確認するには、ファイルを開いてください。&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3108} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-181-1024x445.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3108"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>ファイルからビットコインウォレットの秘密鍵を計算するために、&nbsp;&nbsp;<strong><a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab/" target="_blank" rel="noreferrer noopener">SageMath</a></strong><code>SignatureRSZ.csv</code>をインストールします。<strong><a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2188} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-27.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-2188"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2189} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-28-1024x445.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-2189"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>以前に<a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab/" target="_blank" rel="noreferrer noopener">記事</a>を公開しました。ダウンロード&nbsp;<code>tar-file</code>:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2" target="_blank" rel="noreferrer noopener"><strong>sage-9.3-Ubuntu_20.04-x86_64.tar.bz2</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2
!tar -xf sage-9.3-Ubuntu_20.04-x86_64.tar.bz2</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3114} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-184-1024x330.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3114"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>ディレクトリを見てみましょう。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd SageMath/</code></pre>
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

<!-- wp:image {"id":3118} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-186-1024x594.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3118"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><em>&nbsp;次のコマンドを使用して</em><strong>relocate-once.py</strong><em>を実行します&nbsp;。</em><code>Python-script:</code><em>&nbsp;</em><strong></strong><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!python3 relocate-once.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3119} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-187-1024x461.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3119"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>フォルダ<code>"AttackSafe"</code>に移動<code>"SignatureRSZ.csv"</code><code>"SageMath"</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!mv '/content/attacksafe' '/content/SageMath/attacksafe'
!mv '/content/SignatureRSZ.csv' '/content/SageMath/SignatureRSZ.csv'</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3124} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-190-1024x717.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3124"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3125} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-191-1024x386.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3125"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>Dario Clavijo からユーティリティを通じて&nbsp;スクリプト クラック<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/crack_weak_ECDSA_nonces_with_LLL.py" target="_blank" rel="noreferrer noopener">_weak_ECDSA_nonces_with_LLL.pyをダウンロードします。</a></strong><code>wget</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://raw.githubusercontent.com/demining/CryptoDeepTools/main/21LatticeAttack/crack_weak_ECDSA_nonces_with_LLL.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3130} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-193-1024x359.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3130"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><em>&nbsp;次に、コマンドを</em><em>実行してみましょう&nbsp;。</em><code>SageMath</code><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3132} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-194-1024x389.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3132"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ビットコイン ウォレットの秘密キーを計算するには、パラメータを指定してスクリプト クラック<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/crack_weak_ECDSA_nonces_with_LLL.py" target="_blank" rel="noreferrer noopener">_weak_ECDSA_nonces_with_LLL.pyを実行します。</a></strong><strong><code>249 bits 79 sign</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 crack_weak_ECDSA_nonces_with_LLL.py SignatureRSZ.csv 249 79 &gt; PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3136} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-195-1024x532.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3136"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを開いてみましょう:<code>PrivateKey.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>ビットコインウォレットへの秘密鍵を次の<code>HEX</code>形式で受け取りました。</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3139} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-197.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3139"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>PrivKey = 0x9a52a4dbcc148f1480a6fb5311252524fc498eb508c7cb8f63bbee4b9af37941</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">各 ECDSA 署名の POLYNONCE を確認する</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example1/POLYNONCE.py" target="_blank" rel="noreferrer noopener"><strong>これを行うには、 GITHUB</strong></a>のコードを使用します。<a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example1/POLYNONCE.py" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3142,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-200.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3142"/><figcaption class="wp-element-caption"><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example1/POLYNONCE.py" target="_blank" rel="noreferrer noopener"><code>https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example1/POLYNONCE.py</code></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">結果：</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3143} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-201.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3143"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>から 79 個の同一のオリジナル ビットを取得しました。<code>249</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist)" target="_blank" rel="noreferrer noopener">Hal Finney</a>&nbsp;&nbsp;の secp256k1 曲線の値のおかげで&nbsp;、&nbsp;<a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener">LAMBDA と BETA は</a>&nbsp;同じ初期ビットを明らかにしました。<code>POLYNONCE</code>この形式の値により、<code>HEX</code>隠された数字の問題を完全に解決し、秘密鍵を取得し、ビットコイン ウォレットを復元することができます。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">秘密キーの 16 進数を確認してみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>モジュールをインストールする<code>bitcoin</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!pip3 install bitcoin</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2799} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-86-1024x219.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-2799"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>コードを実行してみましょう:</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from bitcoin import *

with open("PrivateKey.txt","r") as f:
    content = f.readlines()

content = &#91;x.strip() for x in content]
f.close()


outfile = open("PrivateKeyAddr.txt","w")
for x in content:
  outfile.write(x+":"+pubtoaddr(encode_pubkey(privtopub(x), "bin_compressed"))+"\n")
 
outfile.close()</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2800} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-87.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-2800"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを開いてみましょう:<code>PrivateKeyAddr.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3144} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-202-1024x651.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3144"/><figcaption class="wp-element-caption"><code>9a52a4dbcc148f1480a6fb5311252524fc498eb508c7cb8f63bbee4b9af37941:19mJofzRwwwx4VmXuAXgX6pgM3qzJqi25z</code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a></strong>を開いて確認してみましょう&nbsp;&nbsp;:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 19mJofzRwwwx4VmXuAXgX6pgM3qzJqi25z
WIF:  L2PhDrYZw6fWqeLZMnMeAXvxZ47MEnepaQVLL2EazbRhqesytoQB
HEX:  9a52a4dbcc148f1480a6fb5311252524fc498eb508c7cb8f63bbee4b9af37941</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3147} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-bitaddress-4.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3147"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/19mJofzRwwwx4VmXuAXgX6pgM3qzJqi25z"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/19mJofzRwwwx4VmXuAXgX6pgM3qzJqi25z
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3153} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-205.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3153"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3154} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-206.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3154"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3155} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-207-1024x136.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3155"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 1015.58</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">他の例を見てみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>№<strong>2</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ビットコイン アドレスを使用した例 2 を考えてみましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1GPZVDUyPM6qxCsJQrpJeo14WDRVLvTZ2Z" target="_blank" rel="noreferrer noopener">1GPZVDUyPM6qxCsJQrpJeo14WDRVLvTZ2Z</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2788} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-82.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-2788"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/tx/9130c5b8e92f37d3a58dcae16daa27625cc52b698a83af7c8b891f01bfa0b2af" target="_blank" rel="noreferrer noopener"><strong>9130c5b8e92f37d3a58dcae16daa27625cc52b698a83af7c8b891f01bfa0b2af</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3159} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-208.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3159"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">RawTX</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3160} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-209-1024x379.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3160"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>"hex": 0100000041e981df9d37a7af6f5ee77abade3ec58acbf864f942bdecb63ea2efa593e2c3391f0000006b4830450221009d8ceef05e2fa0a623811df57265a3678f902e81dc82c3862d12bbb07b90de18022036bbed961b4f8665eb3fb3047a1398a1aeae519a8e2a1a97de57863fc0cc4a380121029755a17bf76237cde9e05fc333a255b926d526a7763abe725a4f6253ebdae109ffffffff..............................
 </code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>最初の例からファイルを削除しましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!rm HEX.txt
!rm RawTX.txt
!rm NoncesHEX.txt
!rm PrivateKey.txt
!rm SignatureRSZ.csv
!rm PrivateKeyAddr.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3162} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-210.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3162"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><code>HEX</code><em>ユーティリティを通じてデータを&nbsp;</em><em>ダウンロードし&nbsp;</em><code>wget</code><em>&nbsp;、ファイル&nbsp;</em><strong>RawTX.txtに保存します。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://raw.githubusercontent.com/demining/CryptoDeepTools/main/21LatticeAttack/example2/HEX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3167} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-211.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3167"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>コードを実行して必要な部分を取得しましょう&nbsp;</em><code><strong>RawTX</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>with open("HEX.txt") as myfile:

    listfile="\n".join(f'{line.rstrip()&#91;:+298]}' for line in myfile)


f = open("RawTX.txt", 'w')
f.write("" + listfile + "" + "\n")
f.close()</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3175} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-212-1024x376.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3175"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><code>-tool lattice_attack</code>&nbsp;ソフトウェアを使用して&nbsp;起動する&nbsp;<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -tool lattice_attack -open RawTX.txt -save SignatureRSZ.csv</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3178} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-213-1024x458.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3178"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この攻撃は次から開始され&nbsp;<code>-tool lattice_attack</code>&nbsp;、結果はファイルに保存されました。&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>成功した結果を確認するには、ファイルを開いてください。&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3180} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-214.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3180"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><em>&nbsp;コマンド</em><em>を実行しましょう&nbsp;:</em><code>SageMath</code><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3182} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-215.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3182"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>&nbsp;ビットコイン ウォレットの秘密キーを計算するには、パラメータを指定して&nbsp;スクリプト クラック&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/crack_weak_ECDSA_nonces_with_LLL.py" target="_blank" rel="noreferrer noopener">_weak_ECDSA_nonces_with_LLL.pyを実行します。</a></strong><strong><code>249 bits 79 sign</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 crack_weak_ECDSA_nonces_with_LLL.py SignatureRSZ.csv 249 79 &gt; PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3185} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-216-1024x509.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3185"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを開いてみましょう:&nbsp;<code>PrivateKey.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>ビットコインウォレットへの秘密鍵を次の&nbsp;<code>HEX</code>&nbsp;形式で受け取りました。</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3196} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-222.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3196"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>PrivKey = 0x00db251a1ab7cfa7679dfe61271d0af4bb9c68595178cf4c9237478eab2dba1d</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">各 ECDSA 署名の POLYNONCE を確認する</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example2/POLYNONCE.py" target="_blank" rel="noreferrer noopener"><strong>これを行うには、 GITHUB</strong></a>のコードを使用します。<a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example2/POLYNONCE.py" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3190,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-218.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3190"/><figcaption class="wp-element-caption"><code><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example2/POLYNONCE.py" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example2/POLYNONCE.py</a></code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">結果：</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3192} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-219.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3192"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>から 79 個の同一のオリジナル ビットを取得しました。</em><code>249</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist)" target="_blank" rel="noreferrer noopener">Hal Finney</a>&nbsp;&nbsp;の secp256k1 曲線の値のおかげで&nbsp;、&nbsp;<a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener">LAMBDA と BETA は</a>&nbsp;同じ初期ビットを明らかにしました。<code>POLYNONCE</code>この形式の値により、<code>HEX</code>隠された数字の問題を完全に解決し、秘密鍵を取得し、ビットコイン ウォレットを復元することができます。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">秘密キーの 16 進数を確認してみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>コードを実行してみましょう:</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from bitcoin import *

with open("PrivateKey.txt","r") as f:
    content = f.readlines()

content = &#91;x.strip() for x in content]
f.close()


outfile = open("PrivateKeyAddr.txt","w")
for x in content:
  outfile.write(x+":"+pubtoaddr(encode_pubkey(privtopub(x), "bin_compressed"))+"\n")
 
outfile.close()</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3193} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-220-1024x533.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3193"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを開いてみましょう:&nbsp;<code>PrivateKeyAddr.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3194} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-221-1024x657.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3194"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a></strong>を開いて確認してみましょう&nbsp;&nbsp;:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1GPZVDUyPM6qxCsJQrpJeo14WDRVLvTZ2Z
WIF:  KwFNhRPDpgD5X77T8x5oL628aHh9UtscwwrLjGBKE8NeLshYvAqC
HEX:  00db251a1ab7cfa7679dfe61271d0af4bb9c68595178cf4c9237478eab2dba1d</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3202} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-bitaddress-6.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3202"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/1GPZVDUyPM6qxCsJQrpJeo14WDRVLvTZ2Z"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/1GPZVDUyPM6qxCsJQrpJeo14WDRVLvTZ2Z
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3204} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-224.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3204"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3205} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-225.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3205"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3206} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-226-1024x149.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3206"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 999.10</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">他の例を見てみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>№<strong>3</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ビットコイン アドレスを使用した例 3 を考えてみましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/18Y9nUpdtxAKTh6yaN299jfUxcpJ2ApHz" target="_blank" rel="noreferrer noopener">18Y9nUpdtxAKTh6yaN299jfUxcpJ2ApHz</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3209} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-227.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3209"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/tx/0b21368bb6e6658adf4079b5ca6e7286c6e13471acef879168e7c17809476c76" target="_blank" rel="noreferrer noopener"><strong>0b21368bb6e6658adf4079b5ca6e7286c6e13471acef879168e7c17809476c76</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3210} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-228.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3210"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">RawTX</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3211} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-229-1024x378.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3211"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>"hex": 0100000041c7a8d97168ee154550f5e43b9074e5f357a4dc6b2350c96f75e377df0a39b9fa210000006b48304502210097d6b896929d77634b8d9430bc2842209cad42bb236c408e18470b9fd86b3d6a0220684ac14228c4adaa9df819e7fc8e82cf3c4242b74e27f5dd190d63231e8a058a012102990a280aef14e545b9b076b6548a4e886476d967e447bb69efcf0b725efda04effffffff..............................</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>2 番目の例からファイルを削除しましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!rm HEX.txt
!rm RawTX.txt
!rm NoncesHEX.txt
!rm PrivateKey.txt
!rm SignatureRSZ.csv
!rm PrivateKeyAddr.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3219} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-231.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3219"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><code>HEX</code><em>ユーティリティを通じてデータを&nbsp;</em><em>ダウンロードし&nbsp;</em><code>wget</code><em>&nbsp;、ファイル&nbsp;</em><strong>RawTX.txtに保存します。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://raw.githubusercontent.com/demining/CryptoDeepTools/main/21LatticeAttack/example3/HEX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3221} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-232-1024x418.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3221"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>コードを実行して必要な部分を取得しましょう&nbsp;</em><code><strong>RawTX</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>with open("HEX.txt") as myfile:

    listfile="\n".join(f'{line.rstrip()&#91;:+298]}' for line in myfile)


f = open("RawTX.txt", 'w')
f.write("" + listfile + "" + "\n")
f.close()</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3225} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-233.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3225"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><code>-tool lattice_attack</code>&nbsp;ソフトウェアを使用して&nbsp;起動する&nbsp;<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -tool lattice_attack -open RawTX.txt -save SignatureRSZ.csv</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3226} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-234.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3226"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この攻撃は次から開始され&nbsp;<code>-tool lattice_attack</code>&nbsp;、結果はファイルに保存されました。&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>成功した結果を確認するには、ファイルを開いてください。&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3227} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-235.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3227"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><em>&nbsp;コマンド</em><em>を実行しましょう&nbsp;:</em><code>SageMath</code><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3228} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-236-1024x451.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3228"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>&nbsp;ビットコイン ウォレットの秘密キーを計算するには、パラメータを指定して&nbsp;スクリプト クラック&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/crack_weak_ECDSA_nonces_with_LLL.py" target="_blank" rel="noreferrer noopener">_weak_ECDSA_nonces_with_LLL.pyを実行します。</a></strong><strong><code>249 bits 79 sign</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 crack_weak_ECDSA_nonces_with_LLL.py SignatureRSZ.csv 249 79 &gt; PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3231} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-237.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3231"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを開いてみましょう:&nbsp;<code>PrivateKey.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>ビットコインウォレットへの秘密鍵を次の&nbsp;<code>HEX</code>&nbsp;形式で受け取りました。</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3234} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-238.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3234"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>PrivKey = 0x80e3052532356bc701189818c095fb8a7f035fd7a5a96777df4162205e945aa5</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">各 ECDSA 署名の POLYNONCE を確認する</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example3/POLYNONCE.py" target="_blank" rel="noreferrer noopener">これを行うには、 GITHUB</a></strong>のコードを使用します。<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example3/POLYNONCE.py" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3235,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-239.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3235"/><figcaption class="wp-element-caption"><code><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example3/POLYNONCE.py" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example3/POLYNONCE.py</a></code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">結果：</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3236} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-240.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3236"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>から 79 個の同一のオリジナル ビットを取得しました。</em><code>249</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist)" target="_blank" rel="noreferrer noopener">Hal Finney</a>&nbsp;&nbsp;の secp256k1 曲線の値のおかげで&nbsp;、&nbsp;<a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener">LAMBDA と BETA は</a>&nbsp;同じ初期ビットを明らかにしました。<code>POLYNONCE</code>この形式の値により、<code>HEX</code>隠された数字の問題を完全に解決し、秘密鍵を取得し、ビットコイン ウォレットを復元することができます。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">秘密キーの 16 進数を確認してみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>コードを実行してみましょう:</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from bitcoin import *

with open("PrivateKey.txt","r") as f:
    content = f.readlines()

content = &#91;x.strip() for x in content]
f.close()


outfile = open("PrivateKeyAddr.txt","w")
for x in content:
  outfile.write(x+":"+pubtoaddr(encode_pubkey(privtopub(x), "bin_compressed"))+"\n")
 
outfile.close()</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2848} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-103-1024x451.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-2848"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを開いてみましょう:&nbsp;<code>PrivateKeyAddr.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3237} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-241.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3237"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a></strong>を開いて確認してみましょう&nbsp;&nbsp;:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 18Y9nUpdtxAKTh6yaN299jfUxcpJ2ApHz
WIF:  L1YFTAP2X6jhi9W6ZVy2xX8H89TYwZcgSKcPLX7NmAx3n8PjqDkU
HEX:  80e3052532356bc701189818c095fb8a7f035fd7a5a96777df4162205e945aa5</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3242} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-bitaddress-7.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3242"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/18Y9nUpdtxAKTh6yaN299jfUxcpJ2ApHz"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/18Y9nUpdtxAKTh6yaN299jfUxcpJ2ApHz
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3246} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-243.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3246"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3247} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-244.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3247"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3248} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-245-1024x146.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3248"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 1023.25</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><code>№4</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ビットコイン アドレスを使用した例 4 を考えてみましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12fqNTJc1wj2xfNscYHAzehD6f6sRjWBor" target="_blank" rel="noreferrer noopener">12fqNTJc1wj2xfNscYHAzehD6f6sRjWBor</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3253} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-246.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3253"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/tx/6e6d84bc92cd79fba2d1eee5fb47e393896d44f666a50d4948a022751e3f0989" target="_blank" rel="noreferrer noopener"><strong>6e6d84bc92cd79fba2d1eee5fb47e393896d44f666a50d4948a022751e3f0989</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3254} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-247.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3254"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">RawTX</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3255} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-248-1024x371.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3255"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>"hex": 01000000418ff67c7d3309211ab9d9629d97bbac7730d3cbb419df4ec43d2c5fc4f81bbefb1b0000006b4830450221008c223861acf1f265547eddb04a7cf98d206643a05824e56e97c70beddd18eaf20220139a34bf077a1fdb15e716d765955203e746616dfe8bf536b86d259b5c8a09b8012103c50b5619a40a23ff6a5510238405b8efd3f8f1bc442e1a415b25078b4cbd88e3ffffffff..............................</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>2 番目の例からファイルを削除しましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!rm HEX.txt
!rm RawTX.txt
!rm NoncesHEX.txt
!rm PrivateKey.txt
!rm SignatureRSZ.csv
!rm PrivateKeyAddr.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3258} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-249.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3258"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><code>HEX</code><em>ユーティリティを通じてデータを&nbsp;</em><em>ダウンロードし&nbsp;</em><code>echo</code><em>&nbsp;、ファイルに保存します:&nbsp;&nbsp;</em><strong>RawTX.txt</strong><em>ユーティリティを通じてデータを&nbsp;</em><em>ダウンロードし&nbsp;</em><em>&nbsp;、ファイルに保存します:&nbsp;&nbsp;</em><strong>RawTX.txt</strong><code>HEX</code><em></em><code>wget</code><em></em><strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://raw.githubusercontent.com/demining/CryptoDeepTools/main/21LatticeAttack/example4/HEX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3260} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-250.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3260"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>コードを実行して必要な部分を取得しましょう&nbsp;</em><code><strong>RawTX</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>with open("HEX.txt") as myfile:

    listfile="\n".join(f'{line.rstrip()&#91;:+298]}' for line in myfile)


f = open("RawTX.txt", 'w')
f.write("" + listfile + "" + "\n")
f.close()</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3262} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-251.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3262"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><code>-tool lattice_attack</code>&nbsp;ソフトウェアを使用して&nbsp;起動する&nbsp;<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -tool lattice_attack -open RawTX.txt -save SignatureRSZ.csv</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3263} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-252-1024x451.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3263"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この攻撃は次から開始され&nbsp;<code>-tool lattice_attack</code>&nbsp;、結果はファイルに保存されました。&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>成功した結果を確認するには、ファイルを開いてください。&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3265} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-253-1024x444.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3265"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><em>&nbsp;コマンド</em><em>を実行しましょう&nbsp;:</em><code>SageMath</code><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3267} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-254.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3267"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>&nbsp;ビットコイン ウォレットの秘密キーを計算するには、パラメータを指定して&nbsp;スクリプト クラック&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/crack_weak_ECDSA_nonces_with_LLL.py" target="_blank" rel="noreferrer noopener">_weak_ECDSA_nonces_with_LLL.pyを実行します。</a></strong><strong><code>249 bits 79 sign</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 crack_weak_ECDSA_nonces_with_LLL.py SignatureRSZ.csv 249 79 &gt; PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3268} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-255-1024x531.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3268"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを開いてみましょう:&nbsp;<code>PrivateKey.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>ビットコインウォレットへの秘密鍵を次の&nbsp;<code>HEX</code>&nbsp;形式で受け取りました。</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3269} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-256.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3269"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>PrivKey = 0x9e636a4ef1a63c4bd385b8d26d29f6394a29963f12109dbf34fef74377866a32</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">各 ECDSA 署名の POLYNONCE を確認する</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example4/POLYNONCE.py" target="_blank" rel="noreferrer noopener">これを行うには、 GITHUB</a></strong>のコードを使用します。<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example4/POLYNONCE.py" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3272,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-257.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3272"/><figcaption class="wp-element-caption"><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example4/POLYNONCE.py" target="_blank" rel="noreferrer noopener"><code>https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example4/POLYNONCE.py</code></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">結果：</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3278} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-258.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3278"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>から 79 個の同一のオリジナル ビットを取得しました。</em><code>249</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist)" target="_blank" rel="noreferrer noopener">Hal Finney</a>&nbsp;&nbsp;の secp256k1 曲線の値のおかげで&nbsp;、&nbsp;<a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener">LAMBDA と BETA は</a>&nbsp;同じ初期ビットを明らかにしました。<code>POLYNONCE</code>この形式の値により、<code>HEX</code>隠された数字の問題を完全に解決し、秘密鍵を取得し、ビットコイン ウォレットを復元することができます。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">秘密キーの 16 進数を確認してみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>コードを実行してみましょう:</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from bitcoin import *

with open("PrivateKey.txt","r") as f:
    content = f.readlines()

content = &#91;x.strip() for x in content]
f.close()


outfile = open("PrivateKeyAddr.txt","w")
for x in content:
  outfile.write(x+":"+pubtoaddr(encode_pubkey(privtopub(x), "bin_compressed"))+"\n")
 
outfile.close()</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3281} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-259-1024x385.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3281"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを開いてみましょう:&nbsp;<code>PrivateKeyAddr.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3283} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-260.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3283"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a></strong>を開いて確認してみましょう&nbsp;&nbsp;:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 12fqNTJc1wj2xfNscYHAzehD6f6sRjWBor
WIF:  L2Xbaxg8QFoLn5URp7GKMyLwEN9dV5TtgpdbXYo7WDJsHZLcT898
HEX:  9e636a4ef1a63c4bd385b8d26d29f6394a29963f12109dbf34fef74377866a32</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3286} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-bitaddress-8.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3286"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/12fqNTJc1wj2xfNscYHAzehD6f6sRjWBor"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/12fqNTJc1wj2xfNscYHAzehD6f6sRjWBor
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3290} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-262.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3290"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3291} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-263.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3291"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3292} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-264-1024x141.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3292"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 406.03</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><strong><code>№5</code></strong></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ビットコイン アドレスを使用した例 5 を考えてみましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1L8v5aUZRzYbGKWcj9Yt6mGdd95Sy9bXjN" target="_blank" rel="noreferrer noopener">1L8v5aUZRzYbGKWcj9Yt6mGdd95Sy9bXjN</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3297} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-265.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3297"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/tx/8a00ad0cc10d768d6d2b407f99879e556e5fc2917b619cb9a551675b7682a791" target="_blank" rel="noreferrer noopener"><strong>8a00ad0cc10d768d6d2b407f99879e556e5fc2917b619cb9a551675b7682a791</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3298} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-266.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3298"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">RawTX</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3300} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-267-1024x378.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3300"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>
"hex": "01000000fdf4014f7e4a72ecb9a3ed21a82a42b3127da87bdfee7c10779688dd8a38977cb80ece000000006a4730440220423f7cffadd494fb0148d509e67598b3c8d7f54695ee3830184adc2af234d5cf022005ebe83773bc81c7131fd0580350a998adde20fee6fd2d1da40a0191fea8242c0121027a2250a80a31965e928afff97d1c713e7ce70e6eb7c7491404a79991bfc6b5c1ffffffff...........................</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>2 番目の例からファイルを削除しましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!rm HEX.txt
!rm RawTX.txt
!rm NoncesHEX.txt
!rm PrivateKey.txt
!rm SignatureRSZ.csv
!rm PrivateKeyAddr.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3302} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-268.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3302"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><code>HEX</code><em>ユーティリティを通じてデータを&nbsp;</em><em>ダウンロードし&nbsp;</em><code>wget</code><em>&nbsp;、ファイル&nbsp;</em><strong>RawTX.txtに保存します。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://raw.githubusercontent.com/demining/CryptoDeepTools/main/21LatticeAttack/example5/HEX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3304} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-269-1024x461.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3304"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>コードを実行して必要な部分を取得しましょう&nbsp;</em><code><strong>RawTX</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>with open("HEX.txt") as myfile:

    listfile="\n".join(f'{line.rstrip()&#91;:+298]}' for line in myfile)


f = open("RawTX.txt", 'w')
f.write("" + listfile + "" + "\n")
f.close()</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3308} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-270-1024x511.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3308"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><code>-tool lattice_attack</code>&nbsp;ソフトウェアを使用して&nbsp;起動する&nbsp;<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -tool lattice_attack -open RawTX.txt -save SignatureRSZ.csv</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3309} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-271-1024x446.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3309"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この攻撃は次から開始され&nbsp;<code>-tool lattice_attack</code>&nbsp;、結果はファイルに保存されました。&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>成功した結果を確認するには、ファイルを開いてください。&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3310} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-272.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3310"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><em>&nbsp;コマンド</em><em>を実行しましょう&nbsp;:</em><code>SageMath</code><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3311} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-273-1024x495.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3311"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>&nbsp;ビットコイン ウォレットの秘密キーを計算するには、パラメータを指定して&nbsp;スクリプト クラック&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/crack_weak_ECDSA_nonces_with_LLL.py" target="_blank" rel="noreferrer noopener">_weak_ECDSA_nonces_with_LLL.pyを実行します。</a></strong><strong><code>249 bits 79 sign</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 crack_weak_ECDSA_nonces_with_LLL.py SignatureRSZ.csv 249 79 &gt; PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3312} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-274.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3312"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを開いてみましょう:&nbsp;<code>PrivateKey.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>ビットコインウォレットへの秘密鍵を次の&nbsp;<code>HEX</code>&nbsp;形式で受け取りました。</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":3314} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-275.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3314"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>PrivKey = 0xe2eadbde2e6a2adb6f81864cdf574dd44959717fe095486e2c0e55585594edf2</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">各 ECDSA 署名の POLYNONCE を確認する</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example5/POLYNONCE.py" target="_blank" rel="noreferrer noopener">これを行うには、 GITHUB</a></strong>のコードを使用します。<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example5/POLYNONCE.py" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3318,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-276.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3318"/><figcaption class="wp-element-caption"><code><a href="https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example5/POLYNONCE.py" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/blob/main/21LatticeAttack/example5/POLYNONCE.py</a></code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">結果：</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3319} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-277.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3319"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>から 79 個の同一のオリジナル ビットを取得しました。<code>249</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist)" target="_blank" rel="noreferrer noopener">Hal Finney</a>&nbsp;&nbsp;の secp256k1 曲線の値のおかげで&nbsp;、&nbsp;<a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener">LAMBDA と BETA は</a>&nbsp;同じ初期ビットを明らかにしました。<code>POLYNONCE</code>この形式の値により、<code>HEX</code>隠された数字の問題を完全に解決し、秘密鍵を取得し、ビットコイン ウォレットを復元することができます。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">秘密キーの 16 進数を確認してみましょう。</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>コードを実行してみましょう:</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from bitcoin import *

with open("PrivateKey.txt","r") as f:
    content = f.readlines()

content = &#91;x.strip() for x in content]
f.close()


outfile = open("PrivateKeyAddr.txt","w")
for x in content:
  outfile.write(x+":"+pubtoaddr(encode_pubkey(privtopub(x), "bin_compressed"))+"\n")
 
outfile.close()</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3321} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-278.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3321"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを開いてみましょう:&nbsp;<code>PrivateKeyAddr.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":3323} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-279-1024x700.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3323"/><figcaption class="wp-element-caption"><code>e2eadbde2e6a2adb6f81864cdf574dd44959717fe095486e2c0e55585594edf2:1L8v5aUZRzYbGKWcj9Yt6mGdd95Sy9bXjN</code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">ビットアドレス</a></strong>を開いて確認してみましょう&nbsp;&nbsp;:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1L8v5aUZRzYbGKWcj9Yt6mGdd95Sy9bXjN
WIF:  L4porgUmuBkMbATA6Pp7r8uqShFt2zTPNEfuPNYi1BCym4hhV8gs
HEX:  e2eadbde2e6a2adb6f81864cdf574dd44959717fe095486e2c0e55585594edf2</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3332} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-bitaddress-9.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3332"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/1L8v5aUZRzYbGKWcj9Yt6mGdd95Sy9bXjN"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/1L8v5aUZRzYbGKWcj9Yt6mGdd95Sy9bXjN
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3337} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-281.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3337"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3340} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-282.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3340"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3342} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-283.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3342"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 995.39</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">文学：</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em><a href="https://cryptodeep.ru/doc/Lattice-Attacks-against-Elliptic-Curve-Signatures-with-Blinded-Scalar-Multiplication.pdf" target="_blank" rel="noreferrer noopener">ブラインド スカラー乗算による楕円曲線署名に対する格子攻撃 Dahmun Goudarzi、Matthieu Rivain、Damien Vergnaud CryptoExperts、パリ、フランス</a></em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em><a href="https://cryptodeep.ru/doc/Biased-Nonce-Sense-Lattice-Attacks-against-Weak-ECDSA-Signatures-in-Cryptocurrencies.pdf" target="_blank" rel="noreferrer noopener">バイアスされたナンスセンス: 暗号通貨の弱い ECDSA 署名に対する格子攻撃 Joachim Breitner および Nadia Heninger DFINITY Foundation、Zug University of California、サンディエゴ</a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><a href="https://cryptodeep.ru/doc/Return-of-the-Hidden-Number-ProblemA-Widespread-and-Novel-Key-Extraction-Attack-on-ECDSA-and-DSA.pdf" target="_blank" rel="noreferrer noopener">隠された番号問題の復活 ECDSA および DSA に対する広範かつ斬新なキー抽出攻撃 Keegan Ryan</a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><a href="https://cryptodeep.ru/doc/The-curse-of-ECDSA-nonces-Systematic-analysis-of-lattice-attacks-on-noisy-leakage-of-bit-length-of-ECDSA-nonces.pdf" target="_blank" rel="noreferrer noopener">Minerva: ECDSA nonces の呪い ECDSA nonce のビット長のノイズリークに対する格子攻撃の体系的分析 Ján Jančár、Vladimír Sedláček、Petr Švenda、Marek Sýs マサリク大学、ヴェネツィア・カフォスカリ大学</a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><a href="https://cryptodeep.ru/doc/Estimating-the-Effectiveness-of-Lattice-Attacks.pdf" target="_blank" rel="noreferrer noopener">ラティス攻撃の有効性の推定 阿部 耕太郎、池田 誠 東京大学工学系研究科、東京、日本</a></em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/21LatticeAttack" target="_blank" rel="noreferrer noopener">ソース</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://attacksafe.ru/software" target="_blank" rel="noreferrer noopener">攻撃安全なソフトウェア</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/CzaHitewN-4" target="_blank" rel="noreferrer noopener">ビデオ: https://youtu.be/CzaHitewN-4</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/lattice-attack-249bits" target="_blank" rel="noreferrer noopener">出典: https://cryptodeep.ru/lattice-攻撃-249bits</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3344} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/039-1024x576.png" alt="LATTICE ATTACK 249 ビットは 79 個の署名 ECDSA を使用して隠れた数の問題を解決します" class="wp-image-3344"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解析</a></p>
<!-- /wp:paragraph -->
