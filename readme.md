# OCaml library for monitoring runtime_events with Prometheus

The purpose of this library is to expose and serve runtime_events data and report metrics to a [Prometheus][] monitoring service. The goal is to represent this data graphically on [Grafana][] (for example).
The `lib/metrics.ml` provides all metrics related to runtime_events (with all phases and counters).
The bin/runtimeevent.ml program includes a cmdliner option which it must be executed with another executable (`test/test.ml` in our case which contains an infinite loop) it can be executed as follows :

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