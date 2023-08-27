## 第四回課題  

※作成後EC2、RDSは削除済み  

### VPC作成  
![VPC構成図](https://github.com/akiosako/raisetech_aws/assets/107123973/0ec1f1b4-5938-42ef-9557-9d5fd70bce95)
### EC2作成  
[セキュリティグループの設定]  
インバウンド：マイIPからSSHのみ許可  
アウトバウンド：全て許可  

### RDS作成  
[セキュリティグループの設定]  
インバウンド：EC2のセキュリティグループからMySQL/Auroraのみ許可  
アウトバウンド：全て許可  

### EC2からRDSへの接続確認  
1) EC2起動を起動し、以下コマンドを実行  
$ sudo yum update -y  

2) mariaDBの削除  
$ sudo yum remove mariadb-*  

3) MySQLリポジトリをインストール  
$ sudo yum localinstall https://dev.mysql.com/get/mysql80-community-release-el7-7.noarch.rpm -y  

4) パッケージ(mysql-community-server)を取得  
$ sudo yum install --enablerepo=mysql80-community mysql-community-server -y  

5) 起動  
$ sudo systemctl start mysqld  

6) 起動を確認  
$ systemctl status mysqld.service  
![MySQLの起動を確認](https://github.com/akiosako/raisetech_aws/assets/107123973/5274fa71-99ff-4040-9cec-3044699abeb4)
7) RDS接続確認  
mysql -u admin -p -h データベースエンドポイント  
![RDS接続確認](https://github.com/akiosako/raisetech_aws/assets/107123973/92bdc1cb-b3cf-4f73-9275-7fd4c63c7ec0) 

