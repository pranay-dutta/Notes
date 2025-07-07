
1. Relational Database
2. Non Relational Database

| Relational DB                                                          | Non - Relational DB                                                                                           |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| RDMBS - (Relational Database Management System)<br>or SQL Database<br> | NoSQL Databases                                                                                               |
| Example: **MYSQL, Oracle, PostgreSQL**<br>                             | Example: Cassendra, Amazon Dynamo DB, etc<br>                                                                 |
| Represented and store data in **tables & rows**                        | Grouped into **4** groups<br><br>**Graph Stores<br>Key-value Stores<br>Column Stores<br>Document Stores**<br> |
| Can perform **JOIN** operations using **SQL** on different tables      | **JOIN** operations not supports                                                                              |

🤔 But Which one to use ?

- For most developers - **Relational DB** works fine
- But there are many cases in which Relational DB is **not suitable**

😐 When to think about non-relational DB ?
- Your application requires **super low latency.**
- When your data is **unstructured**.
- You only need to **serialized** and **deserialize** data (JSON, XML, YAML, etc.)
- When you need to store **MASSIVE** amount of data.
 - You don't need to maintain **data type**

