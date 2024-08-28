# why we use Schema in database
 - In database management, a schema defines the structure of the database, including the tables, fields, relationships, and constraints. It serves as a blueprint for organizing 
   and managing the data. Understanding and effectively using schemas is crucial for designing efficient, maintainable, and scalable databases.
# Basic Requirement for creating Schema
 - 1. SQL Server Instance: You'll need an instance of Microsoft SQL Server running on your system or network.

 - **2. Database:** Within the SQL Server instance, you'll need a database to house the schema. If a database doesn't exist, you can create one using the CREATE DATABASE command.

 - **3. Permissions:** The user account you're using must have sufficient permissions to create schemas within the specified database. Typically, the CREATE SCHEMA permission is required.
      
  - **4. Schema Name:** You'll need to choose a unique name for the schema. The name should follow SQL Server naming conventions and avoid reserved keywords.

  - **5. Schema Objects:** Once the schema is created, we can populate it with various schema objects, such as tables, views, stored procedures, functions, and triggers. These objects will be associated with the schema and can be accessed using their qualified names (schema_name.object_name).
       
