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

## SQL WHERE Clause Operators Cheat Sheet

#### 1. `=` (Equal)

- Returns rows where the column's value matches the specified value exactly.

  **Example**:

  ```sql
  SELECT * FROM `employees` WHERE `jobTitle` = 'Sales Rep';
  ```

#### 2. `>` (Greater Than)

- Returns rows where a column's value is greater than the specified value.

  **Example**:

  ```sql
  SELECT * FROM `employees` WHERE `salary` > 50000;
  ```

#### 3. `<` (Less Than)

- Returns rows where a column's value is less than the specified value.

  **Example**:

  ```sql
  SELECT * FROM `employees` WHERE `age` < 30;
  ```

#### 4. `>=` (Greater Than or Equal)

- Returns rows where a column's value is greater than or equal to the specified value.

  **Example**:

  ```sql
  SELECT * FROM `employees` WHERE `salary` >= 60000;
  ```

#### 5. `<=` (Less Than or Equal)

- Returns rows where a column's value is less than or equal to the specified value.

  **Example**:

  ```sql
  SELECT * FROM `employees` WHERE `age` <= 40;
  ```

#### 6. `<>` or `!=` (Not Equal)

- Returns rows where a column's value is not equal to the specified value.

  **Example**:

  ```sql
  SELECT * FROM `employees` WHERE `jobTitle` != 'Manager';
  ```

#### 7. `BETWEEN` (Range)

- Filters rows where a column's value is between two values (inclusive).

  **Example**:

  ```sql
  SELECT * FROM `employees` WHERE `salary` BETWEEN 40000 AND 60000;
  ```

#### 8. `LIKE` (Pattern Matching)

- Used for pattern matching. `%` represents any number of characters; `_` represents a single character.

  **Example**:

  ```sql
  SELECT * FROM `employees` WHERE `lastName` LIKE 'S%';
  ```

#### 9. `IN` (Set)

- Checks if a value exists within a list of values.

  **Example**:

  ```sql
  SELECT * FROM `employees` WHERE `department` IN ('Sales', 'Marketing', 'HR');
  ```

### SQL ORDER BY, LIMIT, and ALTER TABLE Cheat Sheet

#### 1. `ORDER BY` (Sorting)

- Used to sort the result set by one or more columns, either in ascending (`ASC`) or descending (`DESC`) order.

  **Example**:

  ```sql
  SELECT * FROM `employees` ORDER BY `lastName` ASC;
  ```

  **Example (Multiple columns)**:

  ```sql
  SELECT * FROM `employees` ORDER BY `department`, `salary` DESC;
  ```

#### 2. `LIMIT` (Limiting Rows)

- Limits the number of rows returned by the query. Useful for fetching a specific subset of rows.

  **Example**:

  ```sql
  SELECT * FROM `employees` ORDER BY `salary` DESC LIMIT 5;
  ```

  - This example returns the top 5 highest-paid employees.

---

#### Modifying Table Structure (Using `ALTER TABLE`)

#### 1. Adding a New Column

- Adds a new column to an existing table.

  **Syntax**:

  ```sql
  ALTER TABLE `table_name` ADD `column_name` datatype;
  ```

  **Example**:

  ```sql
  ALTER TABLE `employees` ADD `dateOfJoining` DATE;
  ```

#### 2. Removing a Column

- Removes a column from an existing table.

  **Syntax**:

  ```sql
  ALTER TABLE `table_name` DROP COLUMN `column_name`;
  ```

  **Example**:

  ```sql
  ALTER TABLE `employees` DROP COLUMN `middleName`;
  ```

#### 3. Changing the Data Type of a Column

- Modifies the data type of an existing column.

  **Syntax**:

  ```sql
  ALTER TABLE `table_name` MODIFY COLUMN `column_name` datatype;
  ```

  **Example**:

  ```sql
  ALTER TABLE `employees` MODIFY COLUMN `salary` DECIMAL(10, 2);
  ```

#### 4. Renaming a Column

- Renames an existing column to a new name.

  **Syntax**:

  ```sql
  ALTER TABLE `table_name` RENAME COLUMN `old_column_name` TO `new_column_name`;
  ```

  **Example**:

  ```sql
  ALTER TABLE `employees` RENAME COLUMN `surname` TO `lastName`;
  ```

## SQL Aggregation, Grouping, and Aliases Cheat Sheet

### Aggregation Functions

- **COUNT()**  
  Returns the number of rows matching the condition.

```sql
  SELECT COUNT(column_name) FROM table_name;
```

- **AVG()**
  Returns the average value of a numeric column.

```sql
  SELECT AVG(column_name) FROM table_name;
```

- **SUM()**
  Returns the total sum of a numeric column.

```sql
  SELECT SUM(column_name) FROM table_name;
```

- **MIN()**
  Returns the smallest value in a column.

```sql
  SELECT MIN(column_name) FROM table_name;
```

- **MAX()**
  Returns the largest value in a column.

```sql
  SELECT MAX(column_name) FROM table_name;
```

- **GROUP BY**
  Used to group rows that have the same values into summary rows.

```sql
  SELECT column_name, COUNT(*)
  FROM table_name
  GROUP BY column_name;
```

- **HAVING**
  Filter groups based on a condition

```sql
  SELECT column_name, COUNT(*)
  FROM table_name
  GROUP BY column_name
  HAVING COUNT(*) > 5;

```

- **Aliases**
  Use aliases to rename a column or table temporarily for better readability.

```sql
  SELECT column_name AS alias_name FROM table_name;

```

- **OFFSET**
  OFFSET skips a specific number of rows before starting to return rows from the query. It is often used with the LIMIT clause.

```sql
  SELECT column_name
  FROM table_name
  LIMIT 10 OFFSET 5;
```
