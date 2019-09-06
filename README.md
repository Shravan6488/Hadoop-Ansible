    Support CentOS and Ubuntu

Operation Step:
    1. disable firewall
    2. hdfs namenode -format
    3. start-dfs.sh 
    

Legacy Issue:
    1. Distributed Hadoop Support.
    2. Comprihension Further on Hadoop Basis.
    
Hadoop Cluster Role 
===================

Installs and configure Hadoop system (version 3.X) in a cluster of nodes.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

	# The type of the node: slave or master or resourcemanager or nodemanager or datanode or namenode 
	hadoop_type_of_node: slave
	# Hadoop base directory to install the software
	hadoop_parent_dir: /opt/hadoop-3.X
	hadoop_home: /usr/local/hadoop
	# Hadoop version to install
	hadoop_version: 3.0.0
	# A dictionary with a set of properties to set in the core-site.xml
	hdfs_props: {}
	# A dictionary with a set of properties to set in the yarn-site.xml
	yarn_props: {}

Example Playbook
----------------

This an example of how to install the Cluster:

In the "Worker Nodes"
```yml
  roles:
    - { role: 'hadoop', hadoop_master: 'MASTER_NODE_NAME_OR_IP' }
```

In the "Manager Node"
```yml
  roles:
    - { role: 'hadoop', hadoop_master: 'MASTER_NODE_NAME_OR_IP', hadoop_type_of_node: 'master'}




