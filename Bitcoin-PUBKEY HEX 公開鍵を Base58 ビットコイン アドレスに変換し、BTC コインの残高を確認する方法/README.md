# Bitcoin-PUBKEY HEX 公開鍵を Base58 ビットコイン アドレスに変換し、BTC コインの残高を確認する方法

<!-- wp:embed {"url":"https://www.youtube.com/embed/Hsk6QIzb7oY","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Hsk6QIzb7oY
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py">この記事では、 bitcoin-checker.py&nbsp;</a><em>Python スクリプト</em>&nbsp;を使用して、大量のデータでビットコインの残高を確認する方法を学習します&nbsp;。<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py"></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/115/c50/ab8/115c50ab8b21651ae63d3cd8d3ecb98d.png" alt="Pythonスクリプトbitcoin-checker.pyをチェックした結果" title="Pythonスクリプトbitcoin-checker.pyをチェックした結果"/><figcaption class="wp-element-caption">Pythonスクリプトbitcoin-checker.pyをチェックした結果</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><br><code>PUBKEY (HEX)</code>&nbsp;また、ビットコインの公開鍵をビットコイン アドレスに&nbsp;変換する方法も学習します。&nbsp;<code>(Base58)</code>&nbsp;この大きな作業はすべて、&nbsp;&nbsp;<em>Python スクリプト</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/pubtoaddr.py" target="_blank" rel="noreferrer noopener">pubtoaddr.pyによって行われます。</a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">その結果、Google Colab ターミナル[TerminalGoogleColab]</a>でブロックチェーンをスキャンすることで、特に簡単にビットコインの残高を確認できます。&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以前にビデオ チュートリアルを録画しました&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener">。</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/03CheckBitcoinAddressBalance" target="_blank" rel="noreferrer noopener">「CryptoDeepTools」</a>リポジトリに移動して&nbsp;、&nbsp;<em>Bash スクリプトが</em>&nbsp;どのように機能するかを詳しく見てみましょう&nbsp;:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/getbalance.sh" target="_blank" rel="noreferrer noopener">getbalance.sh</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>コマンド:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/03CheckBitcoinAddressBalance/

sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip3 install -r requirements.txt

chmod +x getbalance.sh

./getbalance.sh
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d45/57e/1ae/d4557e1ae1a44f4c54e688da3a4882c7.png" alt="ファイル" title="ファイル"/><figcaption class="wp-element-caption">ファイル</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4ff/051/a09/4ff051a0999975eca9beb0b3f349896f.png" alt="Bash スクリプト コード: getbalance.sh" title="Bash スクリプト コード: getbalance.sh"/><figcaption class="wp-element-caption">Bash スクリプト コード: getbalance.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>grep 'PUBKEY = ' signatures.json &gt; pubkeyall.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>このユーティリティは、&nbsp;<code>grep</code>&nbsp;すべての公開鍵を 1 つの共通ファイルに収集します。&nbsp;<code>pubkeyall.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sort -u pubkeyall.json &gt; pubkey.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>このユーティリティは&nbsp;<code>sort</code>&nbsp;、重複を並べ替えて削除し、一意の公開鍵を選択して、結果をファイルに保存します。&nbsp;<code>pubkey.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>rm pubkeyall.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ユーティリティは&nbsp;<code>rm</code>&nbsp;削除します&nbsp;<code>pubkeyall.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sed -i 's/PUBKEY = //g' pubkey.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>ユーティリティは&nbsp;<code>sed</code>&nbsp;プレフィックスを消去します&nbsp;<code>PUBKEY =</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 pubtoaddr.py</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>Python スクリプト</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/pubtoaddr.py" target="_blank" rel="noreferrer noopener">pubtoaddr.py</a>を実行し&nbsp;、<code>pubkey.json</code>&nbsp;ビットコインの公開鍵が保存されている&nbsp;ファイルから<code>PUBKEY (HEX)</code>&nbsp;ファイル&nbsp;&nbsp;に変換します。&nbsp;<code>addresses.json</code>&nbsp;結果はビットコイン アドレスとして保存されます。&nbsp;<code>(Base58)</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>import</strong> hashlib
<strong>import</strong> base58
 
<strong>def</strong> <strong>hash160</strong>(hex_str):
    sha = hashlib.sha256()
    rip = hashlib.new('ripemd160')
    sha.update(hex_str)
    rip.update(sha.digest())
    <strong>return</strong> rip.hexdigest()  # .hexdigest() is hex ASCII
 
 
pub_keys = open('pubkey.json', 'r', encoding='utf-8')
new_file = open('addresses.json', 'a', encoding='utf-8')
compress_pubkey = False
 
<strong>for</strong> pub_key <strong>in</strong> pub_keys:
    pub_key = pub_key.replace('\n', '')
    <strong>if</strong> compress_pubkey:
        <strong>if</strong> (ord(bytearray.fromhex(pub_key&#91;-2:])) % 2 == 0):
            pubkey_compressed = '02'
        <strong>else</strong>:
            pubkey_compressed = '03'
        pubkey_compressed += pub_key&#91;2:66]
        hex_str = bytearray.fromhex(pubkey_compressed)
    <strong>else</strong>:
        hex_str = bytearray.fromhex(pub_key)
 
 
    key_hash = '00' + hash160(hex_str)
 
 
    sha = hashlib.sha256()
    sha.update(bytearray.fromhex(key_hash))
    checksum = sha.digest()
    sha = hashlib.sha256()
    sha.update(checksum)
    checksum = sha.hexdigest()&#91;0:8]
 
#   new_file.write("" + (base58.b58encode(bytes(bytearray.fromhex(key_hash + checksum)))).decode('utf-8'))
    new_file.write((base58.b58encode(bytes(bytearray.fromhex(key_hash + checksum)))).decode('utf-8') + "\n")
pub_keys.close()
new_file.close()</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>ファイルを受け取りました&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py" target="_blank" rel="noreferrer noopener">。bitcoin-checker.py&nbsp;</a><em>Python スクリプト</em><code>addresses.json</code>&nbsp;を&nbsp;使用してビットコインの残高を確認します。<em></em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>Python スクリプト</em>を実行します&nbsp;。&nbsp;<code>python2 bitcoin-checker.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>import</strong> sys
<strong>import</strong> re
<strong>from</strong> time <strong>import</strong> sleep

<strong>try</strong>:    # if is python3
    <strong>from</strong> urllib.request <strong>import</strong> urlopen
<strong>except</strong>: # if is python2
    <strong>from</strong> urllib2 <strong>import</strong> urlopen


<strong>def</strong> <strong>check_balance</strong>(address):

    #Modify the value of the variable below to False if you do not want Bell Sound when the Software finds balance.
    SONG_BELL = True

    #Add time different of 0 if you need more security on the checks
    WARN_WAIT_TIME = 0

    blockchain_tags_json = &#91; 
        'total_received',
        'final_balance',
        ]

    SATOSHIS_PER_BTC = 1e+8

    check_address = address

    parse_address_structure = re.match(r' *(&#91;a-zA-Z1-9]{1,34})', check_address)
    <strong>if</strong> ( parse_address_structure <strong>is</strong> <strong>not</strong> None ):
        check_address = parse_address_structure.group(1)
    <strong>else</strong>:
        print( "\nThis Bitcoin Address is invalid" + check_address )
        exit(1)

    #Read info from Blockchain about the Address
    reading_state=1
    <strong>while</strong> (reading_state):
        <strong>try</strong>:
            htmlfile = urlopen("https://blockchain.info/address/%s?format=json" % check_address, timeout = 10)
            htmltext = htmlfile.read().decode('utf-8')
            reading_state  = 0
        <strong>except</strong>:
            reading_state+=1
            print( "Checking... " + str(reading_state) )
            sleep(60*reading_state)

    print( "\nBitcoin Address = " + check_address )

    blockchain_info_array = &#91;]
    tag = ''
    <strong>try</strong>:
        <strong>for</strong> tag <strong>in</strong> blockchain_tags_json:
            blockchain_info_array.append (
                float( re.search( r'%s":(\d+),' % tag, htmltext ).group(1) ) )
    <strong>except</strong>:
        print( "Error '%s'." % tag );
        exit(1)

    <strong>for</strong> i, btc_tokens <strong>in</strong> enumerate(blockchain_info_array):

        sys.stdout.write ("%s \t= " % blockchain_tags_json&#91;i])
        <strong>if</strong> btc_tokens &gt; 0.0:
            print( "%.8f Bitcoin" % (btc_tokens/SATOSHIS_PER_BTC) );
        <strong>else</strong>:
            print( "0 Bitcoin" );

        <strong>if</strong> (SONG_BELL <strong>and</strong> blockchain_tags_json&#91;i] == 'final_balance' <strong>and</strong> btc_tokens &gt; 0.0): 
            
            #If you have a balance greater than 0 you will hear the bell
            sys.stdout.write ('\a\a\a')
            sys.stdout.flush()

            arq1.write("Bitcoin Address: %s" % check_address)
            arq1.write("\t Balance: %.8f Bitcoin" % (btc_tokens/SATOSHIS_PER_BTC))
            arq1.write("\n")
            arq1.close()
            <strong>if</strong> (WARN_WAIT_TIME &gt; 0):
                sleep(WARN_WAIT_TIME)

#Add the filename of your list of Bitcoin Addresses for check all.
<strong>with</strong> open("addresses.json") <strong>as</strong> file:
    <strong>for</strong> line <strong>in</strong> file:

    	arq1 = open('balance.json', 'a')
        address = str.strip(line)
        <strong>print</strong> ("__________________________________________________\n")
        
        check_balance(address)
<strong>print</strong> "__________________________________________________\n"
arq1.close()</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>その結果、結果はファイルに保存されます。&nbsp;<code>balance.json</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/93a/f82/c34/93af82c3468566ef9f495d0732c9731c.png" alt="ファイル: balance.json" title="ファイル: balance.json"/><figcaption class="wp-element-caption">ファイル: balance.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>これで、次のことがわかりました。</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>PUBKEY (HEX)</code>&nbsp;ビットコイン公開鍵をビットコインアドレスに&nbsp;変換&nbsp;<code>(Base58)</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ビットコイン コインのすべてのビットコイン アドレス (Base58) を確認する</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>これを暗号解読に応用</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>ソースコード:&nbsp;&nbsp;</strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/03CheckBitcoinAddressBalance" target="_blank" rel="noreferrer noopener"><strong>https://github.com/demining/CryptoDeepTools/tree/main/03CheckBitcoinAddressBalance</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>テレグラム:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong>https://t.me/cryptodeeeptech</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>動画素材：&nbsp;&nbsp;</strong><a href="https://youtu.be/Hsk6QIzb7oY" target="_blank" rel="noreferrer noopener"><strong>https://youtu.be/Hsk6QIzb7oY</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/Hsk6QIzb7oY","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Hsk6QIzb7oY
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">暗号解読</a></p>
<!-- /wp:paragraph -->
