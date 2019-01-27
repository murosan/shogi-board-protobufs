# shogi-board-protobufs

protocol buffers for [Shogi Board](https://github.com/murosan/shogi-board)

## testing

↓ のツールを使用するのがおすすめです

https://github.com/ktr0731/evans

```sh
$ cd shogi-board-protobufs/
$ evans --host localhost --port 8080 ./protos/v1.proto
  ______
 |  ____|
 | |__    __   __   __ _   _ __    ___
 |  __|   \ \ / /  / _. | | '_ \  / __|
 | |____   \ V /  | (_| | | | | | \__ \
 |______|   \_/    \__,_| |_| |_| |___/

 more expressive universal gRPC client

localhost:8080> package v1

v1@localhost:8080> show service
+------------+----------------+-----------------------+--------------+
|  SERVICE   |      RPC       |      REQUESTTYPE      | RESPONSETYPE |
+------------+----------------+-----------------------+--------------+
| ShogiBoard | Connect        | EngineName            | Response     |
|            | Close          | EngineName            | Response     |
|            | GetOptions     | EngineName            | Options      |
|            | UpdateButton   | UpdateButtonRequest   | Response     |
|            | UpdateCheck    | UpdateCheckRequest    | Response     |
|            | UpdateSpin     | UpdateSpinRequest     | Response     |
|            | UpdateSelect   | UpdateSelectRequest   | Response     |
|            | UpdateString   | UpdateStringRequest   | Response     |
|            | UpdateFilename | UpdateFilenameRequest | Response     |
|            | Start          | EngineName            | Response     |
|            | Stop           | EngineName            | Response     |
|            | SetPosition    | SetPositionRequest    | Response     |
|            | GetResult      | EngineName            | Result       |
+------------+----------------+-----------------------+--------------+

v1@localhost:8080> service ShogiBoard

v1.ShogiBoard@localhost:8080> call Connect
name (TYPE_STRING) => TEST
{

}

v1.ShogiBoard@localhost:8080> call UpdateSpin
engine::name (TYPE_STRING) => TEST
spin::name (TYPE_STRING) => MultiPV
spin::val (TYPE_INT32) => 3
spin::default (TYPE_INT32) => 1
spin::min (TYPE_INT32) => 1
spin::max (TYPE_INT32) => 594
{

}
```
