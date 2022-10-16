[return to maine page](../readme.md)

# list all the files and folders in current directory

```bash
    ls
```

# name of current directorye

```bash
 pwd
```

# remove file

```bash
    rm filename or
    rm -r name (for removing folder)
```

# create folder

```bash
    mkdir
```

# move file

```bash
    mv filename destination-folder
```

# install downloaded software

```bash
    sudo apt-get install ./name
```

# find files from all directory

```bash
find -name filename or
ls -r | grep filename
```

# Create Zip From folder

```bash
    zip -r file_name.zip folder_name
```

# Install mysql

```bash
    sudo apt-get install mysql-server
```

# Remove mysql

```bash
Stop the MySQL service:---

    sudo systemctl stop mysqld

Purge MySQL, databases, and configurations: ---
    sudo apt purge mysql-server mysql-common mysql-server-core-* mysql-client-core-*

Remove any additional database files:---
    sudo rm -rf /var/lib/mysql/

The folder where the configuration was and any stranglers:---
    sudo rm -rf /etc/mysql/

Clean the logs:---
    sudo rm -rf /var/log/mysql

Delete the user-generated during installation:---
    sudo deluser --remove-home mysql

Finally, get rid of the usergroup that was created during installation:---
    sudo delgroup mysql

That should get rid of everything. If you installed a third-party PPA in order to install MySQL then you'll need to remove that.---
    sudo add-apt-repository --remove ppa:theppayouused/ppa

```

# create custom command

```bash
    alias 'command_name' = "your command"
    eg.
    alias folders = "mkdir new{01..50}"
```

# get process id on current port and kill it

```bash
    lsof -i -P -n | grep port_number
    kill $(    lsof -i -P -n | grep port_number)

```

# force close vscode

```bash
    killall code
```

# switching tab

```
    ctrl + alt + tab or
    alt + tab
```

# switch to desktop

```
    ctrl + alt + (up or down arrow)
```
