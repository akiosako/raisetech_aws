## 第四回課題  

※作成後EC2、RDSは削除済み  

### VPC作成
![VPC構成図.png](images%2FVPC%E6%A7%8B%E6%88%90%E5%9B%B3.png)
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
![MySQL起動確認.png](images%2FMySQL%E8%B5%B7%E5%8B%95%E7%A2%BA%E8%AA%8D.png)
7) RDS接続確認  
mysql -u admin -p -h データベースエンドポイント  
![RDS接続確認.png](images%2FRDS%E6%8E%A5%E7%B6%9A%E7%A2%BA%E8%AA%8D.png)
8) EC2、RDSがtestVPCに作成されたことを確認  
![EC2詳細.png](images%2FEC2%E8%A9%B3%E7%B4%B0.png)
![RDS詳細.png](images%2FRDS%E8%A9%B3%E7%B4%B0.png)