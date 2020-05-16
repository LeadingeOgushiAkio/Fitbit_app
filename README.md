# Fitbit_manage_app

開発環境
Windows10Pro  
Python 3.6.8

## Fitbitからデータを取得する

### API リファレンス
https://dev.fitbit.com/build/reference/  
(https://dev.fitbit.com/ にログインが必要)

### アプリケーションの作成
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
|OAuth 2.0 Application Type *|Clientもしくは|
|Callback URL *|http://127.0.0.1:8080/|
|Default Access Type *|Read-Only(データに変更は加えないので)|

☑ I have read and agree to the terms of service
チェックを入れてRegisterを押下する


### アクセストークンとリフレッシュトークンを取得する

任意のディレクトリにて
'git clone https://github.com/orcasgit/python-fitbit.git'
