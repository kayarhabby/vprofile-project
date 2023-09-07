# fetch mysql:8.0.33 image on dockerhub
FROM mysql:8.0.33
# add label 
LABEL "Project"="Vprofile"
LABEL "Author"="Rhabby"

# set a variable for database

ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"

# dump the file db_backup.sql in docker-entrypoint-initdb.d/db_backup.sql
ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql
