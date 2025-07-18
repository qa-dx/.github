## コミットメッセージの書き方
### 形式

```
<emoji> <subject> #issue-no
```

#### example：

- `:memo: README.mdにコミットメッセージの書き方追加 `
- `:bug: ログアウト後にログイン情報が残ってしまうバグ修正 #22`

### テンプレートを使用
#### `~/.github/commit.template`ファイルを作成

```commit.template



# ==== Format ====
# :emoji: Subject #issue No.
#
# Commit body...

# ==== Emojis ====
# :memo:         ドキュメント作成
# :bug:          バグ修正
# :+1:           機能改善
# :sparkles:     部分的な機能追加
# :tada:         盛大に祝うべき大きな機能追加
# :recycle:      リファクタリング
# :shower:       不要な機能・使われなくなった機能の削除
# :green_heart:  テストやCIの修正・改善
# :shirt:        Lintエラーの修正やコードスタイルの修正
# :rocket:       パフォーマンス改善
# :up:           依存パッケージなどのアップデート
# :lock:         新機能の公開範囲の制限
# :cop:          セキュリティ関連の改善

# ==== The Seven Rules ====
# 1. Separate subject from body with a blank line
# 2. Limit the subject line to 50 characters
# 3. Capitalize the subject line
# 4. Do not end the subject line with a period
# 5. Use the imperative mood in the subject line
# 6. Wrap the body at 72 characters
# 7. Use the body to explain what and why vs. how
#
```

#### git config コマンドを実行
```bash
git config --global commit.template ~/.github/commit.template
```
