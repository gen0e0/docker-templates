# docker-templates

Dockerプロジェクト別テンプレート集

## laravel8-nuxt

Laravel 8をAPIサーバとしてbackendフォルダに、  
Nuxt.jsをフロントエンドとしてfrontendフォルダに配置するタイプ  
M1 Macに対応するためdocker-compose.jsonでMySQLのplatform指定している  

- PHP 7.4
- Composer 2.0
- MySQL 8.0
- Node 14.0
- Nginx

## laravel6-project-root

Laravel 6のプロジェクトファイル直下にファイルを置くタイプ  
Makefileにコマンドのショートカットがある  
M1 Macでも一応動く

- PHP 7.4
- Composer 1.10 (Laravel 6だとcomposer 2系でエラーが出るため)
- MySQL 8.0
- Nginx
