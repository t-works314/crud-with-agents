# CLAUDE.md

このリポジトリで作業する Claude への指示です（最小版。完全版は Epic #1 で作成します）。

## 言語

- コミットメッセージ: **英語**（Conventional Commits。例: `docs: add issue templates`）
- issue・PR・ドキュメント: **日本語**

## ブランチ戦略

- `main` ← `feature/<機能>` ← `dev/<機能>/<issue番号>-<作業>` の 3 段構成
- dev ブランチは Task issue のラベル `feature:<機能>` からワークフローが自動で決めます。ブランチ名を自分で変えないでください。
- `main` と `feature/*` に直接 push しない。rebase・force-push もしない。
- ブランチは削除しない。

## Task issue で依頼されたとき（claude[bot]）

1. issue の内容どおりに作業し、英語のコミットメッセージでコミットする。
2. 作業履歴 `docs/histories/NN.md`（Epic ごとに 1 ファイル）に、今回の作業を日本語で追記する。
3. **必ず自分で PR を作成する**（PR 作成リンクを案内するだけで終わらない）:
   ```
   gh pr create --base feature/<機能> --title "<日本語のタイトル>" --body "<日本語の本文>"
   ```
   - 本文には `Refs #<Task の issue 番号>` を書く（`Closes` は書かない。Task は人間側でクローズする）。
   - 本文には「概要」「変更内容」「確認方法」を書く。
4. issue のコメントで PR のリンクを報告する。

## Epic の feature → main の PR を依頼されたとき

```
gh pr create --base main --head feature/<機能> --title "<日本語のタイトル>" --body "<本文>"
```

- 本文に `Closes #<Epic の issue 番号>` を書く。

## PR でレビュー指摘を受けたとき

- 指摘の内容だけを修正し、同じ PR のブランチに push する。
