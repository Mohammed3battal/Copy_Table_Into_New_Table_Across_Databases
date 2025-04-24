## Script: Copy_Table_Into_New_Table_Across_Databases.sql

**Description**:
This script copies the contents of a table from one database into a **new table** in another database using `SELECT INTO`. The destination table is created automatically with the same structure and data as the source table.

---

> 🔁 Replace:
> - `DATABASE_NAME` → destination database
> - `NEW_TABLE_NAME` → name of the new table to be created
> - `SOURCE_DATABASE_NAME` → database where the original table resides
> - `TABLE_NAME` → source table name

---

### ✅ Use Case:
- Clone tables between databases quickly
- Create archive or backup copies of tables
- Prepare a working table for testing or analysis
- Copy production data into a development or staging environment

---

### ⚠️ Notes:
- The destination table **must not already exist** — otherwise, you'll get an error.
- `SELECT INTO` also copies **column definitions and data types**, but **not** indexes, keys, constraints, or triggers.
- Make sure you have permission to read from the source and write to the destination database.

---

### 💡 Tip:
To include only specific columns or rows:
```sql
SELECT col1, col2
INTO TargetDB.dbo.NewTable
FROM SourceDB.dbo.OldTable
WHERE condition;
```


