

# Environment

  * Spark 2.0.0
  * sbt 0.13.12
  * OpenJDK 1.8.0_101
  (Scala 2.11.8)

# Configuration

## Twitter API Key

Edit `src/main/resources/twitter4j.properties`

## Proxy

### SBT

Copy `.sbtopts.example` to `.sbtops` and edit.

### Spark

Declaration in `SPARK_HOME/conf/spark-default.conf`

```
spark.driver.extraJavaOptions -Dhttp.proxyHost=proxy.host -Dhttp.proxyPort=8080 -Dhttps.proxyHost=proxy.host -Dhttps.proxyPort=8080
```

# Build a jar

```
$ sbt
> assembly
```

# Run

```
$ spark-submit --class local.riverside.TwitterStreaming --master local[2] ./target/scala-2.11/spark-streaming-twitter-assembly-0.0.1.jar '#heartbleed'
```

# Reference

* http://d.hatena.ne.jp/Kazuhira/20150819/1439997051
* http://www.intellilink.co.jp/article/column/bigdata-kk01.html
