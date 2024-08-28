## why we use Schema in database
 - In database management, a schema defines the structure of the database, including the tables, fields, relationships, and constraints. It serves as a blueprint for organizing 
   and managing the data. Understanding and effectively using schemas is crucial for designing efficient, maintainable, and scalable databases.
## Basic Requirement for creating Schema
 - 1. SQL Server Instance: You'll need an instance of Microsoft SQL Server running on your system or network.

 - **2. Database:** Within the SQL Server instance, you'll need a database to house the schema. If a database doesn't exist, you can create one using the CREATE DATABASE command.

 - **3. Permissions:** The user account you're using must have sufficient permissions to create schemas within the specified database. Typically, the CREATE SCHEMA permission is required.
      
  - **4. Schema Name:** You'll need to choose a unique name for the schema. The name should follow SQL Server naming conventions and avoid reserved keywords.

  - **5. Schema Objects:** Once the schema is created, we can populate it with various schema objects, such as tables, views, stored procedures, functions, and triggers. These objects will be associated with the schema and can be accessed using their qualified names (schema_name.object_name).
 ##  Trigger 
 
- Triggers are automatically executed in response to specific events like insertions, updates, or deletions on a table or view.

 #### Types of Triggers

- **BEFORE Trigger**: Executes before an insert, update, or delete operation is performed. This allows you to modify the data or prevent the operation from happening.
- **AFTER Trigger**: Executes after an insert, update, or delete operation has been performed. It’s often used for logging or other actions that need to occur after the operation is completed.
- **INSTEAD OF Trigger**: Executes in place of the usual operation (insert, update, or delete). This type of trigger can replace the standard operation with a different one.

#### Usage Scenarios

- **Data Validation**: Ensure data meets certain criteria before being inserted or updated.
- **Audit Logging**: Automatically record changes to data for auditing purposes.
- **Maintaining Derived Data**: Update related tables or columns automatically when data changes.

#### Example of Creating Triggers

##### BEFORE INSERT Trigger

Suppose you have a table `Employees` and you want to ensure that no employee's salary can be below a certain threshold before inserting a new record.

```sql
CREATE TRIGGER check_salary_before_insert
BEFORE INSERT ON Employees
FOR EACH ROW
BEGIN
  IF NEW.salary < 30000 THEN
    SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'Salary must be at least 30,000';
  END IF;
END;
```
       
