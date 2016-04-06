# hadoop-ubuntu
Everything to deploy a Hadoop cluster on Ubuntu

#### References
1. https://hadoop.apache.org/docs/r2.7.1/hadoop-project-dist/hadoop-common/ClusterSetup.html
2. http://www.alexjf.net/blog/distributed-systems/hadoop-yarn-installation-definitive-guide/

#### Troubleshooting
1. HDFS/YARN process startup failures? Logs are your best friend! `$HADOOP_HOME/logs/`
2. https://wiki.apache.org/hadoop/TroubleShooting
3. To set up a remote cluster on a public cloud, configure ACLs to allow TCP traffic for the ports used by Hadoop. E.g. use an [NSG](https://azure.microsoft.com/en-us/documentation/articles/virtual-networks-create-nsg-arm-pportal/) for Azure.
4. https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-hdfs/HdfsMultihoming.html
