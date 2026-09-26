# sumset — Household Finance Data Platform

家庭の財務データを記録・検証・集計・配信する、個人運用の小さなデータ基盤。ChatGPT 貼り付け製だった旧版（kakeibo / kakeibo_batch）を設計から自力で作り直しています。

## 開発 DB の起動

PostgreSQL 17 を Docker で動かします。ホストの localhost:15432 で待ち受けます。

```bash
cp .env.example .env    # POSTGRES_PASSWORD を書き換える
docker compose up -d
psql -h localhost -p 15432 -U sumset -d sumset
```

止めるときは `docker compose down`。データは Docker の volume に残ります。
