## Execution Contract (Mandatory)

1. Approval gate
- 実作業（ファイル編集・コマンド実行・API更新・PR更新）は、作業方針を整理して提示した上で実行する。
- `push` は承認不要（ユーザー指定ブランチへの反映として常時許可）。
- 実行前に「目的/手順/影響範囲/対象ブランチ」を提示する。
- 依頼外作業、想定外の拡張は実行禁止（ただし `push` は本契約の例外規定に従う）。

2. Request source of truth
- セッション開始時、現在ブランチに対応する open PR を特定し、PR本文 `## Background` / `## Approach` を要求仕様として読む。
- 優先順位は「最新ユーザー指示 > PR本文 > その他文脈」。
- PRが存在しない場合は、その旨を報告して次アクションを確認。

3. Branch / push policy
- `push` 先は「その時点でユーザーが指定した対象ブランチ」のみ。
- `push` 前に対象ブランチ名を明示する（都度承認は不要）。
- 無断で別ブランチへ `push` しない。
- `merge` はユーザーのみ実行。AIは自律 `merge` しない。

4. Working mode
- 原則は remote-first 実装（対象ブランチへの直接変更を許可・推奨）。
- 方針確認・状況確認は remote参照を優先（PR/Issue/branch/commit等の読取）。
- GitHub APIでのリモートファイル直接変更（create/update/delete/commit API）は許可。
- リモート更新操作のうち `push` は承認不要。PR状態変更・コメント投稿等は承認後のみ。

5. Change unit
- 作業は小さいバッチに分割し、各バッチごとに「方針整理→実行→結果報告」。
- `push` は承認不要のため「対象ブランチ明示→実行→結果報告」で実施。
- 報告は「実施内容/差分要点/検証結果/未実施事項」を簡潔に提示。

6. Repository model alignment
- 想定モデル: trunk + tag-driven stability。
- 長期ブランチは `main`。安定性はタグで表現。
- ただし実運用の `push` 先は常にユーザー指定ブランチ規則を優先。

7. Completion handling
- 完了条件は「実装完了 + 検証完了 + 対象ブランチへ反映」。
- PRの Draft→Ready 変更など最終状態操作は、実施前に承認を取る（明示許可がある場合を除く）。

8. Communication style
- 提案と実行を明確に分離して記述。
- 不明点は推測で実行せず、確認質問を優先。

## Repository Context Resolution (Mandatory)

1. Default context
- 標準解釈は常に「ユーザーが示したリモートリポジトリ文脈」で行う。
- リポジトリ名/owner/URL が明示されている場合、まずそのリモート情報を参照する。

2. Local access prohibition by default
- ユーザーの明示指示がない限り、ローカルリポジトリへのアクセスを行わない。
- 禁止対象: `git status` / `git branch` / `git log` / ローカルファイル探索・読取・編集・実行。
- 「確認のためのローカル参照」も同様に禁止（明示指示がある場合のみ可）。

3. Unknown repository handling
- 対象リモートリポジトリが特定できない場合、推定で進めずユーザーへ確認する。
- 最小確認項目: `owner/repo` または GitHub URL。

4. Execution gate with remote-first
- 実作業は「作業方針整理後」に実行可（都度承認は不要）。
- 変更操作は対象ブランチに限定して実行する。
- `push` は承認不要（対象ブランチ明示を必須）。
- `push` 以外のリモート更新（PR更新/コメント投稿等）は承認後のみ。

5. Branch interpretation
- 「対象ブランチ」は原則リモート上の指定ブランチとして扱う。
- ローカルブランチ状態の確認は、ユーザーが明示的に要求した場合のみ実施。
