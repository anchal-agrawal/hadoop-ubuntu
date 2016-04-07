# hadoop-ubuntu

Everything to deploy a Hadoop cluster on Ubuntu

#### Bootstrap node

* `sudo apt-get update`
* `echo yes | sudo apt-get install default-jdk`
* Find download mirror on http://www.apache.org/dyn/closer.cgi/hadoop/common/
* Fetch and untar the binary package
* Add env variables in `.bashrc` (see [bash-env](https://github.com/anchal-agrawal/hadoop-ubuntu/blob/master/bash-env))

#### Configure Hadoop

* `cd $HADOOP_HOME/etc/hadoop`
* Change `core-site.xml`, `yarn-site.xml`, `hdfs-site.xml`, `hadoop-env.sh` (see [configs/](https://github.com/anchal-agrawal/hadoop-ubuntu/tree/master/configs))

#### Format HDFS (before deploying for the first time)

* `$HADOOP_PREFIX/bin/hdfs namenode -format`

#### Start HDFS

* `$HADOOP_PREFIX/sbin/hadoop-daemon.sh start namenode` (on master)
* `$HADOOP_PREFIX/sbin/hadoop-daemon.sh start datanode` (on workers)

#### Start YARN

* `$HADOOP_PREFIX/sbin/yarn-daemon.sh start resourcemanager` (on master)
* `$HADOOP_PREFIX/sbin/yarn-daemon.sh start nodemanager` (on workers)

#### References

1. https://hadoop.apache.org/docs/r2.7.1/hadoop-project-dist/hadoop-common/ClusterSetup.html
2. http://www.alexjf.net/blog/distributed-systems/hadoop-yarn-installation-definitive-guide/

#### Troubleshooting

1. HDFS/YARN process startup failures? Logs are your best friend! `$HADOOP_HOME/logs/`
2. https://wiki.apache.org/hadoop/TroubleShooting
3. To set up a remote cluster on a public cloud, configure ACLs to allow TCP traffic for the ports used by Hadoop. E.g. use an [NSG](https://azure.microsoft.com/en-us/documentation/articles/virtual-networks-create-nsg-arm-pportal/) for Azure.
4. https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-hdfs/HdfsMultihoming.html
