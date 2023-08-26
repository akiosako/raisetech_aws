## 第四回課題<br>
※作成後EC2、RDSは削除済み<br>

### VPC作成<br>
![VPC構成図](https://github.com/akiosako/raisetech_aws/assets/107123973/0ec1f1b4-5938-42ef-9557-9d5fd70bce95)
### EC2作成<br>
[セキュリティグループの設定]<br>
インバウンド：マイIPからSSHのみ許可<br>
アウトバウンド：全て許可<br>

### RDS作成<br>
[セキュリティグループの設定]<br>
インバウンド：EC2のセキュリティグループからMySQL/Auroraのみ許可<br>
アウトバウンド：全て許可<br>

### C2からRDSへの接続確認<br>
①EC2起動を起動し、以下コマンドを実行<br>
$ sudo yum update -y 

②mariaDBの削除<br>
$ sudo yum remove mariadb-*

③MySQLリポジトリをインストール<br>
$ sudo yum localinstall https://dev.mysql.com/get/mysql80-community-release-el7-7.noarch.rpm -y<br>

④パッケージ(mysql-community-server)を取得<br>
$ sudo yum install --enablerepo=mysql80-community mysql-community-server -y<br>

⑤起動<br>
$ sudo systemctl start mysqld

⑥起動を確認<br>
$ systemctl status mysqld.service<br>
![MySQLの起動を確認](https://github.com/akiosako/raisetech_aws/assets/107123973/5274fa71-99ff-4040-9cec-3044699abeb4)<br>
⑦RDS接続確認<br>
mysql -u admin -p -h データベースエンドポイント<br>
![RDS接続確認](https://github.com/akiosako/raisetech_aws/assets/107123973/92bdc1cb-b3cf-4f73-9275-7fd4c63c7ec0)

