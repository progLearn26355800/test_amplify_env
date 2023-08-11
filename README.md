# amplify の環境構築用リポジトリ <!-- omit in toc -->

## 目次 <!-- omit in toc -->

## 構築する環境

- ベースイメージ: nikolaik/python-nodejs:python3.9-nodejs19-slim
- フレームワーク: react-native
  - expo を用いた動作確認


## 構築手順

以下のURLを参考に
https://docs.amplify.aws/start/getting-started/installation/q/integration/react-native/


### docker-compose でコンテナ作成

```
$ docker-compose up -d
```

### amplify のプロファイル登録

1. IAMユーザー作成
  - AWS console上で構築
  - 付与するポリシー: Administorator-Amplify 的なやつ
  - アクセスキー，シークレットキーをメモしておく

2. amplify cli 上で登録
```
amplify configure
```

