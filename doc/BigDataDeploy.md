#Big-data deploy note
##steps(test mode)
>1.deploy hadoop(pseudo-distributed mode)
>2.deploy zookeeper
>3.deploy hbase
>4.deploy kafka

##1.Hadoop pseudo-Distributed mode
> step1: set JAVA_HOME in etc/hadoop/hadoop-env.sh $ test if bin/hadoop can show some usage
> step2: set configurations
> etc/hadoop/core-site.xml:
`<configuration>`
    `<property>`
        `<name>`fs.defaultFS`</name>`
        `<value>`hdfs://localhost:9000`</value>`
    `</property>`
`</configuration>`
>etc/hadoop/hdfs-site.xml:
`<configuration>`
    `<property>`
        `<name>`dfs.replication`</name>`
        `<value>`1`</value>`
    `</property>`
`</configuration>`

>step3: test if you can ssh localhost without a passphrase
> if cannot ssh to localhost,use follow commands :
> $ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
  $ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
  $ chmod 0600 ~/.ssh/authorized_keys

>step4: use command "bin/hdfs namenode -format" to format the namenode
>step5: sbin/start-dfs.sh

##2.Zookeeper
>step1:  configure conf/zoo.cfg, set :
>tickTime=2000
dataDir=/var/lib/zookeeper(this can be set by user's preference)
clientPort=2181
>step2: bin/zkServer.sh start
>step3: test --> "bin/zkCli.sh -server 127.0.0.1:2181" to test if zookeeper has benn deployed successed

##3.hbase(pseudo mode with zookeeper and hdfs)
>step1: set JAVA_HOME in conf/hbase-env.sh
>step2: configure conf/hbase-site.xml
>(1)set distributed mode
    `<property>`
      `<name>`hbase.cluster.distributed`</name>`
      `<value>`true`</value>`
    `</property>`
>(2)set hbase rootdir:
`<property>`
  `<name>`hbase.rootdir`</name>`
  `<value>`hdfs://localhost:8020/hbase`</value>`
`</property>`
>(3)add zookeeper mode:
`<property>`
  `<name>`hbase.zookeeper.quorum`</name>`
  `<value>`localhost`</value>`
`</property>`
`<property>`
  `<name>`hbase.zookeeper.property.dataDir`</name>`
  `<value>`/home/bd/zookeeper/var/lib/zookeeper`</vale>`
`</property>`
>step3: bin/start-hbase.sh
>step4: test --> browse the web : 192.168.18.230:16010 if it is running normal

##kafka
>if you have deployed zookeeper already,then you can use the command:
>"bin/kafka-server-start.sh config/server.properties" to start kafka, the default port is 9092
>some kafka command:
>(1)Create a topic:"bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test"
>(2)list topic : "bin/kafka-topics.sh --list --zookeeper localhost:2181"
>(3)send messages:"bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test"
>(4)Start a consumer: "bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning"