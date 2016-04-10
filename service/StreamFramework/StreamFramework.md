# Notes

<pre>
<code>
(1) How to store activities?

Good choice:
Add a field used to perform aggregation (eg. object category)
You want to keep every piece of information needed to work with activities in Stream Framework (eg. avoid database lookups)
Bad choice:
The data stored in the activity gets updated
The data requires lot of storage

(2) Compare notification and activity system?

Building a scalable notification system is almost entirely identical to building an activity feed. From the user’s perspective the functionality is pretty different. A notification system commonly shows activity related to your account. Whereas an activity stream shows activity by the people you follow. Examples of Fashiolista’s notification system and Facebook’s system are shown below. Fashiolista’s system is running on Stream Framework.
Notification: xxx liked your post
Activity: xxx post something, you post something (you follow yourself by default)

(3) Stream Framework Design

a database
b push/pull
c stream framework
https://stream-framework.readthedocs.org/en/latest/design.html

(4) Activities are stored on Stream Framework trying to maximise the benefits of the storage backend used.
    
When using the redis backend Stream Framework will keep data denormalized; activities are stored in a special storage (activity storage) and user feeds only keeps a reference (activity_id / serialization_id). This allow Stream Framework to keep the (expensive) memory usage as low as possible.
When using Cassandra as storage Stream Framework will denormalize activities; there is not an activity storage but instead every user feed will keep the complete activity. Doing so allow Stream Framework to minimise the amount of Cassandra nodes to query when retrieving data or writing to feeds.
In both storages activities are always stored in feeds sorted by their creation time (aka Activity.serialization_id).

(5) Prioritise fanouts
    
Stream Framework partition fanout tasks in two priority groups. Fanouts with different priorities do exactly the same operations (adding/removing activities from/to a feed) the substantial difference is that they get published to different queues for processing. Going back to our pinterest example app, you can use priorities to associate more resources to fanouts that target active users and send the ones for inactive users to a different cluster of workers. This also make it easier and cheaper to keep active users’ feeds updated during activity spikes because you dont need to scale up capacity less often.
Stream Framework manager is the best place to implement your high/low priority fanouts, in fact the get_follower_ids method is required to return the feed ids grouped by priority.
https://stream-framework.readthedocs.org/en/latest/background_tasks.html
    
</code>
</pre>

# Reference
 - https://stream-framework.readthedocs.org/en/latest/
 - [Build a scalable feed using Stream-Framework and Django (not about how to set up)](http://www.mellowmorning.com/2013/10/18/scalable-pinterest-tutorial-feedly-redis/)
 - [Activities' serialization ids are not always unique for unique activities](https://github.com/tschellenbach/Stream-Framework/issues/58)