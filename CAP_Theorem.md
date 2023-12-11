# CAP Theorem


Cap theorem states that a distributed system can't provide more than two of theese guarantees simultaneously.

1. Consistency
   - all reads recieve the most recent write or an error
   - all clients see same data at the same time no matter which node they connect to
   - ex : for a bank system, consitency is more important than availability (showing correct information is imp).
2. Availability
    - all reads gives data, but it might not be the recent one
    - ex : In a ecommerce application, availability of products is important.
3. Partition tolerance 
    - system continues to operate despite network failures(a communication failure between any 2 nodes in the system - also called network partition).


