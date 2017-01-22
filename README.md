# 시작하세요 엘라스틱서치 개정판 (가제)

## 목차 - (중간 중간 변경될 수 있음.)

1. [서문](./01-서문)
2. Elasticsearch 시작하기
  1. 설치 및 실행
    1. Unix 기반 운영체제에서 설치
    2. Windows 기반 운영체제에서 설치
    3. 이전 버전으로 부터 업그레이드
    4. 실행 파일 생성
  2. 프로그램 디렉토리 구조
    1. lib / modules
    2. bin
    3. data
    4. config
    5. logs
    6. plugins
  3. 환경 설정
    1. elasticsearch.yml
    2. jvm.options
    3. log4j2.properties
  4. 플러그인 설치
    1. 기본 플러그인 설치
    2. 사용자 정의 플러그인 설치

3. 데이터 처리
  1. 데이터 구조 (Index, Type, Document, Field)
  2. 데이터 처리
    1. 입력
    2. 조회
    3. 삭제
파일을 사용한 입력
Document APIs
Bulk
Reindex
Term Vectors
Kibana 설치 및 실행
Kibana Dev Tools 사용

시스템 구조
클러스터 (cluster)
클러스터 상태 정보
_cluster API
노드 (Node)
노드 바인딩
마스터 노드와 데이터 노드
샤드와 복사본 (Shard & Replica)
샤드와 복사본 개수 설정
디스커버리 (Discovery)
Zen discovery
EC2 discovery

검색
_search API
URI 검색
Request Body 검색
Query
From / Size
Sort
_source 필터링
highlight
rescore
suggester
scroll
Multi Search
Query Profiler
Profiling queries
Prifiling aggregation

검색 동작 구조
Page 매기기
검색 페이즈
검색 타입
query_then_fetch
dfs_query_then_fetch
세그먼트 Segments
세그먼트 개요
세그먼트 병합 – segment merge
Query Cash
Query Cash 동작 개요
BitSets

분석 (Text Analysis)
역파일 색인 (Inverted Index)
텍스트 분석 과정
Analyzer
사용자 정의 Analyzer
Standard / Whitespace
Stop
Pattern
Keyword
Character Filters
HTML strip char filters
Mapping char filters
Pattern replace char filters
Tokenizer
Standard / Whitespace
Letter / Lowercase
UAX URL Email
NGram / Edge NGram
Pattern
Keyword 
Token Filters
Lowercase
Synonyms – 동의어
Stop – 불용어
Shingle
Stemmer
CJK 
_analyze API
한글 형태소 분석기

매핑 (Mapping)
_mapping API
Data types
Numeric (+Bit Packing)
String – Text / Keyword
Binary
Boolean
Date
Geo-point
Geo-shape
IP
Array
Object
Nested
Token count
Percolator
Parent – Child 관계
메타 필드
_id
_uid
_source
_field_names
_all
_mapping
_index
_parent
_routing
매핑 자동화 (Dynamic Mapping)
Default mappings
Dynamic field
Index templates

Query DSL
쿼리와 필터
query_string
일반 쿼리
term / terms
match / match_phrase / match_phrase_prefix
match_all
range
exists
prefix / wildcard / regexp
복합 쿼리
bool
function_score
boosting
조인 쿼리
nested
has parent / child
Geo 쿼리
Geo Shape
Geo Bounding Box
Geo Distance
Geo Distance Range
Geo Polygon
More Like This 쿼리
Percolate 쿼리

검색어 추천 – suggesters (보류)
suggester 개요
query 구조
Term suggester
Phrase suggester
Completion suggester
Context suggester

Aggregation
개요
keword 타입과 doc_value
Metric aggregation
Sum / Min / Max / Avg
Aggregation 복합 사용
Stats
Percentiles
Cardinality
Bucket aggregation
Terms
Significant Terms
Range / Date Range
Histogram / Date Histogram
Pipeline aggregation
개요
Sum / Min / Max / Avg bucket
Derivative bucket
Stats bucket
Percentiles bucket
Moving average

연관도 Relevancy (보류)
개요
Vector Space 모델
TF-IDF
루씬 랭킹 공식
쿼리 조정
Boosting
Function Score
Random score
Decay function

Elasticsearch 시스템 API
_cat API
Shard allocation
Timeout
Thread pool
Tribe node
Painless Script
Snapshot & Restore
플러그인 설치

Kibana
개요
설치 및 실행
환경 설정
kibana.yml
Index Patterns
Object 관리
Advanced Settings
Discover
Time Filter
Query Bar
Visualize
Metric
Line / Area / Vertical Bar charts
Pie chart
Data Table
Tile maps
Tag cloud
Markdown widget
Dashboard
Dashboard 생성
Dashboard 공유
Timelion
Timelion 함수들
Time Series Visualization
Dev Tools
Management

Logstash
개요
설치 및 실행
config 파일 구조
조건문 입력
코덱
입력 Input
stdin
file
beats
jdbc
elasticsearch
출력 Output
stdout
elasticsearch
필터 Filter
csv
grok
mutate
kv
geoip


Beats
개요
설치 및 실행
.yml 환경 설정
scripts 를 이용한 대시보드 생성
Packetbeat
Filebeat
Metricbeat
사용자 정의 Beats 만들기

X-Pack
개요
설치
Basic License key 신청
elasticsearch.yml 설정
kibana.yml 설정
Monitoring
개요
Elasticsearch overview
Indices
Nodes
Kibana overview
Security
개요
Realms
Users / Roles
Kibana 에서 사용자 추가
Alerting
개요
입력 inputs
트리거 triggers
조건문 conditions
동작 actions
reporting
리포트 생성
Graph
Graph 
Machien Learning (Prelert)
개요
레서피 작성
데이터 모델
특이점 분석

Elastic Cloud
Elastic Cloud
계정 생성
클러스터 설정
Elastic Cloud Enterprise
설치
관리

Elastic Stack 시스템 운영 가이드
시스템 추천 사양
JVM Heap
Avoid Swap
File Descriptors
SSD vs Spinning disk
대용량 아키텍처 운영 전략
Hot & Warm nodes
Message broaker – Kafka
Multi cluster
Elasticsearch 벤치마크 테스트

맺음말

