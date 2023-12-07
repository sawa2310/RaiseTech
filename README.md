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

## rails

    ・which rails

    ・rails -v
        railsのバージョンを確認

    ・gem install rails -v 7.0.4
        railsのバージョンを7.0.4を指定してインストール

