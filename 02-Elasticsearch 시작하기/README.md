## 2. Elasticsearch 시작하기
### 2.1 데이터 색인
### 2.2 JSON 문서와 REST API
### 2.3 설치 및 실행
```
$ bin/elasticsearch
[2017-02-01T07:21:48,096][INFO ][o.e.n.Node               ] [] initializing ...
[2017-02-01T07:21:48,180][INFO ][o.e.e.NodeEnvironment    ] [-MTDUpj] using [1] data paths, mounts [[/ (/dev/disk1)]], net usable_space [169gb], net total_space [464.7gb], spins? [unknown], types [hfs]
[2017-02-01T07:21:48,180][INFO ][o.e.e.NodeEnvironment    ] [-MTDUpj] heap size [1.9gb], compressed ordinary object pointers [true]
[2017-02-01T07:21:48,190][INFO ][o.e.n.Node               ] node name [-MTDUpj] derived from node ID [-MTDUpjzQj-Z9E2UVY63QA]; set [node.name] to override
[2017-02-01T07:21:48,193][INFO ][o.e.n.Node               ] version[5.2.0], pid[80279], build[24e05b9/2017-01-24T19:52:35.800Z], OS[Mac OS X/10.12.2/x86_64], JVM[Oracle Corporation/Java HotSpot(TM) 64-Bit Server VM/1.8.0_65/25.65-b01]
[2017-02-01T07:21:48,954][INFO ][o.e.p.PluginsService     ] [-MTDUpj] loaded module [aggs-matrix-stats]
[2017-02-01T07:21:48,954][INFO ][o.e.p.PluginsService     ] [-MTDUpj] loaded module [ingest-common]
[2017-02-01T07:21:48,955][INFO ][o.e.p.PluginsService     ] [-MTDUpj] loaded module [lang-expression]
[2017-02-01T07:21:48,955][INFO ][o.e.p.PluginsService     ] [-MTDUpj] loaded module [lang-groovy]
[2017-02-01T07:21:48,955][INFO ][o.e.p.PluginsService     ] [-MTDUpj] loaded module [lang-mustache]
[2017-02-01T07:21:48,955][INFO ][o.e.p.PluginsService     ] [-MTDUpj] loaded module [lang-painless]
[2017-02-01T07:21:48,955][INFO ][o.e.p.PluginsService     ] [-MTDUpj] loaded module [percolator]
[2017-02-01T07:21:48,955][INFO ][o.e.p.PluginsService     ] [-MTDUpj] loaded module [reindex]
[2017-02-01T07:21:48,955][INFO ][o.e.p.PluginsService     ] [-MTDUpj] loaded module [transport-netty3]
[2017-02-01T07:21:48,955][INFO ][o.e.p.PluginsService     ] [-MTDUpj] loaded module [transport-netty4]
[2017-02-01T07:21:48,956][INFO ][o.e.p.PluginsService     ] [-MTDUpj] no plugins loaded
[2017-02-01T07:21:50,736][INFO ][o.e.n.Node               ] initialized
[2017-02-01T07:21:50,736][INFO ][o.e.n.Node               ] [-MTDUpj] starting ...
[2017-02-01T07:21:55,968][INFO ][o.e.t.TransportService   ] [-MTDUpj] publish_address {127.0.0.1:9300}, bound_addresses {[fe80::1]:9300}, {[::1]:9300}, {127.0.0.1:9300}
[2017-02-01T07:21:59,020][INFO ][o.e.c.s.ClusterService   ] [-MTDUpj] new_master {-MTDUpj}{-MTDUpjzQj-Z9E2UVY63QA}{mzmQ8ittTiuwyODIwXhWkA}{127.0.0.1}{127.0.0.1:9300}, reason: zen-disco-elected-as-master ([0] nodes joined)
[2017-02-01T07:21:59,038][INFO ][o.e.h.HttpServer         ] [-MTDUpj] publish_address {127.0.0.1:9200}, bound_addresses {[fe80::1]:9200}, {[::1]:9200}, {127.0.0.1:9200}
[2017-02-01T07:21:59,038][INFO ][o.e.n.Node               ] [-MTDUpj] started
[2017-02-01T07:21:59,149][INFO ][o.e.g.GatewayService     ] [-MTDUpj] recovered [1] indices into cluster_state
[2017-02-01T07:21:59,331][INFO ][o.e.c.r.a.AllocationService] [-MTDUpj] Cluster health status changed from [RED] to [YELLOW] (reason: [shards started [[.kibana][0]] ...]).
```
