# 道場のスキルは Codex のネイティブ plugin `dojo` として配り、`$dojo:plan-md` で呼ぶ

生徒（v0 は Windows ＋ WSL ＋ Codex CLI）に `plan-md`・`report` を配るのに、このリポジトリを marketplace `singularity-dojo` にし、plugin `dojo` として配る（`codex plugin marketplace add SingularityDojo/plugins` → `codex plugin add dojo@singularity-dojo`）。mattpocock/skills が Codex 向けに案内している形で、更新を `codex plugin marketplace upgrade` で届けられるため。

plugin のスキルは `plugin名:スキル名` で一覧に出るので、呼び方は `$dojo:plan-md`・`$dojo:report` になる。`$plan-md` と打っても、AI がファイルを探し当てて動くことがあるが、スキルとしては渡っていない（2026-10-10、codex-cli 0.160.0 で `codex exec --json` の記録で確かめた）。接頭辞を外したくなっても、外さない。

## Considered Options

- **skills.sh（`npx skills@latest add`）**: 接頭辞なしの `$plan-md` で呼べるが、ファイルを手元にコピーするので更新は生徒が手で行う。配る側の形として、ネイティブの plugin を選んだ
- **plugin 名 `dojo-skills`**（`mattpocock-skills` にならう）: 毎日打つ呼び方が `$dojo-skills:plan-md` と長くなり、スキル以外を入れたときに名前が合わなくなる
- **リポジトリ名 `skills`**（`mattpocock/skills`・`anthropics/skills` にならう）: このリポジトリの役割は、生徒が入れるための棚。OpenAI（`openai/skills`・`openai/plugins`）も Anthropic（`anthropics/skills`・`anthropics/claude-plugins-official`）も、中身の skills と配る棚の plugins を分けているので、棚の側の名前にした

## Consequences

- 道場のガイドは `$dojo:plan-md` で書く。Claude Code 用（`.claude-plugin/`）を足すときも plugin 名を `dojo` にし、ガイドは「Codex は `$`、Claude Code は `/`」の違いだけにする
- Codex は入れた plugin を `~/.codex/plugins/cache/` にコピーするので、このリポジトリを更新しても、生徒の手元にはすぐには届かない
