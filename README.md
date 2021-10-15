# Redis

Redis is an open source, in-memory data structure store, used as a database, cache, and message broker. Redis provides data structures such as strings, hashes, lists, sets, sorted sets with range queries, bitmaps, hyperloglogs, geospatial indexes, and streams.

To use redis, like any other database, you need to have it installed on your machine.

After you installed the redis server, you should start it (if not running it as a service). To do that run `redis-server` command in the terminal below before continuing to next steps of the tutorial.

```bash|{type: 'terminal'}
```

Then you can use a redis client to connect to the redis server. Since we are using Node.js, we will use the [`redis`](https://www.npmjs.com/package/redis) npm package. To add redis as a dependency in your npm module, run:

```
npm install redis
```

Once you have installed the redis client, you can use it in your code like this:

```js
const redis = require("redis");
const client = redis.createClient();
```

Once you have initialized the client, you can use it to set and retrieve keys from redis server. Run the code below to set a `greeting` to `Hello CSC342` and then retrieve the value you set ▶️

```js | {type: 'script'}
const redis = require("redis");
const client = redis.createClient();

client.on("error", function(error) {
  console.error(error);
});

client.set("greeting", "Hello CSC342", redis.print);
client.get("greeting", redis.print);
```


Redis also provides a command line utility called `redis-cli` that can be used to send commands to redis. Here is a live `redis-cli` session, can you send a command below to retrieve the value that we set for `greeting` key in the code above?

```| {type: 'terminal', 'command': 'redis-cli'}
```

Hint: [see here](https://redis.io/topics/quickstart#check-if-redis-is-working).
