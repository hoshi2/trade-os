# Trade OS

XAUUSD裁量トレード用の自作トレード管理アプリ（単一HTMLファイル・ビルド不要）。
エントリー前のゲートと規律チェックを行い、記録を残すための道具。

- 2026-07-08 に作成。もとは `roy-log` リポジトリの中に `/trade-os/` として同居していた。
  2026-09-20 に独立させた。
- データはブラウザの `localStorage`（`tos_cfg` / `tos_log` / `tos_state`）に入る。
  保存先は `hoshi2.github.io` という住所全体に紐づくため、URLが
  `/roy-log/trade-os/` から `/trade-os/` に変わってもデータは引き継がれる。
- 方針・トレードルールの詳細は `rules-docs/docs/trade-os.md` にある。
