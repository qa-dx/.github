## 開発フロー

1. **Issueを作成**
1. **最新の`develop`をpull**
   ```bash
   git switch develop
   git pull origin develop
   ```
1. **`develop`からブランチを作成**
   - ブランチ名: `feature/<概要>-issue-<Issue番号>`
   - 例: `feature/add-login-form-issue-42`
   ```bash
   git switch -c "feature/add-login-form-issue-42"
   ```
1. **作業ブランチに commit&push**
   ```bash
   # 変更をステージング
   git add .
   git commit # ファイルが開くので開発内容を記載
   git push origin "feature/add-login-form-issue-42"
   ```
1. **`develop` 宛に Pull Request を作成**
