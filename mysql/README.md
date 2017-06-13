# MySQL

Convert all tables to a specific collation.

    $ DB="dbname"; ( echo 'ALTER DATABASE `'"$DB"'` CHARACTER SET utf8
    COLLATE utf8_general_ci;'; mysql "$DB" -e "SHOW TABLES" --batch
    --skip-column-names | xargs -I{} echo 'ALTER TABLE `'{}'` CONVERT TO
    CHARACTER SET utf8 COLLATE utf8_general_ci;' ) | mysql "$DB"

Backup all databases

    #!/usr/bin/env bash

    TIMESTAMP=$(date +"%F")
    BACKUP_DIR="/root/tmp/$TIMESTAMP"
    MYSQL_USER="root"
    MYSQL=/usr/bin/mysql
    MYSQL_PASSWORD="secret"
    MYSQLDUMP=/usr/bin/mysqldump

    mkdir -p "$BACKUP_DIR/mysql"

    databases=`$MYSQL --user=$MYSQL_USER -p$MYSQL_PASSWORD -e "SHOW DATABASES;" | grep -Ev "(Database|information_schema|performance_schema)"`

    for db in $databases; do
      $MYSQLDUMP --force --opt --user=$MYSQL_USER -p$MYSQL_PASSWORD --databases $db | gzip > "$BACKUP_DIR/mysql/$db.gz"
    done
