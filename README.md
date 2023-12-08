# RaiseTech memo

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
