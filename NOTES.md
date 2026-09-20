# Trade OS

XAUUSD裁量トレード用の自作トレード管理アプリ。長期的にトレード業務の中核ツールにする予定。

## 目的
自動売買ではなく、「感覚だけのEntryを減らし、SL→Lot→RR確認→記録→検証を習慣化する」ための裁量トレード支援ツール。最終判断は本人が行う。

## 現状
- Phase 1（Risk/Lot/RR計算、トレード記録、決済後更新、一覧、統計、SQLite）はClaude Codeでローカル実装済み。GitHubで管理。
- 以前Claudeが単一HTML版（Stage 1: Briefゲート、Entry計算＋ロック、決済記録、週次レビュー、localStorage）を作成したが、簡易的すぎると判断し、本格版を作る方針に転換（2026年9月）

## 環境
- PCファースト（Mac・複数モニター）。スマホは閲覧程度でよいが対応にも関心あり
- 既存有料環境：ChatGPT Plus（Bob）、Claude Pro/Claude Code（Zoro）、TradingView、Bookmap、リアルタイムCOMEX GCデータ
- 追加の従量課金APIは極力避けたい
- 口座の約定履歴自動取得をTrade OSに組み込みたい（cTraderを検討中の主な理由）

## UX方針
- 入力項目を増やさない、選択式多用、画面遷移なし
- 記録が重いと使わなくなる自覚があるため、UXを最優先する

## 避けたいこと
- 機能過多
- 開発自体が目的化すること
- AI依存
- バックテストの過剰適合
- 最初から完全自動化すること

## トレードルール（Trade OSに組み込む前提のルール）
- Risk：1トレードあたり0.5%
- RR最低1:2（理想1:3〜1:4）
- 全EntryでSL必須。SLを決めてからLotを逆算
- 重要指標（FOMC/CPI/雇用統計）・要人発言前後はノーポジ
- SLを損失方向に広げない
- リベンジトレード禁止

## ツールの役割分担
- TradingView（Daily/8H/4H/15M/5M）＝どこで取引するか
- Bookmap（COMEX GC板）＝今Entryしてよいか
- BOB EDGE（別プロジェクト、`bob-edge.md`参照）＝相場環境を定量化するものとして育てたい
- Morning Brief（朝の環境認識）は重要機能。初期は半自動でよい

## 開発体制
- コードを書くのはClaude Code一本
- Bob（ChatGPT）はPine Script/BOB EDGEと相場・仕様の相談役
- GitHubリポジトリの有無は未確認 → Claude Codeに確認・作成を依頼予定

出典：`rules-docs/docs/trade-os.md`。2026-09-20 にこのフォルダへ移動した。
