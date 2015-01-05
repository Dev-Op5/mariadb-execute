## PRE-REQUISITES

You must code your data structures and initial data scripts in the SQL file with filename leading by 0 (zero)
  eg: 000-data-structure.sql

The folder that contains your script must have a file named db.conf that contains config as below:
  db_host = your_database_hostname
  db_port = your_database_port
  db_user = your_username
  db_pass = your_password
  db_name = your_database_name

You must code the Stored Routines inside the SUB-FOLDER named 'routines' (without any quotes)
The routines script must save in the SQL file prefixed with filename leading by 0 (zero)
  eg: 001-my_stored-proc.sql

This folder naming convention was ALREADY setup for the workspace extracted from Mokapedia's [git_project_template.tar.gz](http://src.mokapedia.net/git_project_template.tar.gz)


## USAGE EXAMPLES

cd /path/to/your/queries/folder
execute model                            # this will be drop/re-create your database and refill the schema + routines
execute code                             # this will be re-create ONLY the files under the 'routines' folder
execute "SELECT * FROM some_tables"      # this will be execute the specified queris and output the result to screen
execute help                             # display this inline help


## TIPS

For global usage, copy the `execute` file within /usr/bin

```bash
sudo cp /path/to/your/execute /usr/bin
```

# ENJOY!
