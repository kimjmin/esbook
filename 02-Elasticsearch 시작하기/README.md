## 2. Elasticsearch 시작하기
### 2.1 데이터 색인
### 2.2 JSON 문서와 REST API
### 2.3 설치 및 실행

###### 화면2-7 Elasticsearch 실행 화면
```
$ bin/elasticsearch
[2017-02-13T07:00:56,530][INFO ][o.e.n.Node               ] [] initializing ...
[2017-02-13T07:00:56,590][INFO ][o.e.e.NodeEnvironment    ] [-IOaU6D] using [1] data paths, mounts [[/ (/dev/disk1)]], net usable_space [232.1gb], net total_space [464.7gb], spins? [unknown], types [hfs]

... 중략 ...

[2017-02-13T07:00:58,797][INFO ][o.e.n.Node               ] initialized
[2017-02-13T07:00:58,797][INFO ][o.e.n.Node               ] [-IOaU6D] starting ...
[2017-02-13T07:01:03,967][INFO ][o.e.t.TransportService   ] [-IOaU6D] publish_address {127.0.0.1:9300}, bound_addresses {[fe80::1]:9300}, {[::1]:9300}, {127.0.0.1:9300}
[2017-02-13T07:01:07,021][INFO ][o.e.c.s.ClusterService   ] [-IOaU6D] new_master {-IOaU6D}{-IOaU6DTSBeESCjkrsLZYQ}{7OrnqXIzSPayQfPF8Q0Fbw}{127.0.0.1}{127.0.0.1:9300}, reason: zen-disco-elected-as-master ([0] nodes joined)
[2017-02-13T07:01:07,036][INFO ][o.e.h.HttpServer         ] [-IOaU6D] publish_address {127.0.0.1:9200}, bound_addresses {[fe80::1]:9200}, {[::1]:9200}, {127.0.0.1:9200}
[2017-02-13T07:01:07,037][INFO ][o.e.n.Node               ] [-IOaU6D] started
[2017-02-13T07:01:07,041][INFO ][o.e.g.GatewayService     ] [-IOaU6D] recovered [0] indices into cluster_state
```

###### 화면2-8 백그라운드로 실행된 Elasticsearch 로그 파일 내용
```
$ bin/elasticsearch -d
$ cat logs/elasticsearch.log

... 중략 ...

[2017-02-13T07:08:14,457][INFO ][o.e.n.Node               ] initialized
[2017-02-13T07:08:14,457][INFO ][o.e.n.Node               ] [-IOaU6D] starting ...
[2017-02-13T07:08:19,634][INFO ][o.e.t.TransportService   ] [-IOaU6D] publish_address {127.0.0.1:9300}, bound_addresses {[fe80::1]:9300}, {[::1]:9300}, {127.0.0.1:9300}
[2017-02-13T07:08:22,690][INFO ][o.e.c.s.ClusterService   ] [-IOaU6D] new_master {-IOaU6D}{-IOaU6DTSBeESCjkrsLZYQ}{5IPA51r4QMaTep7i6NEpiA}{127.0.0.1}{127.0.0.1:9300}, reason: zen-disco-elected-as-master ([0] nodes joined)
[2017-02-13T07:08:22,707][INFO ][o.e.h.HttpServer         ] [-IOaU6D] publish_address {127.0.0.1:9200}, bound_addresses {[fe80::1]:9200}, {[::1]:9200}, {127.0.0.1:9200}
[2017-02-13T07:08:22,707][INFO ][o.e.n.Node               ] [-IOaU6D] started
[2017-02-13T07:08:22,710][INFO ][o.e.g.GatewayService     ] [-IOaU6D] recovered [0] indices into cluster_state
```

###### 화면2-9 ps 명령으로 백그라운드로 실행중인 Elasticsearch프로세스 검색
```
$ ps -ef | grep elasticsearch
  501 68601     1   0  7:07AM ttys000    0:12.45 /usr/bin/java -Xms2g -Xmx2g -XX:+UseConcMarkSweepGC -XX:CMSInitiatingOccupancyFraction=75 -XX:+UseCMSInitiatingOccupancyOnly
 -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -server -Xss1m -Djava.awt.headless=true -Dfile.encoding=UTF-8 -Djna.nosys=true -Djdk.io.permissionsUseCanonicalPath=true -Dio.netty.noUnsafe=true
 -Dio.netty.noKeySetOptimization=true -Dio.netty.recycler.maxCapacityPerThread=0 -Dlog4j.shutdownHookEnabled=false -Dlog4j2.disable.jmx=true -Dlog4j.skipJansi=true
 -XX:+HeapDumpOnOutOfMemoryError -Des.path.home=/elasticsearch-5.2.0 -cp /elasticsearch-5.2.0/lib/elasticsearch-5.2.0.jar:/elasticsearch-5.2.0/lib/* org.elasticsearch.bootstrap.Elasticsearch -d
```

