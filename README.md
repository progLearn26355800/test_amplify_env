# amplify の環境構築用リポジトリ <!-- omit in toc -->

## 目次 <!-- omit in toc -->
- [1. 構築する環境](#1-構築する環境)
- [2. 構築手順](#2-構築手順)
  - [2.1. docker-compose でコンテナ作成](#21-docker-compose-でコンテナ作成)
  - [2.2. amplify のプロファイル登録](#22-amplify-のプロファイル登録)


## 1. 構築する環境

- ベースイメージ: nikolaik/python-nodejs:python3.9-nodejs19-slim
- フレームワーク: react-native
  - expo を用いた動作確認


## 2. 構築手順

以下のURLを参考に
https://docs.amplify.aws/start/getting-started/installation/q/integration/react-native/

### 環境変数ファイルを作成

`.env`ファイルを作成し，以下のように内容を編集する

```.env
hogehoge=fugafuga
```

### 2.1. docker-compose でコンテナ作成

```
$ docker-compose up -d
```

作成後，コンテナにログイン

```
$ docker-compose exec <コンテナ名> /bin/bash
```

### 2.2. amplify のプロファイル登録

1. IAMユーザー作成
  - AWS console上で構築
  - 付与するポリシー: Administorator-Amplify 的なやつ
  - アクセスキー，シークレットキーをメモしておく

2. amplify cli 上で登録
```
amplify configure
```

3. アクセスキーを入力
4. シークレットキーを入力
5. プロファイル名を入力

### react native プロジェクトの作成

```
$ npx create-expo <プロジェクト名>
$ cd <プロジェクト名>
$ npm start
```

表示されたQRコードをexpo client で読み取る
もしくは expo client で以下のURI を入力

```
expo://<PCのIPアドレス>:8081/
```

#### 補足 <!-- omit in toc -->
1. expo client を実行するときは，プロジェクトを起動しているPCとexpo client を起動しているデバイスが同じネットワーク内に属している状態にすること

## amplify の導入

以下のコマンドを実行

``` 
$ amplify init
```

色々入力する項目あるけどまぁなんとかしようず

## amplify のリソース追加

1. リソースを追加する場合以下のコマンドを実行
```
$ amplify add <リソース名>
# 例1: GraphQL による Appsync を追加する場合
$ amplify add api
# API の種類を選択するタイミングでGraphQLを選択する
# もう一個でREST APIを選べるはず
#
# 例2: Cognito によるユーザー認証機能を追加する場合
$ amplify add auth
```

2. リソース追加をAmplify のアプリに反映する場合以下のコマンドを実行
```
$ amplify push
```

3. リソースの反映状況を確認
```
$ amplify status
```
