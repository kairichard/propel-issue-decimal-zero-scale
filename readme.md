Propel issue #

When working with a legacy database that has field like the follwing

```mysql
  `field_name` decimal(11,0) DEFAULT NULL
```

propel generates a wrong schema.xml ommitting the scale of the field
This can be reporduced using `make test` where a second migration will be created
because the schema does not match with the generated migration.


If you run into trouble on OSX:
  Unable to open PDO connection [wrapped: SQLSTATE[HY000] [2002] No such file or directory]
  On Terminal, execute these commands

  sudo mkdir /var/mysql/
  sudo ln -s /private/tmp/mysql.sock /var/mysql/mysql.sock