###### 화면2-10 kill 명령으로 엘라스틱서치 프로세스 종료
```
$ kill 68601
$ ps -ef | grep elasticsearch
  501 68800 66982   0  7:19AM ttys000    0:00.00 grep elasticsearch
$
```

###### 화면2-11 -p 옵션으로 es.pid 파일에 프로세스 ID 저장
```
$ bin/elasticsearch -d -p es.pid
$ ls
LICENSE.txt    NOTICE.txt     README.textile bin            config         data           es.pid
lib            logs           modules        plugins
$ cat es.pid
68863
$ ps -ef | grep elasticsearch
  501 68863     1   0  7:22AM ttys000    0:10.94 /usr/bin/java -Xms2g -Xmx2g -XX:+UseConcMarkSweepGC -XX:CMSInitiatingOccupancyFraction=75 -XX:+UseCMSInitiatingOccupancyOnly 
-XX:+DisableExplicitGC -XX:+AlwaysPreTouch -server -Xss1m -Djava.awt.headless=true -Dfile.encoding=UTF-8 -Djna.nosys=true -Djdk.io.permissionsUseCanonicalPath=true -Dio.netty.noUnsafe=true 
-Dio.netty.noKeySetOptimization=true -Dio.netty.recycler.maxCapacityPerThread=0 -Dlog4j.shutdownHookEnabled=false -Dlog4j2.disable.jmx=true -Dlog4j.skipJansi=true -XX:+HeapDumpOnOutOfMemoryError 
-Des.path.home=/elasticsearch-5.2.0 -cp /elasticsearch-5.2.0/lib/elasticsearch-5.2.0.jar:/elasticsearch-5.2.0/lib/* org.elasticsearch.bootstrap.Elasticsearch -d -p es.pid
  501 68909 66982   0  7:24AM ttys000    0:00.00 grep elasticsearch
```

###### 화면2-12 kill 명령으로 엘라스틱서치 프로세스 종료
```
$ kill 68863
$ ls
LICENSE.txt    NOTICE.txt     README.textile bin            config         data
lib            logs           modules        plugins
```

###### start.sh 파일의 내용
```
bin/elasticsearch -d -p es.pid
```

###### stop.sh 파일의 내용
```
kill `cat es.pid`
```

###### 화면2-13 start.sh, stop.sh 파일 생성 및 실행 권한 부여
```
$ echo 'bin/elasticsearch -d -p es.pid' > start.sh
$ echo 'kill `cat es.pid`' > stop.sh
$ chmod 755 start.sh stop.sh
$ ls
LICENSE.txt    NOTICE.txt     README.textile bin            config         data           lib
logs           modules        plugins        start.sh       stop.sh
$
```

###### 화면2-14 start.sh, stop.sh로 엘라스틱서치 실행 및 종료
```
$ ./start.sh
$ ls
LICENSE.txt    README.textile config         es.pid         logs           plugins        stop.sh
NOTICE.txt     bin            data           lib            modules        start.sh
$ ps -ef | grep elasticsearch
  501 69246     1   0  7:41AM ttys000    0:10.60 /usr/bin/java -Xms2g -Xmx2g -XX:+UseConcMarkSweepGC -XX:CMSInitiatingOccupancyFraction=75 -XX:+UseCMSInitiatingOccupancyOnly 
-XX:+DisableExplicitGC -XX:+AlwaysPreTouch -server -Xss1m -Djava.awt.headless=true -Dfile.encoding=UTF-8 -Djna.nosys=true -Djdk.io.permissionsUseCanonicalPath=true -Dio.netty.noUnsafe=true 
-Dio.netty.noKeySetOptimization=true -Dio.netty.recycler.maxCapacityPerThread=0 -Dlog4j.shutdownHookEnabled=false -Dlog4j2.disable.jmx=true -Dlog4j.skipJansi=true 
-XX:+HeapDumpOnOutOfMemoryError -Des.path.home=/elasticsearch-5.2.0 -cp /elasticsearch-5.2.0/lib/elasticsearch-5.2.0.jar:/elasticsearch-5.2.0/lib/* org.elasticsearch.bootstrap.Elasticsearch -d -p es.pid
  501 69266 66982   0  7:42AM ttys000    0:00.00 grep elasticsearch
$ ./stop.sh
$ ls
LICENSE.txt    NOTICE.txt     README.textile bin            config         data           lib
logs           modules        plugins        start.sh       stop.sh
$ ps -ef | grep elasticsearc
  501 69281 66982   0  7:42AM ttys000    0:00.00 grep elasticsearc
```

