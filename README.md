# Fitbit_manage_app


## アプリの使用説明を記述する部分

開発が終わったら書く


## 開発時に進めた手順(メモ)
開発環境  
Windows10Pro   
VS Code   
Python 3.6.8

モジュール(pipからインストール)  
fitbit  
cherryPy


### Fitbitからデータを取得する

#### API リファレンス
https://dev.fitbit.com/build/reference/  
(https://dev.fitbit.com/ にログインが必要)

#### アプリケーションの作成
https://dev.fitbit.com/login にfitbitアカウントでログインし  
Manageメニューにある REGISTER AN APP から新しくアプリケーションを作る

|項目|入力内容|
|-|-|
|Application Name *|アプリケーション名|
|Description *|説明|
|Application Website *|Webサイト|
|Organization *|組織名|
|Organization Website *|組織のWebサイト|
|Terms Of Service Url *|利用規約のURL|
|Privacy Policy Url *|プライバシーポリシーのURL|
|OAuth 2.0 Application Type *|Personal|
|Callback URL *|http://127.0.0.1:8080/|
|Default Access Type *|Read-Only(データに変更は加えないので)|

☑ I have read and agree to the terms of service
チェックを入れてRegisterを押下する


MANAGE MY APPSからOAuth 2.0 Client IDとClient Secretを取得し、メモする。  
この値は環境変数として自分の環境のみで保持し、アップはしない  
Python-dotenvで保持し、Gitにアップするのはサンプルファイルとする。


#### アクセストークンとリフレッシュトークンを取得する

任意のディレクトリにて
'git clone https://github.com/orcasgit/python-fitbit.git'

ターミナルから以下のコマンドを実行
作成したAPPSから取得したOAuth 2.0 Client IDとClient Secretを置き換える

`python gather_keys_oauth2.py {OAuth 2.0 Client ID} {Client Secret}`

ブラウザで自分のどのデータにアクセスできるかが表示される。
必要なものにチェックを入れてAllowを押下する。
押下後、ブラウザに以下の画面が表示されていればOK
```
You are now authorized to access the Fitbit API!

You can close this window
```
ターミナルに以下のようにアクセストークンとリフレッシュトークンが表示されているのでメモしておく  
access_token = ??????????????????  
refresh_token = ??????????????????

実際のコード中に使用するのは以下の4つ  
Client ID  
Client Secret  
access_token  
refresh_token  


上記を.envに保存しておく。またGitアップ用の.env.sampleも作成しておく

