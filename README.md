# check_es_system
This is a monitoring plugin to check the status of an ElasticSearch cluster node. Besides the classical status check (green, yellow, red) this plugin also allows to monitor disk or memory usage of Elasticsearch. This is especially helpful when running Elasticsearch in the cloud (e.g. Elasticsearch as a service) because, as ES does not run on your own server, you cannot monitor the disk or memory usage. This is where this plugin comes in. Just tell the plugin how much resources (diskspace, memory capacity) you have available (-d) and it will alarm you when you reach a threshold.
Besides that, the plugin offers additional (advanced) checks of a Elasticsearch node/cluster (Java Threads, Thread Pool Statistics, Master Verification, Read-Only Indexes, ...).

Please refer to https://www.claudiokuenzler.com/monitoring-plugins/check_es_system.php for full documentation and usage examples.

Requirements
------
- The following commands must be available: `curl`, `expr`
- One of the following json parsers must be available: `jshon` or `jq` (defaults to jq)

Usage
------

    ./check_es_system.sh -H ESNode [-P port] [-S] [-u user] [-p pass] [-d available] -t check [-o unit] [-i indexes] [-w warn] [-c crit] [-m max_time] [-e node] [-X jq|jshon]
