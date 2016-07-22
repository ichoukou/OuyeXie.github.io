 - neo4j.config
    - memory
        - # The amount of memory to use for mapping the store files, in bytes (or
          # kilobytes with the 'k' suffix, megabytes with 'm' and gigabytes with 'g').
          # If Neo4j is running on a dedicated server, then it is generally recommended
          # to leave about 2-4 gigabytes for the operating system, give the JVM enough
          # heap to hold all your transaction state and query context, and then leave the
          # rest for the page cache.
          # The default page cache memory assumes the machine is dedicated to running
          # Neo4j, and is heuristically set to 50% of RAM minus the max Java heap size.
          #dbms.memory.pagecache.size=10g
    - thread
        - # Number of Neo4j worker threads.
          #dbms.threads.worker_count=
 - neo4j-wrapper.config
    - JVM
        - # Java Heap Size: by default the Java heap size is dynamically
          # calculated based on available system resources.
          # Uncomment these lines to set specific initial and maximum
          # heap size in MB.
          #dbms.memory.heap.initial_size=512
          #dbms.memory.heap.max_size=512