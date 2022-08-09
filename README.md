# mediawiki
Docker project to launch mediawiki

## Install
1. Set database password in .env
2. Launch setup.sh

## setup.sh
docker-compose up -d 
wget https://releases.wikimedia.org/mediawiki/1.38/mediawiki-1.38.2.tar.gz
tar zxvf mediawiki-1.38.2.tar.gz && rm mediawiki-1.38.2.tar.gz
mv mediawiki-1.38.2 ./www/html/wiki
Set .env secrets in LocalSettings.php -> copy to ./www/html/wiki
wget https://github.com/bharley/mw-markdown/archive/refs/tags/v0.2.tar.gz
tar zxvf v0.2.tar.gz && rm v0.2.tar.gz
mv mw-markdown-0.2 ./www/html/wiki/extensions/Markdown
wget https://github.com/erusev/parsedown/blob/master/Parsedown.php
mv Parsedown.php ./www/html/wiki/extensions/Markdown
wget https://github.com/erusev/parsedown-extra/blob/master/ParsedownExtra.php
mv ParsedownExtra.php ./www/html/wiki/extensions/Markdown

Add to LocalSettings.php:
require_once("$IP/extensions/Markdown/Markdown.php");
