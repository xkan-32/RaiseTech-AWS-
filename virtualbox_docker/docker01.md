# Dockerの概要
## コンテナ型の仮想化の特徴
* 仮想化する際に、ホストOS上にゲストOSを立ち上げる必要がない為、軽量
* プロセスを実行する為のOSはホストOSを使用している
## Dockerとは
* コンテナを管理するツール
## Dockerを使用するメリット
* 環境構築の時間低減
    * 環境構築の際に一つ一つ手でDLしたりする必要がなくなり、設定ファイルに従い構築されるため、コマンド１つで環境を構築できる
* 冪等性の確保
    * 毎度コマンドを入力し、構築する必要がない為、設定ファイルが正しく作成できていれば、いつでも同様の環境を構築でき、冪等性が保てる
* IaC(Infrastructure as Code)による自動化
    * インフラ環境をコード化できる為、CircleCI・ServerSpecなど自動化ツールと連携し、環境構築を自動化できる
## コンテナとは
* パッケージ化された箱のことで、サーバー上に隔離されたアプリ空間を作る
* 一つのコンテナに一つのアプリケーションというイメージ
    * nginx・Ruby・MySQLがそれぞれコンテナとして存在する感じ
* 実際にアプリケーションとしてDockerを使うためには、各コンテナ間でやりとりができるようにする必要がある(Compose)
## Dockerfile・Dockerイメージ・Dockerコンテナ
* Dockerfile
    * Dockerイメージを作成する為の指示書
    * DokerFileの先頭から順番に実行していくことで、Dockerイメージを作成する(buildコマンド)
* Dokerイメージ
    * レイヤ構造で構成されるコンテナ実行される前段階
    * レイヤ一つが一つのコマンドという感じ
    * runコマンドを実行することで、コンテナを実行できる
    * DockerHubから作成されたイメージを取得可能
* Dockerコンテナ
    * Dockerイメージをもとに実行される
    * イメージをもとに複数作成できるが、イメージと依存関係にある為、コンテナが作成されて起動状態では、イメージを消去できない


