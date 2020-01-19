# dockerfile
Apache, MySQL, PHP

## このDockerファイルの説明

ローカルの./mini_blog以下のファイルを/var/www/html以下にマウントする。

## MySQL、MySQLへの接続
user root
password pass
host mysql

```
docker exec -i -t [コンテナ名] bash
```
```
mysql -u root -p
```


### ドキュメントルートを変更したいとき
```
docker exec -i -t [コンテナ名] bash
```
上のコマンドでコンテナの内部に入る

```
cd /etc/apache2/
cd sites-available
apt-get update
apt-get install vim
vim 000-default.conf
```

000-default.confを下の様に変更する
```
DocumentRoot /var/www/html/［ドキュメントルートにしたいディレクトリ名］
```
