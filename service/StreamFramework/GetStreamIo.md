# Understanding

 - feed
     - A feed is something like a queue, in the [getting started tutorial](http://getstream.io/get_started/#flat_feed), "user" is a flat feed. 
     - A feed group is a collection of feeds, which makes it easier to config all grouped feeds.
     - It would make more sense to name each feed group literally, for example, timeline, user, and not to use feed TYPE name.
     - All activities in a feed can be endurable, but we do not want to store too much history data according to the official explaination (It's normal to have millions of feeds per feed class. Every individual feed however will contain no more than this number of activities.). So in my understanding, it should be better to have one feed for a user (named by ${id}), as for the aggregated result, it is grouped by aggregated key (The aggregation rule uses the Jinja2 template syntax. The feed will group all activities which have the same key as determined by the aggregation format). To see detailed activities, use ```juleAggregatedFeed.get({'limit': 3}).then(callback2);```.
 - follow
     - Following has no sequense, which means once you follow someone, all activities will be accessable, even the ones added before following.
     - After deleting a followee's activity, follower's related activity will also be deleted.
     - Use "unfollow" to stop a following. After unfollowing, all irrelevant activities will be deleted automatically.
     - All followed activities is add into the follower's feed, which means less querying time during reading.
 - Token: a token is only used on client side (which means it can be generated freely on server side), however, how does getStream.io know whether a api call is from client or server (checked in nodejs package?)?

# How to use nodejs client high-level getstream-node

 <pre>
 <code>
 Copy getstream.js config file from node_modules/getstream-node into the root directory of your application
 
 Login with Github on getstream.io and edit the configuration values for apiKey, apiSecret and apiAppId in your getstream.js file (you can find them in the dashboard).
 
 Make sure you require the getstream-node early on in your application (eg. in app.js)
 </code>
 </pre>

# Notes

 - Flat feeds are the default feed type. Note that you can only follow flat feeds
 - The "TO" field allows you to specify a list of feeds to which the activity should be copied. You can think of it as the CC functionality of email. This is useful when you want to support @mentions and notify users
 - Batch all the database queries. Never run N queries for N items in the feed
 - BATCH ACTIVITY ADD Allows you to add a single activity to multiple feeds with just 1 API request. Note that this batch method doesn't trigger a fanout. So the followers of these feeds won't receive an update
 - When importing both activities and follows, start with the activities. Your import will run substantially faster
 
# Reference

 - http://getstream.io/docs/
 - https://github.com/GetStream/stream-node
 - https://github.com/GetStream/stream-js