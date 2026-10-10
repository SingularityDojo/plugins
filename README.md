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

入れたら Codex を起動し直し、`/skills` に出ることを確かめます。くわしくは準備講座 0-3 を見てください。
