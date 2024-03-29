# RaiseTech memo

## EC2の初期設定

    ・アップデート
        sudo yum -y update

    ・環境構築に必要なパッケージをインストール
        sudo yum  -y install git make gcc-c++ patch libyaml-devel libffi-devel libicu-devel zlib-devel readline-devel libxml2-devel libxslt-devel ImageMagick ImageMagick-devel openssl-devel libcurl libcurl-devel curl

    「-yオプション」とは、yumコマンドのオプションで、「すべての問いにYesで自動的に答える」



## rbenv

    ・rbenvとはRubyのバージョンを簡単に切り替えてくれるツール。
    
        1.初期化設定
            $ echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
    
        2.初期化設定の反映
            $ source ~/.bash_profile
    
        3.rbenvのインストール：
            $ brew install rbenv ruby-build
    
        4.インストール可能なRubyのバージョン一覧の表示
            $ rbenv install -l
    
        5.指定したRubyのバージョンをインストール
            $ rbenv install 2.3.5
    
        6.インストールしたRubyを使用可能な状態にする⇒shimsへの反映
            $ rbenv rehash

    ※複数のバージョンのRubyをインストールしたい場合は、4.⇒5.⇒6.を繰り返す。

### memo・別・その他？

    ・rbenvのインストール
        git clone https://github.com/sstephenson/rbenv.git ~/.rbenv

    ・ruby-buildのインストール
        git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build

    ・rbenvが利用できるようにbashの設定ファイルを編集。

        echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
        echo 'eval "$(rbenv init -)"' >> ~/.bash_profile

    ・rbenvが使用できるか確認しつつ、インストールできるRubyのバージョンを確認。
        rbenv install -l

    ・ruby3.1.2をインストール
        rbenv install 3.1.2
            または
        rbenv install 3.1.2 -v
        （-v オプションは、インストールプロセスの詳細を表示）

    ・使用するRubyバージョンの設定
        rbenv global 3.1.2

        rbenv uninstall 2.0.0

        rbenv uninstall --all



## rails

    ・which rails

    ・rails -v
        railsのバージョンを確認

    ・gem install rails -v 7.0.4
        railsのバージョンを7.0.4を指定してインストール



## volta

### Voltaとは何か？

    VoltaはJavaScriptのランタイムバージョン管理ツール。
    Node.jsやNpm、Yarnなどのバージョンを簡単に切り替えることができる。また、プロジェクトごとに使用するバージョンを固定する機能もあり、異なるバージョンでの動作に悩むことがなくなる。
    特に、複数のプロジェクトを同時に扱う開発者にとって、Voltaは非常に便利なツールと言える。

### Node.jsとYarnのセットアップ
    Voltaを使うと、Node.jsとYarnのセットアップもとても簡単に行うことができる。


    ・voltaのインストール（mac・Linux）
        curl https://get.volta.sh | bash

    ＊インストール後は新しいターミナルを開く必要がある

    ・voltaでNode.jsのv17.9.1をインストール
        volta install node@17.9.1

    ・指定したバージョンの安定版をインストール
        volta install node@17

    ・最新版をインストール
        volta install node@latest

    ・バージョンを確認
        node --version

    ・Node.jsのインストールを完了すると自動でnpmもインストールされている(npmの確認コマンド)
        npm -v

    ・Volta経由でインストールされているツールを全て確認
        volta list all

    ・Node.jsのバージョンの変更もインストール方法と同じコマンドで変更できる
        volta install node

    ・yarnのインストール
        volta install yarn@1.22.19



    参照サイト（https://coding-note.com/volta/）

### Pryとは
    PryはRubyに標準でついているIRB(Interactive Ruby)をより便利なものにしたもの
        gem install pry

    参照元（https://tagamidaiki.com/ruby-debugging-gem-pry/）



## Bundler

### バージョンの確認
        
        $ ruby -v
        $ gem -v
        $ bundle -v
    （rubyをインストールするとgemがインストールされる。gemがインストールインストールされるとbundlerがインストールされる。bundlerはgemによってインストールされる。）


    インストール済みのbundlerバージョン一覧
        $ gem list bundler

    出力結果
        例1: bundler (default: 2.3.17)
	        -> 2.3.17がデフォルト

        例2: bundler (default: 2.3.17, default: 2.2.22)
	        -> 2.3.17 & 2.2.22がデフォルト

        例3: bundler (2.3.17, 2.3.16, default: 2.2.22)
	        -> 2.2.22がデフォルト

        例4: bundler (default: 2.3.17, 2.3.16, 2.2.22)
	        -> 2.3.17だけがデフォルト

    インストールできるbundlerバージョン一覧
        $ gem search ^bundler$ --all

    特定のbundlerバージョンをインストール
        $ gem install bundler -v 2.3.17

    特定のbundlerバージョンをインストール & defaultに設定
        $ gem install --default bundler -v 2.2.22

        参照（https://www.fuwamaki.com/article/373）

    bundle install



