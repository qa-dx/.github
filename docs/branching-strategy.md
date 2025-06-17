## ブランチ戦略

基本方針は **Feature Branch + Pull Request Review** です。

- `main`：本番リリース用の安定ブランチ
- `develop`：開発の統合ブランチ
- `feature/*`：機能追加
- `bugfix/*`：バグ修正
- `hotfix/*`：本番の緊急修正
- `release/*`：リリース準備用のブランチ

```mermaid
gitGraph
   commit id: "初期コミット"
   branch develop
   checkout develop
   commit id: "開発開始"
   branch feature/awesome-feature
   checkout feature/awesome-feature
   commit id: "機能追加中1"
   commit id: "機能追加中2"
   checkout develop
   merge feature/awesome-feature id: "機能完了→developにマージ"
   commit id: "テスト修正"
   branch release/v1.0.0
   checkout release/v1.0.0
   commit id: "ドキュメント整備"
   checkout main
   merge release/v1.0.0 id: "mainにリリース反映"
   checkout develop
   merge release/v1.0.0 id: "developにもマージ"
   branch hotfix/urgent-bug
   checkout hotfix/urgent-bug
   commit id: "本番バグ修正"
   checkout main
   merge hotfix/urgent-bug id: "緊急修正をmainへ"
   checkout develop
   merge hotfix/urgent-bug id: "緊急修正をdevelopにも反映"
```

---

## ブランチ命名規則


```
feature/<概要>-issue-<issue番号>
bugfix/<概要>-issue-<issue番号>
hotfix/<概要>
```

例：
- `feature/CTM-101-add-login-page-issue-103`
- `bugfix/CTM-204-fix-date-format-issue-99`
