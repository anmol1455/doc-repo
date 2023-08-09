# Query Optimization

Enhance query performance by refining SQL queries, utilizing appropriate JOINs, optimizing WHERE clauses, and leveraging query execution plans. These techniques help minimize processing time and resource utilization, resulting in more efficient data retrieval.

## Inefficient Query Example

Consider the following query that involves JOINs and a WHERE clause:

```sql
SELECT n.`type`, n.conid, n.`user`, n.`by`, n.`date`, n.amt, m.url AS `url`, u.dp, u.uname AS `other_user`
FROM `notifications` n
LEFT JOIN `memes` m ON n.conid = m.mid
LEFT JOIN `users` u ON n.`user` = u.id
WHERE n.`by` = :user AND n.`type` IN (1, 2, 9)
ORDER BY n.nid DESC
LIMIT :skip, :product_per_page;
```
We can optimize such queries by dividing them into multiple queries and making them more efficient and fast.