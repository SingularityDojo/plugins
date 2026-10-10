# Singularity Dojo plugins

[Singularity Dojo](https://singularity-dojo.vercel.app) の練習で使うスキルです。

| スキル | 呼び方（Codex） | すること |
|---|---|---|
| plan-md | `$dojo:plan-md <やりたいこと>` | 今日の日付ディレクトリに、テーマのディレクトリと plan.md を作る |
| report | `$dojo:report` | テーマのディレクトリに report.md を書いて、commit・push する |

## 入れ方（Codex）

```bash
codex plugin marketplace add SingularityDojo/plugins
codex plugin add dojo@singularity-dojo
```

入れたら `/clear` で新しいセッションにし、`$dojo` と打って候補に `plan-md (dojo)`・`report (dojo)` が出ることを確かめます。くわしくは準備講座 0-3 を見てください。
