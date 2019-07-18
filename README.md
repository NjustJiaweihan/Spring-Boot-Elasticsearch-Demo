# Spring-Boot-Elasticsearch-Demo

### 版本问题

spring-data-elasticsearch与本地的elasticsearch的版本不匹配就会出现下面的ERROR：

```
None of the configured nodes are available:[{#transport#-1}
```

**官方提供的版本对照表：**

|  spring data elasticsearch   | elasticsearch  |
|  --------------------------  | -------------  |
|          3.1.x.              |     6.2.2      |
|          3.0.x               |     5.5.0      |
|          2.1.x               |     2.4.0      |
|          2.0.x               |     2.2.0      |
|          1.3.x               |     1.5.2      |

Demo-1.0使用的本地elasticsearch版本为[elasticsearch-6.2.4-MacOS](https://www.elastic.co/downloads/past-releases/elasticsearch-6-2-4)与[JDK1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

MacOS多版本JDK切换方法[参考阅读](https://docs.oracle.com/javase/8/docs/technotes/guides/install/mac_jdk.html#CHDBADCG)

elasticsearch-6.2[官方文档](https://www.elastic.co/guide/en/elasticsearch/reference/6.2/index.html)

### Demo启动步骤(MacOS)

- IDEA打开`Spring-Boot-Elasticsearch-Demo-1.0`项目
- 开启maven的`auto-import` 等待依赖导入完毕
- 下载elasticsearch-6.2.4并解压 如下方式启动

```bash
$ cd elasticsearch-6.2.4/bin
# windows是运行elasticsearch.bat
$ elasticsearch
```
- IDEA运行DemoApplication
- 谷歌浏览器输入:`localhost:9200` 回车

```json
{
"name": "tuONNuK",
"cluster_name": "elasticsearch",
"cluster_uuid": "LolhTskySImUF5IeifY8OQ",
"version": {
"number": "6.2.4",
"build_hash": "ccec39f",
"build_date": "2018-04-12T20:37:28.497551Z",
"build_snapshot": false,
"lucene_version": "7.2.1",
"minimum_wire_compatibility_version": "5.6.0",
"minimum_index_compatibility_version": "5.0.0"
},
"tagline": "You Know, for Search"
}
```

- 谷歌浏览器输入:`localhost8080/save` 回车
- 谷歌浏览器输入:`localhost8080/book/1` 回车

```json
{
"id": "1",
"title": "ES Demo",
"author": "Deep",
"postDate": "2019-07-18"
}
```