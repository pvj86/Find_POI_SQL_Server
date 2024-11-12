# Find_POI_SQL_Server
Find POI using SQL Server
How to restore Database named POI:

Download POI_DB_zip.7z file from location and unzip it so you can get POI_Backup.bak. 

Database name is POI. If you already have POI database on your machine, you can name it POI_new for example. In that case restore code would be:

RESTORE DATABASE POI_new
FROM DISK = 'C:\path_to_backup\POI.bak'
WITH MOVE 'POI' TO 'C:\path_to_new_location\POI_new.mdf',
     MOVE 'POI_log' TO 'C:\path_to_new_location\POI_new_log.ldf',
     RECOVERY

Change 'C:\path_to_backup' to your location on local disk where you have downloaded POI_Backup.bak file.


I created two procedures:

FindPOIs_GeoJSON_Compressed and FindPOIs_GeoJSON_Compressed_Decompressed. First one is giving us required GeoJSON, compressed by SQL Server. And second one is inserting data into table GeoJsonResults where we can see two columns GeoJsonData (which is readable by user), and required GeoJSON, compressed by SQL Server - CompressedGeoJson column. At the beggining of procedures' code, you can find example how to execute.
