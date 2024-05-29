# Google Colab に SageMath をインストールする

<!-- wp:embed {"url":"https://www.youtube.com/embed/DBu0UnVe0ig","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/DBu0UnVe0ig
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>この記事では、 に新規インストールを実行し<code>SageMath</code>ます<code>Google Colab</code>。<strong><a href="https://cryptodeeptech.ru/install-sagemath-on-fedora/" target="_blank" rel="noreferrer noopener">以前に「 Fedora 64 ビット (10GB) クラウド仮想サーバーに暗号解析用に SageMath をインストールする</a></strong>」という記事を公開しましたが、ビットコイン ブロックチェーンの暗号解析を続けるために、読者の多くは、 とは<code>Debian</code>対照<code>Ubuntu</code>的に と を使用することを好みます<code>Fedora</code>。私たちが知る限りでは、<code>Google Colab</code>に更新されています<code>"Ubuntu 20.04.5 LTS"</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>これは、次のコマンドを実行して確認できます。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!cat /etc/lsb-release
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2598} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-21-1024x192.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2598"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>したがって<code>"Ubuntu 20.04.5 LTS"</code>、このバージョンではインストールのみが可能です<code>SageMath version 9.0, Release Date: 2020-01-01</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>標準のインストール コマンドを使用します。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!sudo apt-get install -y sagemath-common</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2599} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-22-1024x120.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2599"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>残念ながら、このバージョンは正しく動作しません。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><code>Google Colab</code>完全な暗号解析を行うには、完全に新しいバージョンをインストールします。<code>SageMath version 9.3</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ファイル:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/19SageMathGoogleColab/Install_SageMath_in_Google_Colab.ipynb" target="_blank" rel="noreferrer noopener"><strong>Install_SageMath_in_Google_Colab.ipynb</strong></a>&nbsp;で公開しました<code>GitHub</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>公式ウェブサイトにアクセスしましょう:&nbsp;<strong><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">https://colab.research.google.com</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>「メモ帳をダウンロード」</strong>オプションを選択します<strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2605} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-24.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2605"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルをダウンロードします:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/19SageMathGoogleColab/Install_SageMath_in_Google_Colab.ipynb" target="_blank" rel="noreferrer noopener"><strong>Install_SageMath_in_Google_Colab.ipynb</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2606} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-25.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2606"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>次に、ユーティリティを通じて、<a href="https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2" target="_blank" rel="noreferrer noopener"><strong>sage-9.3-Ubuntu_20.04-x86_64.tar.bz2</strong></a>を<code>wget</code>&nbsp;ダウンロードします。<code>tar-file</code><a href="https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2
!tar -xf sage-9.3-Ubuntu_20.04-x86_64.tar.bz2</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2612} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-29-1024x321.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2612"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ディレクトリを見てみましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd SageMath/</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2617} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-32-1024x110.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2617"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>パネルを開いてフォルダーに移動します。<code>SageMath</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2619} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-34.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2619"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>relocate-once.py</strong>があるかどうかを確認する<code>Python-script:</code><strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2618} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-33-1024x180.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2618"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>次のコマンドを使用して<code>Python-script:</code><strong>relocate-once.py</strong>を実行します。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!python3 relocate-once.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2620} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-35-1024x451.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2620"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>すべて準備完了です！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>SageMath</code>次に、コマンドを実行してみましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2623} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-36-1024x304.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2623"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>バージョンチェックコマンドを実行してみましょう。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sage -v</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2624} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-37-1024x344.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2624"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>わかった！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>新しいバージョンができました:&nbsp;<code>SageMath version 9.3, Release Date: 2021-05-09</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/twist-attack/" target="_blank" rel="noreferrer noopener">Twist Attack</a>アルゴリズムの実装、 &nbsp;&nbsp;<code>Python-script:</code><a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener">discrete.pyのダウンロード</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>wget https://raw.githubusercontent.com/demining/CryptoDeepTools/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2628} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-41-1024x517.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2628"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>離散対数を解くには、&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener">discrete.py</a><em><code>(Pollard's rho algorithm for logarithms)</code></em>&nbsp;を実行します。&nbsp;<code>Python-script:</code><a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>秘密キーを取得するには、次のコマンドを実行するだけです。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 discrete.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2654} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-43-1024x548.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2654"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>Sage Math&nbsp;</strong><strong>9.3</strong>は&nbsp;離散対数問題を解決します&nbsp;<em><code>(Pollard's rho algorithm for logarithms)</code></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><br>これで、すべてが正しく動作するようになりました。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://cryptodeeptech.ru/twist-attack/" target="_blank" rel="noreferrer noopener">ビットコイン ウォレットの秘密キーを 10 進数形式で受け取りました。その後、暗号解析を行うには、 Twist Attack</a></strong>に特化した記事の指示に従う必要があります。&nbsp;<strong><a href="https://cryptodeeptech.ru/twist-attack/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/Install-SageMath-in-Google-Colab" target="_blank" rel="noreferrer noopener">ソース</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/DBu0UnVe0ig" target="_blank" rel="noreferrer noopener">ビデオ: https://youtu.be/DBu0UnVe0ig</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/install-sagemath-in-google-colab" target="_blank" rel="noreferrer noopener">出典: https://cryptodeep.ru/install-sagemath-in-google-colab</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2669} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/037-1-1024x576.png" alt="Google Colab に SageMath をインストールする" class="wp-image-2669"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解析</a></p>
<!-- /wp:paragraph -->
