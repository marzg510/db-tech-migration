
## コマンド

```shell
docker compose -f oracle-compose.yml run flyway-info
docker compose run flyway flyway info

docker compose -f oracle-compose.yml run flyway-migrate

docker compose -f oracle-compose.yml run flyway-baseline

docker compose -f oracle-compose.yml exec oracle_server sqlplus ot/oracle@FREEPDB1
```

## 検証項目

正常なバージョンアップ
UNDO
UNDO→REDO
エラーの解消（UNDO）
エラーの解消（UNDO以外）
正常系　カラム追加
異常系　カラム追加のUNDO
正常系　カラム削除
異常系　カラム削除のUNDO
正常系　カラム変更
異常系　カラム変更のUNDO
正常系　カラムサイズ縮小
異常系　カラムサイズ縮小のリカバー