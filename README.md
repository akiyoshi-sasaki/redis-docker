# 手順

1. コンテナの起動 `docker-compose up -d`
2. 使うファイルの用意 `docker cp SET_pokemon151.txt redis-docker-redis-1:/data/SET_pokemon151.txt`
3. コンテナにログイン `docker exec -it redis-docker-redis-1 /bin/bash` (※以降コンテナ内での作業)
4. redisを使う `redis-cli`
5. redisが空であることを確認 `keys *` 、「(empty array)」と出るはず
6. redisから出る `exit`
7. 用意したファイルをredisにセット `redis-cli < SET_pokemon151.txt`
8. もう一度redisに入る `redis-cli`
9 keyから値を取得する
    - ① `get 1`
    - ② `get 25`
    - ③ `get 151`

# 参考

- docker-composeでredis環境をつくる
    - https://qiita.com/uggds/items/5e4f8fee180d77c06ee1
- redis-cliの使い方
    - https://qiita.com/sawada_masahiko/items/1f60936c421ecab8dfbf
- 【入門】Redis
    - https://qiita.com/wind-up-bird/items/f2d41d08e86789322c71#%E5%8B%95%E4%BD%9C%E7%A2%BA%E8%AA%8D
