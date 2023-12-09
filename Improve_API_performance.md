# 5 Ways to Improve API Performance


1. Pagination

2. Asynchronous Logging
    - synchronous logging writes to the disk for every call and slowes down our response.
    - Using async logging
      - we can seperate our logging to another thread from main call. So response time will be less.
      - Also not every log will be written directly to the disk.
      - Each log will be pushed into a memory buffer and then written onto the disk after reaching a reasonable size.
  
3. Caching
4. Payload Compression
   - requests and response can be  compressed using gzip.

5. Connection pool
   - Opening/Closing a connection to db cost computing resources.
   - So rather than a opening a request every time, we keep a certain number of connections open(called connection pool).
   - We pass the incoming db operations b/w these connections in connection pool.

   - Keeping the connections open is also Costly.
   - Going for the Choice of Connection pool or not completely depends on how many requests we get and how regularly our application interacts with db.
   - Sizing your connection pool depends on 
     - Cost to keep the Connection pool open    vs  cost to Open/Close those connections.

