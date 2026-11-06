# crud-with-agents

読んだ本と感想を記録する、シンプルな CRUD Web アプリです。
人間 1 人と AI エージェントによる「チーム開発」の進め方を、issue・PR・ブランチ戦略を含めて実践・記録することも目的にしています。

> 現在は開発基盤の準備中です（Epic #1）。

## チーム構成

| 役割 | 担当 | GitHub 上の名義 |
|---|---|---|
| レビュアー・承認者 | 人間（takanashi314） | takanashi314 |
| 開発者 | Claude Code GitHub Actions | claude[bot] |
| 計画・issue 管理 | Claude Code（クラウドセッション、人間の代理） | takanashi314 |

## ブランチ戦略

```
main  <-  feature/<機能>  <-  dev/<機能>/<issue番号>-<作業>
```

- `dev/*` → `feature/*`: squash merge
- `feature/*` → `main`: merge commit
- マージ済みのブランチも削除しません

## 技術スタック（予定）

Python 3.15 / Flask / Jinja2 + Bootstrap 5 / PostgreSQL / Docker / Google Cloud（Cloud Run・Cloud SQL）

## ライセンス

[MIT](LICENSE)
