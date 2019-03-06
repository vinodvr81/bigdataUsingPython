

```bash
%%bash
hdfs dfs -ls /
```

    Found 2 items
    drwxr-xr-x   - root supergroup          0 2017-09-10 20:34 /data
    drwxr-xr-x   - root supergroup          0 2017-09-10 19:07 /user



```python
! hdfs dfs -ls /data/wiki
```

    Found 1 items
    drwxrwxrwx   - jovyan supergroup          0 2017-09-10 20:34 /data/wiki/en_articles_part



```python
! hdfs dfs -du -h /data
```

    73.3 M  /data/wiki



```python
! hdfs fsck /data/wiki/en_articles_part/articles-part -files -blocks -locations
```

    Connecting to namenode via http://localhost:50070/fsck?ugi=jovyan&files=1&blocks=1&locations=1&path=%2Fdata%2Fwiki%2Fen_articles_part%2Farticles-part
    FSCK started by jovyan (auth:SIMPLE) from /127.0.0.1 for path /data/wiki/en_articles_part/articles-part at Tue Mar 05 10:06:32 UTC 2019
    /data/wiki/en_articles_part/articles-part 76861985 bytes, 1 block(s):  OK
    0. BP-912138591-172.17.0.1-1508245861251:blk_1073741825_1001 len=76861985 Live_repl=1 [DatanodeInfoWithStorage[127.0.0.1:50010,DS-abfda850-d766-4f78-a27c-3744043afccc,DISK]]
    
    Status: HEALTHY
     Total size:	76861985 B
     Total dirs:	0
     Total files:	1
     Total symlinks:		0
     Total blocks (validated):	1 (avg. block size 76861985 B)
     Minimally replicated blocks:	1 (100.0 %)
     Over-replicated blocks:	0 (0.0 %)
     Under-replicated blocks:	0 (0.0 %)
     Mis-replicated blocks:		0 (0.0 %)
     Default replication factor:	1
     Average block replication:	1.0
     Corrupt blocks:		0
     Missing replicas:		0 (0.0 %)
     Number of data-nodes:		1
     Number of racks:		1
    FSCK ended at Tue Mar 05 10:06:32 UTC 2019 in 17 milliseconds
    
    
    The filesystem under path '/data/wiki/en_articles_part/articles-part' is HEALTHY



```python
! hdfs fsck /data/wiki/en_articles_part/articles-part -blockId blk_1073741825
```

    Connecting to namenode via http://localhost:50070/fsck?ugi=jovyan&blockId=blk_1073741825+&path=%2Fdata%2Fwiki%2Fen_articles_part%2Farticles-part
    FSCK started by jovyan (auth:SIMPLE) from /127.0.0.1 at Tue Mar 05 10:09:16 UTC 2019
    
    Block Id: blk_1073741825
    Block belongs to: /data/wiki/en_articles_part/articles-part
    No. of Expected Replica: 1
    No. of live Replica: 1
    No. of excess Replica: 0
    No. of stale Replica: 0
    No. of decommissioned Replica: 0
    No. of decommissioning Replica: 0
    No. of corrupted Replica: 0
    Block replica on datanode/rack: 1ad0ecc7064f/default-rack is HEALTHY

