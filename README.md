# MongoDB Installation with Mezzio#

## 1)	Prerequisites for the Integration
    - MongoDB Driver extension is required to connect with mongodb
    - MongoDB Compass

```sh 
MongoDB Connection details are as –
mongodb://<username>:<password>@localhost:27017/?authMechanism=DEFAULT&authSource=<dbname>
```

## 2)	Required composer Modules 
 ```sh
    $ composer require laminas/laminas-cache
    $ composer require mongodb/mongodb
    $ composer require laminas/laminas-cache-storage-adapter-ext-mongodb
 ```
## 3)	Configuration setup
   Mongo Configuration `config/autoload/cache.global.php` add in the last 
```sh 
/**
     * Mongodb coneection string 
     *  server   => 'mongodb://<username>:<password>@<hostname>:<port>',  
     *  database => database name   
     */
   'mongo'=> [      
        'server'=>'mongodb://root:Test#1123@mongo:27017',    
        'database'=>'admin'           
    ]
```
## 4)	Integration
Use the required namespace to use the mongoDb
//Required namespace for the mogoDB
```sh
use Laminas\Cache\Storage\Adapter\ExtMongoDb;
```

Check how to invoke class
```sh 
//$config has to pass as mentioned in the cache.global.php
$mongo= new ExtMongoDb($config);

$mongo->setItem("key","{TestKey:TestValue}");
echo $mongo->getItem("key"); 
```

`ExtMongoDb` class has multiple methods to fetch the data from mongo dB, you can explore the class file for this.












