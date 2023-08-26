## 第四回課題<br>
※作成後EC2、RDSは削除済み<br>

### VPC作成<br>
<img width="705" alt="VPC構成図" src="https://github.com/akiosako/raisetech_aws/assets/107123973/17c84c60-709a-45a2-9fd8-3daac06dd755">

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
<img width="481" alt="MySQLの起動を確認" src="https://github.com/akiosako/raisetech_aws/assets/107123973/9c13d680-2dd2-4b24-ba32-aa67e2e0bae5"><br>

⑦RDS接続確認<br>
mysql -u admin -p -h データベースエンドポイント<br>
<img width="487" alt="RDS接続確認" src="https://github.com/akiosako/raisetech_aws/assets/107123973/3cdd41d9-6b62-4c2b-99e9-d55cd0e9f6e7">