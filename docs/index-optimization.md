# Index Optimization

Optimize query performance by implementing strategic indexes in database tables. This involves creating indexes on specific columns or combinations of columns to speed up data retrieval.

## Indexing Example

For example, consider a scenario where the `comments` table is very large and frequently queried based on the `uname` column. We can create an index on the `uname` column to improve search performance:

```sql
-- Create an index on the uname column of the comments table
CREATE INDEX idx_comments_uname ON comments(uname);
```
Additionally, for large tables with complex search patterns, consider creating indexes on combinations of columns to allow fast searching:

```sql
-- Create a composite index on columns (col1, col2) of a large_table
CREATE INDEX idx_large_table_col1_col2 ON large_table(col1, col2);
```
