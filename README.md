# Create-ERD-MySQL-Workbench
Tutorial for creating ERD model in MySQL Workbench.

## 1. Create ERD model
**2 common ways to create ERD model:**
- **First way:** Create tables before (using SQL statements) then create ERD (Database → Reverse Engineer).
- **Second way:** Create empty databases then create ERD (Database → Reverse Engineer), you can create tables and their relationship. After that, update all tables and relationships into databases (Database → Forward Engineer).

*Note:* Prefer to use the Second way. 

**Steps when use second way:**
- **Step1:** Create empty database, then create ERD (`Databases → Reverse Engineer`).
- **Step2:** Create tables with all columns except **Foriegn Keys (FK)**. 
- **Step3:** Create relationship between tables (This creates automatically **FK**).
- **Step4:** Update table in databases (`Databases → Forward Engineer`)

## 2. Example to create ERD model

**Requirement:** Create hospital ERD model base on the figure below and insert the data via `hopsital_insert_data.sql`.
![img](https://drive.google.com/uc?export=view&id=1Hdwwmpb8O4ABdp_RTTjjcX_H0q8F_ZNm)

**Follow step-by-step:**

*1. Create empty databases:* Two ways.
- Use SQL statement: `CREATE DATABASES hospital`.
- Create schema in MySQL Workbench: click `Create a new schema in the connected server` then pass Schema Name `hospital` and click `Apply`.

*2. Connected ERD workspace with database:*
- `Databases → Reverse Engineer` and choose the databases `hospital`.

*3. Create tables in ERD workspace:*
- Create all table like the figure above without **FK** - any the red color symbol at the left of column name is **FK** with **strong relationship** or **Weak relationship** with **Null** or **Not Null**.

*4. Create relationship between tables:*
- When you create relationship, that will create automatically **FK** in tables (you should rename collumns the same the figure).

*5. Change the order of columns in tables:*
- You should change the order of columns in table cause the next step we will insert data into those tables with `hospital_insert_data.sql`. In this SQL file, we use `INSERT INTO <table_name> VALUES(<values>)`. `<values>` are inserted must corresponding to the order of columns in tables.

*6. Update tables in database:*
- `Databases → Forward Engineer`.

*7. Insert serveral data in databases:*
- Open `hospital_insert_data.sql` and run. If get errors mean somethings wrong in you ERD. Check carefully (name of table, columns, order of columns, ....).