## mysql2インストール

    gem install mysql2:0.5.4

    gem install mysql2:0.5.4 --source 'https://rubygems.org/'

    sudo yum install mysql-devel
    参照元(https://qiita.com/akk_ayy/items/f43a1af5368d1570c6f3)

    yum install [オプション] [パッケージ名]

    mysql-devel　（MySQL というデータベースの、開発用（development）のパッケージ

    インストールする対象のパッケージ（＝ファイル群）の名前。
    MySQLモジュールを使うCプログラムをコンパイルするといには、このパッケージが必要。
    gemのインストールの時に、Cプログラムのコンパイルが必要なgemがそこそこある。

    参照 (https://teratail.com/questions/177710)

    gem uninstall mysql2
    
    gem install mysql

## mariaDB削除・mysqlインストール

    mysqlの状態を確認する
    sudo systemctl enable mysql

    mariaDB削除・mysqlインストール（※raisetech資料）
    curl -fsSL https://raw.githubusercontent.com/MasatoshiMizumoto/raisetech_documents/main/aws/scripts/mysql_amazon_linux_2.sh | sh

    mysqlインストール時に一時的なパスワードを表示
    sudo cat /var/log/mysqld.log | grep "temporary password" | awk '{print $13}'

    mysqlに接続
    mysql -u root -p

    ユーザー名とパスワードを設定
    ALTER USER 'root'@'localhost' IDENTIFIED BY '設定するパスワード';

    データベース内のGRANTテーブルから再読み込みを実行するステートメント
    FLUSH PRIVILEGES;

    /etcは，Linuxディストリビューションを構成する各種プログラムの設定ファイルを格納したディレクトリ

    ls /etc
    cat /etc/my.cof

    データベースの情報確認コマンド
    show databases;


# VScodeのSSH接続の仕方と拡張機能

    参照(https://qiita.com/829yasubee/items/68aabe197a47202c8688)

# Nginx

## EC2にNginxをインストールする

    amazon-linux-extrasを使ってインストールできるパッケージの確認
        $ which amazon-linux-extras
        $ amazon-linux-extras

    Nginxのインストール
        $ sudo amazon-linux-extras install nginx1
        $ nginx -v

    初期設定ファイルのバックアップ

        $ sudo cp -a /etc/nginx/nginx.conf /etc/nginx/nginx.conf.back

## 起動設定

    Nginx起動
        $ sudo systemctl start nginx

    インスタンス起動時にNginxも自動で起動させる
        $ sudo systemctl enable nginx

    設定確認
        $ systemctl status nginx

        $ systemctl is-enabled nginx

    セキュリティグループで80を開放していれば、EC2のパブリックIPでnginxのデフォルト画面が表示される

    ブラウザで EC2インスタンスのIPv4パブリックIPを入力すると起動確認できる

	nginxを一旦停止
		$ sudo /etc/init.d/nginx stop

	nginxの設定ファイルを編集
		$ sudo vi /etc/nginx/nginx.conf

    Nginxをリスタート
		$ sudo systemctl restart nginx

	ファイルの所有者を変更する
		$  sudo chown ec2-user:ec2-user /etc/nginx/nginx.conf
		このコマンドでファイルの所有者をec2-userユーザーに変更する。

	圧縮ファイルの解凍
		$ sudo gzip -d ファイル名.gz



# unicorn

    unicornをインストール
		$ sudo gem install unicorn
	unicornの設定ファイルを作成

	unicornを起動
		$ cd [あなたのアプリ名]
		$ unicorn_rails -c config/unicorn.rb -D
		$ unicorn_rails -E production -c config/unicorn.rb -D (本番環境で稼働させる場合)

	プロセスを検索して起動確認
	unicorn masterが動いていればok
		$ ps ax|grep unicorn|grep -v grep
    
    unicornの停止
		$ kill -QUIT 12345  # マスタープロセスのPIDを指定


## blockedhostが解消

	unicorn.rbに以下を記述
		listen = ["localhost"]

	development.rb以下を記述
		config.hosts = ["unicorn"]
	必要に応じてdevelopment.rbに以下を記述
	config.hosts << "0.0.0.0"　（EC2のIPアドレス）

# css

	・rails assets:precompile

	config.assets.debug設定は、CSSの動作をデバッグするための設定。この設定をtrueにすると、以下のようになる。

	CSSファイルはコンパイルされない。
	CSSファイルは結合されない。
	CSSファイルに改行コードは追加されない。
	これらの変更により、CSSのファイルサイズが大きくなり、ページの表示速度が遅くなる。

	config.assets.debug設定をfalseにすると、以下のようになる。

	CSSファイルはコンパイルされる。
	CSSファイルは結合される。
	CSSファイルに改行コードが追加される。
	これらの変更により、CSSのファイルサイズが小さくなり、ページの表示速度が向上する。

	具体的には、CSSのコンパイルは、CSSファイルの記述をより効率的なコードに変換する処理である。これにより、CSSファイルのサイズを小さくすることができる。

	CSSの結合は、複数のCSSファイルを1つのファイルにまとめる処理である。これにより、CSSファイルの読み込み回数を減らすことができる。

	CSSへの改行コードの追加は、CSSファイルの読み込みを効率的に行うための処理である。これにより、CSSファイルの読み込み速度を向上させることができる。

	config.assets.debug設定をfalseにすることで、CSSのファイルサイズを小さくして、ページの表示速度を向上させることができる。ただし、CSSのデバッグが難しくなるというデメリットがある。

	デバッグが必要ない場合は、config.assets.debug設定をfalseにして、パフォーマンスを向上させることを検討するとよい。


	・ローカルで `rails assets:precompile` を実行してしまい以後アセットの更新が反映されなくなってしまった場合の対応
	(https://qiita.com/GandT/items/4b3701a6ca51ff84370c)


	・最後に躓いたところ
	
	nginx.conf内の63～65行目　
	
	location ~^/assets/ {
		root home/ec2-user/----
	}


	の部分を

	location ~^/assets/ {
		root /home/ec2-user/----
	}


	に書き換えたらCSSとJavaScriptが反映されるようになった。
	

## ALB


	nginx.confに下記を追記

	```

	location = /healthcheck.html {
    		empty_gif;
    		break;
	}

	```


	empty_gifとは？
	nginxの標準モジュールが持つ機能で、nginxがメモリに保持している1x1ピクセルの透過 GIF ファイルをクライアントに返すことができる。

	参照（https://qiita.com/yumiyon/items/5cd2c6b4c696355926dc）	


## S3

	S3を作成　参照（https://qiita.com/miriwo/items/41e488b79fb58fa7c952）


	
	本番環境(production)の保存先を:localから:amazonに変更

		config.active_storage.service = :amazon



	開発環境(development)でAmazon S3の動作を確認したい場合はこちらの方も変更

		config.active_storage.service = :amazon

	
	config/storage.yml の以下の部分をコメント解除する

		amazon:
  		service: S3
  		access_key_id: <%= Rails.application.credentials.dig(:aws, :access_key_id) %>
  		secret_access_key: <%= Rails.application.credentials.dig(:aws, :secret_access_key) %>
  		(以下の２行を変更)
  		region: ap-northeast-1 #東京の場合
  		bucket: my-rails-app-bucket #自分で作成したS3のバケットの名前

## 構成図

    draw.ioにて作成



# その他

	railsのログの削除
		rake log:clear

## オンプレミス

	オンプレミスとは、システムの稼働やインフラの構築に必要となるサーバーやネットワーク機器、あるいはソフトウェアなどを自社で保有し運用するシステムの利用形態

## ルートディレクトリとホームディレクトリ

	ルートディレクトリは階層構造の一番上にあるディレクトリシステムのこと、サブディレクトリはメインとなるディレクトリの中にあるディレクトリ、カレントディレクトリは自分が今表示させているディレクトリ、ホームディレクトリは、OSにログインした直後に表示されるディレクトリ、ディレクトリ名は、ディレクトリに付いている名前のこと


## セキュリティ

	* SSL通信
		SSL（Secure Socket Layer）/ TLS (Transport Layer Security)とは、インターネット上でデータを暗号化して送受信する仕組みのひとつ
	（https://www.soumu.go.jp/main_sosiki/cybersecurity/kokumin/basic/basic_structure_13.html）

	* Firewall
		ファイアウォールは、ネットワークの通信において、その通信をさせるかどうかを判断し許可するまたは拒否する仕組み
	（https://www.soumu.go.jp/main_sosiki/cybersecurity/kokumin/basic/basic_structure_01.html）


## CloudFormation

	* AWS CloudFormation
		コードの通りにAWS環境を構築するサービス。テンプレートファイルを読み込ませるだけで、あとは自動で環境を構築するAWSの機能。

	* テンプレートファイル
		AWSの環境（VPC、EC2等）の情報を記述したテキストファイル。
		記述形式はJSON形式、またはYAML形式。


	* Former2
		Former2 は、AWS アカウント内の既存のリソースから Infrastructure-as-Code 出力を生成できるようにする Web サービス。
		Former2 を使用すると、ユーザは既存の AWS 環境から CloudFormation や Terraform、Troposphere などのテンプレートを作成し、AWS インフラ構築の自動化に役立つ。（今回の課題では未使用）

## github

	* githubでSSH keys登録したときに、そのSSH keysを使うユーザーは「git」というユーザー。

## cron

	* (https://qiita.com/shota0616/items/af336cda4253242da3ee)


