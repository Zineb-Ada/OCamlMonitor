# OCaml library for monitoring runtime_events with Prometheus

The purpose of this library is to expose and serve runtime_events data and report metrics to a [Prometheus][] monitoring service. The goal is to represent this data graphically on [Grafana][] (for example).

The `lib/metrics.ml` provides all metrics related to runtime events (with all phases and counters).

This tool takes an executable and its arguments as argument and takes care of exposing runtime events via prometheus.

You can find the runtime events documentation here [Ocaml][]

```shell
$ dune exec bin/runtimevent.exe _build/default/test/test.exe
```
The default Prometheus port is 9090 but you can change it by adding the desired port number to your command :

```shell
$ dune exec bin/runtimevent.exe _build/default/test/test.exe — —p (or port) <port number>
```

This program provides metrics on : <http://localhost:9090/metrics>.

You can also see the graphs on <http://localhost:9090/graphs> for graphs.

[Prometheus]: https://prometheus.io
[Grafana]: https://grafana.com
[Ocaml]: https://github.com/ocaml/ocaml