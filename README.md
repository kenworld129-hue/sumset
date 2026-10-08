# sumset — Household Finance Data Platform

家庭の財務データを記録・検証・集計・配信する、個人運用の小さなデータ基盤。ChatGPT 貼り付け製だった旧版（kakeibo / kakeibo_batch）を設計から自力で作り直しています。

## 設計文書

- [DB 再設計ノート](docs/db_redesign_notes.md): 旧版のスキーマの棚卸し（Before）と、R1 で作る 6 テーブルの設計方針・ER 図
- [ADR](docs/adr/): 設計判断の記録

## 開発 DB の起動

PostgreSQL 17 を Docker で動かします。ホストの localhost:15432 で待ち受けます。

```bash
cp .env.example .env    # POSTGRES_PASSWORD を書き換える
docker compose up -d
psql -h localhost -p 15432 -U sumset -d sumset
```

止めるときは `docker compose down`。データは Docker の volume に残ります。
