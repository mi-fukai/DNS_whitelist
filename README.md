# DNS_whitelist
Route53 resolver DNS Firewallのホワイトリストを管理するワークフロー

ホワイトリストのファイル名：domainlist.txt

## Gthub Actions

### ワークフロー
- ファイル：.github/workflows/main.yml
- 対象ブランチ
  - feature/*
  - stage
  - prod
- リポジトリ内にある「domainlist.txt」の変更をプッシュするとワークフローが実行される

### Repository secretsの作成
- [github.com](https://github.com/)にブラウザでアクセス
- リポジトリのメニュー「Settings」＞「Secrets」にて環境変数を登録する
- 以下の名称で作成すること
  - リージョン情報
    - DEV_AWS_REGION
    - STG_AWS_REGION
    - PROD_AWS_REGION
  - GithubActions用IAM RoleのArn（テンプレート「01-IAM-02-RoleForGithubActions.yml」で作成）
    - DEV_AWS_ROLE_ARN
    - STG_AWS_ROLE_ARN
    - PROD_AWS_ROLE_ARN
  - 保存先バケット名
    - DEV_S3_UPLOAD_BUCKET
    - STG_S3_UPLOAD_BUCKET
    - PROD_S3_UPLOAD_BUCKET

