# BASH MySQL/MariaDB `execute`

An impressive ~~black magic~~ management tools to easily maintain your SQL code.

## 1. PRE-REQUISITES

Required Package :

```bash
sudo apt-get install ed
```

## 2. INSTALLATION

You have **no need** to `git clone` this repo to implement this on your Linux Box. Just [download from here](https://github.com/C0mmitBot/mariadb-execute/raw/master/execute) and copy the `execute` file to folder `/usr/local/bin`. 

```bash
cd /tmp
wget https://github.com/C0mmitBot/mariadb-execute/raw/master/execute
chmod +x /tmp/execute
sudo cp /tmp/execute /usr/local/bin
```

Of course, there is no restriction if you wanna fork this repo and changes the code to suit your needs. I'll be happy if you add the functionality to this script to make this more powerful. Please don't hesitate to gimme pull requests.

Example :

```bash
mkdir -p ~/Scripts
cd ~/Scripts/
git clone https://github.com/C0mmitBot/mariadb-execute.git mariadb-execute 
chmod +x execute
sudo ln -s ~/Scripts/mariadb-execute/execute /usr/local/bin 
```

## 3. COMMON USAGE: backup & restore

To perform backup just type in the directory that **already have** the `db.conf` file:

```bash
execute backup
```

This command will generate sub-folder with the name based on the date when you perform backup (format: `YYYY-MM-DD`), e.g. `2021-10-02`

To perform restore, just type the `execute restore` and add extra-parameter with the name of the folder that you've previously backup.

```bash
execute restore 2021-10-02
```

As simple as that.

## 4. ADVANCE USAGE: Code Development (SQL Routines)

You must code your data structures and initial data scripts in the SQL file with filename leading by 0 (zero)

  eg: `000-data-structure.sql`


The folder that contains your script must have a file named `db.conf` that contains config as below:

```bash
  db_host = your_database_hostname
  db_port = your_database_port
  db_user = your_username
  db_pass = your_password
  db_name = your_database_name
  db_charset = utf8mb4
  db_collation = utf8mb4_unicode_ci
```

You must code the Stored Routines inside the SUB-FOLDER named `routines` (without any quotes)

The routines script must save in the SQL file prefixed with filename leading by 0 (zero)

  eg: `001-my_stored-proc.sql`

I will expand (or rewrite) the documentation about how to use the `execute` to maintain the SQL Code Development soon.


## USAGE EXAMPLES

```bash
cd /path/to/your/folder
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


# ENJOY!
