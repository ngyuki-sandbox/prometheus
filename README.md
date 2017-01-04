# Prometheus 使ってみた

Prometheus を docker-compose で使ってみた

## 参考

- https://prometheus.io/docs/operating/configuration/
    - prometheus のコンフィグレーション
- http://qiita.com/sugitak/items/ff8f5ad845283c5915d2
    - 知ったきっかけ
- http://qiita.com/tukiyo3/items/da379f6e5844c99b65df
    - docker で動かして grafana で表示する例

## メモ

- Sensu で使ったときにも思ったけど Grafana の使い方がよくわからん
- 監視対象で exporter を実行して prometheus から PULL する感じ
- 外形監視は blackbox_exporter でできる
    - blackbox_exporter 自体は監視のモジュール？のみ設定する
    - prometheus 側でターゲットやモジュールを指定して↓みたいな URL にアクセスしてメトリクスを取得
        - `http://blackbox:9115/probe?target=example.com&module=http_2xx`

## 雑感

- やっぱ Grafana の使い方がよくわからなくてめんどくさそう
- 何もしなくてもそれっぽいダッシュボードがさーっと表示させられるようにしたいが・・
- Grafana のクエリを覚えてアドホックに表示するのが基本的な使い方？？
- ダウンサイジングが出来ないとのことなので１年とかのデータを保持するのは辛そう
- アラートは試していない
