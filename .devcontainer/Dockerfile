FROM ubuntu:24.04

# パッケージの更新
RUN apt-get update
RUN apt-get upgrade -y

# localesパッケージのインストール
# システムの地域の設定を行うためのツール
RUN apt-get install -y locales

# gitのインストール
RUN apt-get install -y git

# curlのインストール
RUN apt-get install -y curl

# hugoのインストール
RUN curl -L -o hugo_extended.deb https://github.com/gohugoio/hugo/releases/download/v0.129.0/hugo_extended_0.129.0_linux-arm64.deb
RUN apt-get install -y ./hugo_extended.deb
RUN rm hugo_extended.deb

# apt-get update で取得された一時的に保存されたリポジトリ情報を削除する
RUN rm -rf /var/lib/apt/lists/*

# ロケールを作成する
RUN localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8

# 環境をen_US.utf8に設定
ENV LANG en_US.utf8
