# PostgreSQL for Analytics

PostgreSQL is a great option for data analytics because of its reliability and data integrity. It also has many features and customisation, making it adaptable to diverse needs. PostgreSQL also features Multi-Version Concurrency Control (MVCC) which enables high transaction rates and concurrent access to data without traditional locking mechanisms. 

JOIN operation in PSQL is a powerful command especially in analysing relational data because we can understand the relationships across different tables rather than looking at each table individually and inferring in this way. 

Window functions compute per-row metrics without collapsing rows. It allows rows to retain their individual identities while still performing calculations on a defined "window" of related rows, unlike using GROUP BY. Below shows an example of using a window function. 

<img width="792" height="900" alt="Screenshot 2025-08-21 at 22 39 44" src="https://github.com/user-attachments/assets/7e3ee3d1-a61c-4f23-9907-dfd97e42c42a" />

Query optimisation involves enhancing the efficiency of SQL queries to improve database performance, that is, minimising resource consumption (CPU, memory, etc) and reduce execution time. By adding EXPLAIN ANALYZE, not only do we execute the query itself but also provides execution stats such as the plan, timings, and row counts so we can identify bottlenecks and determine if there's a more efficient query. Below shows an output when using EXPLAIN ANALYZE. 

<img width="1054" height="397" alt="Screenshot 2025-08-21 at 22 35 31" src="https://github.com/user-attachments/assets/7c97aac9-9d97-438b-a68b-085f10d0f7ad" />
