# Dockerのよく使うコマンド
## runコマンド
* 一つのコンテナを起動するコマンドでローカルにDockerイメージがない場合、DockerHubから自動でイメージを取得してくれる
 ```zsh
 % docker run "イメージ名"
 ```
* オプションコマンド
    * --name・・・コンテナに任意の名前をつける
     ```zsh 
     % docker run --name "変更後のコンテナ名" "変更前のコンテナ名"
     ```
    * --rm・・・コンテナを実行した後、コンテナを消去する
     ```zsh
     % docker run --rm "コンテナ名"
     ```
    * -it・・・シェルによってコンテナの中に入る

        ex) CentOS:8のbashCLIを起動し、コンテナ内に入る
     ```zsh
     % docker run -it centos:8 /bin/bash
     ```

## psコマンド
* 起動中のコンテナを表示するコマンド
 ```zsh
 % docker ps
 ```
* オプションコマンド
    * -a・・・停止中のコンテナも表示する
     ```zsh
     % docker ps -a
     ```

## start/stop/restartコマンド
* コンテナを起動、停止、再起動するコマンド
 ```zsh
 % docker start "コンテナ名/コンテナID"
 ```
## execコマンド
* 起動中のコンテナ内に入らず、コンテナ内に対してコマンドを実行する
 ```zsh
 % docker exec "コンテナ名" "実行したいコマンド"
 ```
* オプションコマンド
    * -it・・・コンテナ内に入る(詳細は[runコマンドのオプションコマンド](#runコマンド)参照)
     ```zsh
     % docker exec -it "~"
     ```
## rmコマンド
* 停止中のコンテナを削除する
 ```zsh 
 % docker rm "コンテナ名"
 ```
* オプションコマンド
    * -f・・・起動中のコンテ強制的に削除、強制削除はおすすめできない
     ```zsh
     % docker rm -f "コンテナ名"
     ```
## imagesコマンド
* ローカル内のDockerイメージを全て表示する
 ```zsh
 % docker images
 ```
## rmiコマンド
* Dockerイメージを削除するコマンド(削除対象のイメージで作成されたコンテナが起動している場合は実行できない)
 ```zsh
 % docker rmi "イメージID"
 ```
