## Why is it useful to query databases directly from Python instead of using a SQL client?

Querying databases directly from Python instead of an SQL client offers several advantages, to name a few:
- Python has a rich ecosystem of libraries that allow for powerful data manipulation
- Python allows for custom logic and complex algorithms that might be difficult to achieve with an SQL client
- Python has reliable error handling mechanisms that can handle database connection issues, query errors, etc.

## How does psycopg differ from psycopg2?

psycopg is the modern, redesigned version of postgreSQL adapter for Python, while psycopg2 is actually the predecessor.  There are a couple of differences between these two:
- psycopg2 requires manual management of connections and cursors; psycopg leverages python's context managers for automatic connection
- psycopg demonstrates better performance, especially involving large data retrieval and array processing
- psycopg2 no longer receives new feature development; psycopg supports newer PSQL features

## How can pandas help with post-query data transformation?

The pandas module can execute the following which can help with post-query data transformation:
- Data cleaning: renaming columns, drop/fill nulls
- Filtering
- Aggregations
- Joins
- Formulate time series
- Create quick outputs along with matplotlib

## How could this integration be used to generate automated reports for Focus Bear?

- Query: use psycopg to pull observations
- Transform: use pandas to aggregate, compute KPIs, create charts and presentable reports
- Publish: We can save the generated outputs for reports
- Distribute: We can even distribute these outputs and reports to the rest of the team or the relevant parties through python.
