# docker_wordpress_template


## description
開発､ステージング､本番環境それぞれで切り替え可能な､ wordpress+mysql5.7コンテナ  
本番環境ではnginxによるvirtual hostを使用することを想定  
  
## howToUse
envファイル内を環境に合わせて変更する｡  
  
該当ディレクトリで以下を実行  
(起動後すぐはdatabase error が出るので注意)  
  
開発環境の場合  
~~~
docker-compose -f docker-compose.yml -f development.yml up -d --build
~~~
  
検証環境の場合  
~~~
docker-compose -f docker-compose.yml -f staging.yml up -d --build
~~~
  
本番環境の場合  
~~~
docker-compose -f docker-compose.yml -f production.yml up -d --build
~~~
  
  
ymlがどうマージされたか知りたいとき  
~~~
docker-compose -f docker-compose.yml -f development.yml -p development config
~~~
  
# reference
https://ikasamak503.hatenablog.com/entry/dry-docker-compose-yaml?utm_source=pocket_reader
  