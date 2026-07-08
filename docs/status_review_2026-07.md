# Repository Status Review — 2026-07

Cross-repo Architecture Audit（2026-07-07）後の本Repository整理。
2026-07-08 承認済み（conclusion の境界表現を補正のうえ承認）。

```yaml
repository:
  name: yemalthouse-wq/nkm-protocol

  responsibility: >
    .nkm ストリートマガジンのプロトコル層（ドクトリン正本）。
    不変ルール（QR→Hidden Page→Discord→Creator、都市選定、Creator招待制）、
    マスター決定（decision_009）、ロードマップ、Issue 001 作業ファイルのみを保持。

  current_status: FROZEN_MID_EXPERIMENT
  status_detail: >
    全13ファイルが 2026-03-04 の1日で作成され、以後4ヶ月コミットゼロ。
    内容はドクトリンとして純粋（コード・ログ・他事業の混入ゼロ = 全repo中最クリーン）。
    ただし roadmap は「フェーズ1（現在）」のまま Q2 が失効し、
    3月以降の .nkm 決定は ops-log の観測ログ内に流出して未還流。

  evidence:
    - "git: 全コミット 2026-03-04 / origin/main = ba898f6 / tree clean"
    - "コード・CI・package・config・logs 一切なし（純ドキュメントrepo）"
    - "決定ファイルは decision_009 のみ。ops-log が参照する decision_011/012 は実体なし"
    - "ops-log/logs/2026-05-22/nkm-archaeology.md 等に 3月以降の .nkm 決定があり本repoに未反映"
    - "内部矛盾①: city_selection『2/3条件』vs roadmap フェーズ4『3条件列挙』"
    - "内部矛盾②: decision_009『最新号のみ・毎号上書き』vs url_map の恒久7セクション"
    - "README は1行のみ。02_WORKING/nkm/magazine は拡張子なし・cover_lines と重複"

  risks:
    - "ドクトリン空洞化: 本repoを信頼する読者は3〜4ヶ月古いプロトコルに従う"
    - "decision registry 分裂（正本不在・欠番001-008・幽霊011/012）"
    - "都市選定基準の二重定義はフェーズ4到達時に判定不能を起こす"
    - "URL方針未整理は Issue 002 発行時に即設計判断を強制する"

  missing_information:
    - "unknown: QR 300枚配布の実施有無とフェーズ1の結果"
    - "unknown: decision_001〜008 / 011 / 012 の所在・正文"
    - "unknown: nkm-site / nkm-site-clean と本repoの正式関係（未読）"
    - "unknown: roadmap 2026Q2 の失効扱い / Q3版の有無"

  recommended_state: HOLD
  state_reason: >
    ACTIVE ではない（決定流が他所・4ヶ月停止）。SEALED は矛盾2件と
    失効roadmapを封印するため不可。ARCHIVE 候補でもない（.nkm は稼働中で
    本repoが唯一のドクトリン置き場）。同期判断が下るまで HOLD。

  next_action:
    - "decision_NNN 系列の正本を本repoに置くか否かを人間が確定"
    - "3月以降の .nkm 決定を decision_010+ として還流 or 『03-04時点スナップショット』と明示、の二者択一"
    - "フェーズ1（QR実験）の結果を事実として確定"
    - "city_selection 2/3条件 vs 3条件の矛盾を一方に確定"
    - "url_map と decision_009 URL方針の関係を確定"
    - "README に責務1文と関連repo境界を書く判断"

  do_not_do_next:
    - "アーカイブしない / ops-log・the-garage に統合しない"
    - "nkm-editorial repo を作らない（『今作らない』決定が有効）"
    - "欠番決定を推測で補完しない"
    - "フォルダ taxonomy を改編しない / Issue 002 の設計を先行しない"

  conclusion: >
    nkm-protocol は「.nkm の唯一のドクトリン正本」として HOLD のまま温存し、
    新規作業を流し込まない。
    新しい観測・実験ログは本repoに記録しない。
    ドクトリンとして確定した事項のみ、
    明示的な同期判断のもとで本repoへ還流する。
```
