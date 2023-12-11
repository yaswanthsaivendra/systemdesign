# Caching

### Caching in different levels

1. client side
    - caching content in browser
2. DNS
3. Web Server
    - includes CDNs, Reverse Proxies, Web Accelerators, Key/Value Stores
    - ex : Amazon CloudFront, ElasticCahce for Redis & Memcached
4. Application
    - include Key/Value Stores, Local Caches
    - ex : Redis, Memcached
    - it keeps a cache on the application server, whenever a request is made for some resource, firstly cache will be checked, if not found, it will query data from some storage like database.
5. Database
    - reduce latency associated with db query requests
    - ex : database buffers, key/value data stores
6. other cahces
    - cpu cache
    - gpu cache
    - disk cache (OS cache)


### Cache Invalidation

If data is modified in database, it should be invalidated in cache. If not can cause inconsistency.

1. Write through cache
    - a write is confirmed as success only if writes to both DB and cache succeed.
    - pros : data consistency, fast retrieval(as reads from cache), robuts to system interruptions
    - cons : higher latency for write operations
2. Write around cache
    - writes directly to DB first, later DB can remove or update the data in cache.
    - pros : reduce write latency
    - Cons : however, it increases read latency in applications where immediate reads happen after a write(as we need to read from db).
3. Write back cache
    - write to cache first and write is confirmed as soon as write to cache is done.
    - Later cache writes to db asynchronously.
    - pros : really quick writes
    - cons : risking of losing data, in case of cache layer failure


### Cache Eviction Policies

1. FIFO - First In First Out
2. LIFO - Last In First Out
3. LRU  - Least Recently Used
4. MRU  - Most Recently Used
5. LFU  - Least Frequently Used
6. RR   - Random Replacement


### Others

#### Global Caches

#### distributed Caches
