
## コマンド

```shell
docker compose -f oracle-compose.yml run flyway-info
docker compose run --rm flyway-info

docker compose -f oracle-compose.yml run flyway-migrate

docker compose -f oracle-compose.yml run flyway-baseline

docker compose exec oracle_server sqlplus ot/oracle@FREEPDB1
```

## 検証項目

### 1. 正常系シナリオ

| NO  | タイトル           | 確認事項                                                     | 確認結果 | 成功条件・特記事項 |
| --- | ------------------ | ------------------------------------------------------------ | -------- | ------------------ |
| 1   | 新規テーブル作成   | 何もない状態からCREATE TABLEできる                           |          |                    |
| 2   | NULL可カラム追加   | NULL可のカラムを追加する                                     |          |                    |
| 3   | NOT NULL制約追加 | NOT NULLのカラムを追加する                                   |          |                    |
| 4   | カラム桁数拡張     | カラムの桁数 拡張                                            |          |                    |
| 5   | カラム桁数縮小     | 縮小後より長いデータが入っていても、カラムの桁数を縮小できる |          |                    |
| 6   | カラム削除         | カラム削除                                                   |          |                    |
| 7   |                  |                                                              |          |                    |



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