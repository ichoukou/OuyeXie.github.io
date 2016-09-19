# Steps

 - Scope the problem: Don't make assumptions; Ask questions; Understand the constraints and use cases.
 - Sketch up an abstract design that illustrates the basic components of the system and the relationships between them.
 - Think about the bottlenecks these components face when the system scales.
 - Address these bottlenecks by using the fundamentals principles of scalable system design.
 
 - Don't skip steps, don't make assumptions, start broad and go deep when asked.
 - Second, keep in mind that system design questions serve as an idea exchange platform. Be prepared for discussions about tradeoffs, about pros and cons. Be prepared to give alternatives, to ask questions, to identify and solve bottlenecks, to go broad or deep depending on your interviewer's preferences.
 
# Concepts

 - Vertical scaling
 - Horizontal scaling
 - Caching
 - Load balancing
 - Database replication
 - Database partitioning
 - Using NoSQL instead of scaling a relational database
 - Being asynchronous
 
# Readings

 - [scalability-for-dummies-part-1-clones](http://www.lecloud.net/post/7295452622/scalability-for-dummies-part-1-clones)
    - I have 4 parts
 - [database sharding](http://highscalability.com/blog/2009/8/6/an-unorthodox-approach-to-database-design-the-coming-of-the.html)
    - disadvantages
        - Rebalancing data
        - Joining data from multiple shards. 
        - How do you partition your data in shards? What data do you put in which shard? Where do comments go? Should all user data really go together, or just their profile data? Should a user's media, IMs, friends lists, etc go somewhere else? Unfortunately there are no easy answer to these questions.
        - Less leverage. 
        - Implementing shards is not well supported
 
# Techniques
    
 - HAProxy, nginx, memcached, Redis, Lucene, NodeJS
 - RabbitMQ (one of many systems which help to implement async processing)
    - The basic idea is to have a queue of tasks or jobs that a worker can process
 - Munin (monitoring, graph metrics across all of our system)
 - mdadm (software RAID)
 - vmtouch (managing what data is in memory)
 - [AWS tools](https://www.airpair.com/aws/posts/building-a-scalable-web-app-on-amazon-web-services-p1)
 - Capistrano (make sure that a code change is sent to all your servers without one server still serving old code)
 
# Examples

 - Design a URL shortening service like bit.ly.
    - https://www.zhihu.com/question/29270034
 - How would you implement the Google search?
    - mapreduce pagerank (hubs and authority (hits)) bm25
    - http://programmers.stackexchange.com/questions/38324/how-would-you-implement-google-search
 - Design a client-server application which allows people to play chess with one another.
    - http://stackoverflow.com/questions/14846727/java-network-game-design
    - https://www.careercup.com/question?id=5648661084110848
 - How would you store the relations in a social network like Facebook and implement a feature where one user receives notifications when their friends like the same things as they do?
    - [stream framwork] (https://stream-framework.readthedocs.io/en/latest/)
 
 - Twitter: real time feed of the tweets by the people you’re following
 - Google: instantly returning the pages matching any search query (Search); Storing and serving massive amounts of video data (YouTube); Aggregating the world’s news by topic (Google news)
 - Facebook: serving massive amounts of photos
 
 - Recommendation
    - https://help.aliyun.com/document_detail/30369.html?spm=5176.doc30371.6.101.vXZNPV
        - a/b test
        - cloud watch
 - [聊天室服务分析设计](http://www.cnblogs.com/yjf512/archive/2013/03/05/2943783.html)
 - [node.js聊天室架构设计  ](http://snoopyxdy.blog.163.com/blog/static/601174402011102110415398/)
        
 - [Examples of Scalable Architectures](http://www.hiredintech.com/system-design/sample-architectures/)
    - [instagram](http://instagram-engineering.tumblr.com/post/13649370142/what-powers-instagram-hundreds-of-instances)
        - [Sharding & IDs at Instagram](http://instagram-engineering.tumblr.com/post/10853187575/sharding-ids-at-instagram)
        - madam
        - vmtouch
        - All of our PostgreSQL instances run in a master-replica setup using Streaming Replication
        - We use XFS as our file system, which lets us freeze & unfreeze the RAID arrays when snapshotting
    - [justin.tv](http://highscalability.com/blog/2010/3/16/justintvs-live-video-broadcasting-architecture.html)
        - Usher, custom business logic server for playing video streams.
            - Usher calculates how many servers to send each stream in order to ensure there's always optimal load.
        - The number of streams is sampled constantly. If a certain stream has a high velocity of new incoming viewers then that stream is replicated to a few other servers. And the process repeats, building up a tree shape, potentially including all the servers in the network.
        - Flash is used to be as accessible as possible, which uses the RTMP protocol. 
        - The point of having multiple datacenters is not for redundancy, it's to be as close as possible to all the major peering exchanges 
        - While video streams are not streamed from disk, video is archived to disk. The origin server, the server picked to handle an incoming stream, records a stream on local disk, that recording is then uploaded to long term storage.
        - The client participates in the load balancing logic, which is one of the reasons they require the use of their own player.
        - Added real-time transcoding which can take in any format of stream,
        - challenge
            - Live video can't hiccup, which means you can't oversubscribe bandwidth. 
            - Graceful overflow to a CDN when they do overflow. 
            - Building systems that appear to have 100% up time yet have the ability to take machines out of production slowly and gradually for maintenance. 
    - [YouTube Architecture](http://highscalability.com/youtube-architecture)
        - web server (cache)
            - NetScalar is used for load balancing and caching static content.
            - Some pre-generated cached HTML for expensive to render blocks.
            - Row level caching in the database.
            - Fully formed Python objects are cached.
            - Some data are calculated and sent to each application so the values are cached in local memory.
        - video server (cache)
            - Most popular content is moved to a CDN (content delivery network)
            - Caching doesn't do a lot of good in this scenario, so spending money on more cache may not make sense. This is a very interesting point. If you have a long tail product caching won't always be your performance savior. 
        - Serving Thumbnails
            - problems
                - Lots of disk seeks and problems with inode caches and page caches at OS level.
                - Ran into per directory file limit. Ext3 in particular. 
                - A high number of requests/sec as web pages can display 60 thumbnails on page.
                - Under such high loads Apache performed badly.
                - Used squid (reverse proxy) in front of Apache. This worked for a while, but as load increased performance eventually decreased. Went from 300 requests/second to 20.
                - Tried using lighttpd but with a single threaded it stalled. Run into problems with multiprocesses mode because they would each keep a separate cache.
                - With so many images setting up a new machine took over 24 hours.
                - Rebooting machine took 6-10 hours for cache to warm up to not go to disk.
            - To solve all their problems they started using Google's BigTable, a distributed data store
        - Databases
            - The Early Years
                - Use MySQL to store meta data like users, tags, and descriptions.
                - Served data off a monolithic RAID 10 Volume with 10 disks. 
                - They went through a common evolution: single server, went to a single master with multiple read slaves, then partitioned the database, and then settled on a sharding approach.
        - Data Center Strategy
            - Videos come out of any data center. Not closest match or anything. If a video is popular enough it will move into the CDN.
            - Images are replicated to different data centers using BigTable
        - Lessons Learned
        -    Constant iteration on bottlenecks
        - Have a good cross discipline team that understands the whole system and what's underneath the system.
# References
 - http://www.hiredintech.com/system-design/