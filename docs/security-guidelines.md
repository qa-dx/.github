# セキュリティガイドライン（Security Guidelines）

---

## 目次

- [認証・認可](#認証認可)
- [機密情報の管理](#機密情報の管理)
- [通信の保護](#通信の保護)
- [依存ライブラリと脆弱性管理](#依存ライブラリと脆弱性管理)
- [ソースコード管理の注意点](#ソースコード管理の注意点)
- [ユーザー入力の検証](#ユーザー入力の検証)
- [その他の推奨事項](#その他の推奨事項)

---

## 認証・認可

- 認証方式は以下のいずれかを採用してください。
  - JWT（JSON Web Token）ベースのトークン認証（推奨）
  - OAuth2 / OpenID Connect（外部IDPと連携する場合）
  - AWS Cognito（クラウドベースのID管理）
- ユーザー名・パスワード認証を採用する場合、以下を必ず実施してください。
  - パスワードはフロントエンドで**ハッシュ化する**
    - パスワードリプレイ攻撃の脆弱性は残るが、社内であり個人のよく使うパスワードが流出してしまうことのほうが問題と考えたため

---

## 機密情報の管理

- 開発環境・本番環境で**環境変数を分離**すること

---

## 通信の保護

- APIトークンやセッション情報をURLパラメータに含めないこと

---

## 依存ライブラリと脆弱性管理

- 使用するライブラリは **定期的にアップデート**すること
- `npm audit`, `pip-audit`, `safety`, `dependabot` などのツールを活用して**脆弱性スキャンを定期実施**
- 利用するOSSは信頼性・更新頻度を確認の上、導入判断すること

---

## ソースコード管理の注意点

- `secret`, `password`, `api_key` などのキーワードで**検索し漏洩がないか確認**
- 誤ってコミットした秘密情報は、履歴ごと削除（`git filter-repo`等を使用）

---

## ユーザー入力の検証

- **サニタイズ処理を徹底**し、XSS・SQL Injectionを防止する
- 入力値の**バリデーションは必ずサーバー側でも実施**
- ORM（例：SQLAlchemy, Prisma）を活用し、プレースホルダによる安全なクエリ実行を徹底

---
