### サンプルアプリケーションのデプロイ 
■デプロイ画面<br>
<img width="371" alt="スクリーンショット 2023-08-20 213208" src="https://github.com/akiosako/raisetech_aws/assets/107123973/8465ea21-40d9-418c-8f81-428ecf7f4133"> 

■APサーバの名前とバージョンを確認<br>
名前：Puma<br>
バージョン：5.6.5<br>
<img width="386" alt="スクリーンショット 2023-08-21 202004" src="https://github.com/akiosako/raisetech_aws/assets/107123973/8689624b-a331-40ef-9df4-b8f83cbd01c5"><br>

■AP サーバーを終了させた場合<br>
①ps -ef | grep pumaでPumaのプロセスを確認<br>
<img width="360" alt="スクリーンショット 2023-08-20 214318" src="https://github.com/akiosako/raisetech_aws/assets/107123973/08008a5f-5a14-4144-8d2d-f717d7a25901"><br>

②kill 'プロセスID'<br>
→接続できなくなる<br>
<img width="597" alt="スクリーンショット 2023-08-21 195808" src="https://github.com/akiosako/raisetech_aws/assets/107123973/a640b7e9-3937-4dca-a05b-d68c123d506a"><br>

③rails sコマンドで再起動<br>
<img width="369" alt="再起動" src="https://github.com/akiosako/raisetech_aws/assets/107123973/976887eb-dbf1-4a55-bf57-72b4f85d5f6f"><br>
④ブラウザから、正常に起動されることを確認<br>

■サンプルアプリケーションで使った DB サーバー（DB エンジン）の名前と、今 Cloud9 で動作
しているバージョンの確認<br>
DBエンジン：MySQL<br>
バージョン：8.0.34<br>
<img width="401" alt="スクリーンショット 2023-08-21 200619" src="https://github.com/akiosako/raisetech_aws/assets/107123973/3ecb8849-dc11-4f36-bad2-ae049ead49b1"><br>

■DB サーバーを終了させた場合<br>
①sudo service mysqld stopでDBサーバ停止<br>
<img width="364" alt="スクリーンショット 2023-08-20 213316" src="https://github.com/akiosako/raisetech_aws/assets/107123973/ab4c66fd-4be7-4bf0-86e5-bf460f2fa74e"><br>
<img width="750" alt="スクリーンショット 2023-08-20 213444" src="https://github.com/akiosako/raisetech_aws/assets/107123973/d5f515f2-64e6-4c5b-9494-ea4ff67111ef"><br>
DBサーバに接続できなくなる<br>
sudo service mysqld startで再起動後、DBサーバへの接続を確認<br>

■Rails の構成管理ツールの名前<br>
Bundler<br>

■今回の課題から学んだこと<br>
APサーバが停止している場合と、DBサーバが停止している場合では、エラーの表示のされ方が異なる。


