# BASH SQL `execute`

An impressive ~~black magic~~ management tools to easily maintain your SQL code.

See changelog [here](#changelog)

## PRE-REQUISITES

Required Package :

```bash
sudo apt-get install ed
```

You have **no need** to `git clone` this repo to implement this on your Linux Box. Just [download from here](http://code.mokapedia.net/server/execute/raw/master/execute) and copy the `execute` file to folder `/usr/bin`. 

```bash
cd /tmp
wget http://code.mokapedia.net/server/execute/raw/master/execute
chmod +x /tmp/execute
sudo cp /tmp/execute /usr/bin
```

Of course, there is no restriction if you wanna fork this repo and changes the code to suit your needs. I'll be happy if you add the functionality to this script to make this more powerful. Please don't hesitate to gimme pull requests.


## GUIDES

You must code your data structures and initial data scripts in the SQL file with filename leading by 0 (zero)

  eg: `000-data-structure.sql`


The folder that contains your script must have a file named `db.conf` that contains config as below:

```bash
  db_host = your_database_hostname
  db_port = your_database_port
  db_user = your_username
  db_pass = your_password
  db_name = your_database_name
```

You must code the Stored Routines inside the SUB-FOLDER named `routines` (without any quotes)

The routines script must save in the SQL file prefixed with filename leading by 0 (zero)

  eg: `001-my_stored-proc.sql`



This folder naming convention was ALREADY setup for the workspace extracted from Mokapedia's [Git Project Template](http://code.mokapedia.net/angkringan/git-project-template)


## USAGE EXAMPLES

```bash
cd /path/to/your/queries/folder
execute init                             # this will create database, user & grant privileges automatically (this will drop everything!)
execute model                            # this will be drop/re-create your database and refill the schema + routines
execute code                             # this will be re-create ONLY the files under the 'routines' folder
execute "SELECT * FROM some_tables"      # this will be execute the specified queries and output the result to screen
execute backup                           # this will dump your database into *.sql that'll be generated on the timestamp-based-name subfolder
execute restore 2015-01-01               # this will restore the previously backup scripts on the given timestamp
execute help                             # display this inline help
execute generate-config                  # this will generate the db.conf (if not exists)
execute show-config                      # this will display the db.conf values
execute login                            # this will login into CLI Mode of MySQL/MariaDB database console
execute help                             # display this inline help
execute -v                               # display the program version
execute self-update                      # update the program
```

## CHANGELOG

```text
2015-01-05 : initial version, 4 methods available : execute model, code, query, help
2015-04-03 : update the README.md
2015-05-25 : added new argument : backup and restore
2015-06-08 : added 4 more argument : generate-config, show-config, --version, --self-update
2015-11-27 : added 2 new argument : --init and --login
```

# ENJOY!
