# Prague PostgreSQL Meetup: September Edition

https://www.meetup.com/prague-postgresql-meetup/events/308864510/

Talk: 

PostgreSQL Connections Memory Usage on Linux: How Much, Why, and When?

This talk explores the memory usage of PostgreSQL connections on Debian/Ubuntu running on x86–64 architecture. It gives an overview of memory management concepts, explaining key metrics like virtual, resident, and proportional memory sizes. It also covers various Linux tools for displaying memory usage.
The second part presents practical measurements of PostgreSQL memory usage, based on data from /proc/PID/smaps and /proc/PID/pagemap. It explains why RSS numbers for PostgreSQL connections in top command appear so large after query execution and demonstrates that the actual unique memory usage is only a few dozen megabytes.
Finally, the talk also reveals where work_mem is “hidden” in these statistics, visualizes memory usage during query processing with multiple plots, and discusses queries that exceed the work_mem setting multiple times. It also demonstrates the total memory usage when a query utilizes parallel workers.

Key Takeaways:
- The large RSS values in long-running sessions mostly come from linked shared_buffers
- A newly created connection consumes only up to 10 MB of physical memory, independent of the work_mem setting
- Additional memory is allocated and later released as queries execute
- Work_mem is a “soft maximum limit” — it may not be fully used, but it can also be exceeded
