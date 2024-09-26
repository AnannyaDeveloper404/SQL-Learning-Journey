# Relational Databases & SQL

`inserting data into table`:Command below:

```sql
    mysql> insert into offices (officeCode,city,phone,addressLine1,country,postalCode
    ,territory) values('aaa','Kolkata','1234567890','xyz','India','700000','Asia');
    Query OK, 1 row affected (0.06 sec)
```

`Viewing data in the table`:Command below:

```sql
    mysql> select officeCode,city from offices;
    +------------+---------+
    | officeCode | city    |
    +------------+---------+
    | aaa        | Kolkata |
    +------------+---------+
    1 row in set (0.00 sec)
```
