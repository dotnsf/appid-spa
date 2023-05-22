# AppID SPA(Single Page Application)


## Overview 

AppID による認証機能を加えた SPA サンプル


## Pre-requisite

- Node.js

  - Node.js および npm 環境をインストール

- Docker

  - 本番運用する場合はコンテナイメージをビルドする必要があるため docker 環境をインストール

- AppID

  - `Applications`

    - `type = singlepageapp` なアプリケーションの登録

    - 同アプリケーションの `discoveryEndpoint` および `clientId` 情報の取得

    - `Allowed Callback URLs` および `Allowed Logout URLs` にアプリケーション運用時の URL を指定（試験的に利用する場合は `http://localhost:3000` を指定）

    - `Access Token Expiration` を設定（試験的に利用する場合はすぐ無効になるよう 600 など短めに設定）

  - `User management`

    - 上述で登録したアプリケーションへログインする資格のあるユーザー（のメールアドレスとパスワード）を登録

- 本アプリケーション

  - `.env` ファイル

    - 上述の中で取得した `clientId` および `discoveryEndpoint` の値を `.env` ファイル内の `REACT_APP_APPID_CLIENT_ID` および `REACT_APP_APPID_ENDPOINT` の値としてそれぞれ設定して保存する

  - 依存ライブラリのインストール（初回１回のみ）

    - `$ npm install`

## How to Run

- 試験的に localhost で実行する場合

  - 試験実行向けに Auth0 側の Application 設定を調整

  - `$ npm run start`

  - `http://localhost:3000` にアクセス

  - `LOGIN` ボタンでログイン。ログイン後は `LOGOUT` ボタンでログアウト

- 本番環境で運用する場合

  - 本番運用向けに Auth0 側の Application 設定を調整

  - `$ npm run build`

  - `$ docker build -t username/appid-spa .`

  - 出来上がったコンテナイメージ(`username/appid-spa`)をデプロイ

  - 運用サイトにアクセス

  - `LOGIN` ボタンでログイン。ログイン後は `LOGOUT` ボタンでログアウト


## Licensing

This code is licensed under MIT.


## Copyright

2023 K.Kimura @ Juge.Me all rights reserved.

  