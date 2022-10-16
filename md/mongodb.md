[return to maine page](../readme.md)

# install mongodb

```c
    download mongodb shell from there debian/ubuntu package
    https://www.mongodb.com/try/download/shell

    then download server using
    sudo apt install mongodb-server-core

    then go to
    cd /usr/lib/systemd/system

    then create file
    sudo touch  mongodb.service

    then open file using gedit and paste below content and save it

    sudo gedit mongodb.service

        Description=An object/document-oriented database
        Documentation=man:mongod(1)
        After=network.target

        [Service]
        User=mongodb
        Group=mongodb
        ExecStart=/usr/bin/mongod --quiet --config /etc/mongodb.conf

        [Install]
        WantedBy=multi-user.target

    check file status usign
        systemctl list-unit-files --type=service

    if file is mask then unmask using
    sudo systemctl unmask mongodb

    then run
    sudo systemctl enable mongodb.service

    now just run mongo to use mongodb
```

# list all database

```c
    show dbs
```

# create database or Select database

```c
    use db_name

    eg. use my_db
```

# check current database

```c
    db
```

# details about current database

```c
    use db_name
    db.stats()
```

# remove database

```c
    db.dropDatabase()
```

# create collection

```c
    db.createCollection(name,options)

    eg. db.createCollection('use,
    {})
```

# list all collections

```c
    show collections
```

# drop collections

```c
    db.collection_name.drop()

    eg.
    db.user.drop()
```

# insert into collection

```c
    db.collection_name.insert({})

    eg.
    db.user.insert([
    {
        "name":"user1",
        "age":10,
    },
    {
        "name":"user2",
        "age":20,
    },
    {
        "name":"user3",
        "age":30,
    },
    {
        "name":"user4",
        "age":40,
    },
    {
        "name":"user5",
        "age":50,
    }
    ])

```

# search from collection

```c
    db.collection_name.find({})
    or use pretty for structured way
    db.collection_name.find({}).pretty()

    eg.

    select where name = 'abc'
    db.user.find({
        "name":"user1"
    })

    select value greater than equal 20, less than equal 40 and not equal 30
    db.user.find({
        "age":{$gte:20,$lte:40,$ne:30}
    })

     select value equal 20 or equal 40 or name equal user5
    db.user.find({
        $or:[
            {"age":20},
            {"age":40},
            {"name":"user5"}
            ]
    })

    we can limit the number of field by passing second argument in the find function eg.
    select value greater than equal 20, less than equal 40 and not equal 30
    db.user.find({
        "age":{$gte:20,$lte:40,$ne:30}
    },{"age":1,"_id":0})
```

# update the document

```c
    db.collectio_name.update({})

    use $set otherwise complete document will replace with updated value
    eg.
    db.user.update({
        "age":50,
    },{
        $set:{"age":60}
    })

    to update multiple documents use third parameter as ({multi:true})

    save method will replace current document with new document syntax same as update
```

# delete document

```c
    db.collection_name.remove({})

    eg.
    db.user.remove({"name":"user1"})
    if you want to delete jsut one record use 1 in parameter
    db.user.remove({"name":"user1"},1)

```

# limit the records

```c
    db.collection_name.find().limit(number)

    eg.

    db.user.find().limit(3)
```

# skip the record

```c
    db.collection_name.skip(number)

    eg.
    db.user.find().skip(2)
```

# sort the record

```c
    db.collection_name.sor()

    eg.
    1 for ascending order
    db.user.find().sort({"name":1})

    -1 for descending order
    db.user.find().sort({"name":-1})
```

# aggregation in mongo

```c
    db.collection_name.aggreagate({})

    eg.

    db.user.aggregate([{$group:{_id:"$name"}}])
```
