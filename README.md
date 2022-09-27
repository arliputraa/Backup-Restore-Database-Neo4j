# Backup Restore Online and Offline Database Neo4j

all script running in path file /home/neo4j-enterprise/bin$

## Offline Backup Restore Database Neo4j

* Stop Database Neo4j 

      ./neo4j stop 

* BACKUP OFFLINE (only offline)

      ./neo4j-admin dump --database=(name database you want to backup) --to=/(path file you want to backup)/(name file you want to backup).dump
      
Example:

      ./neo4j-admin dump --database=movies --to=/home/arliputraa/neo4j-enterprise-4.4.10/backup/backup_db_movies.dump
      
* RESTORE OFFLINE (can also be online)


      ./neo4j-admin load --from=/(name database you want to restore)/(name file backup).dump --database=(database name) --force
     
Example:

    ./neo4j-admin load --from=/home/arliputraa/neo4j-enterprise-4.4.10/import/backup_db_movies.dump --database=movies_backup --force


## Online Backup Restore Database Neo4j

* BACKUP ONLINE

Example 1. Use neo4j-admin backup to back up a single database.

       ./neo4j-admin backup --backup-dir=/home/arliputraa/neo4j-enterprise-4.4.11/backup --database=neo4j
      
Example 2. Use neo4j-admin backup to back up all databases.

    ./neo4j-admin backup --backup-dir=/home/arliputraa/neo4j-enterprise-4.4.11/backup --database=”*” 
    
or
    
    ./neo4j-admin backup --from=localhost:6362 --backup-dir=/home/arliputraa/neo4j-enterprise-4.4.11/backup --database=”*” 
      
* RESTORE ONLINE

      ./neo4j-admin restore --from=/home/arliputraa/neo4j-enterprise-4.4.11/backup/neo4j --database=neo4j_backup --force




