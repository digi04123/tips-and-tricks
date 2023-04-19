# Redis

## Set

````py
### Create a set and add some elements:

redis_cli.sadd("myset", 10, 10, 20, 20, 30, 30)

### Check the total number of elements in a set:
redis_cli.scard("myset")

### Check all elements in a set:
redis_cli.smembers("myset")

### Check if an element exists in a set:
redis_cli.sismember("myset", 20)

### String type also works:
redis_cli.sismember("myset", 200)

### Iterate a set:
for elem in redis_cli.sscan_iter("myset"):
    print(elem)
    
### Get a random element from a set:
redis_cli.spop("myset")
````

## List
````py
redis_cli.lpush("mylist", 1, 2)

# Push elements to the tail of a list:
redis_cli.rpush("mylist", 10, 20)

# Check the total number of elements in a list:
redis_cli.llen("mylist")

# Check all elements in a list:
redis_cli.lrange("mylist", 0, -1)

# Check the list elements from index 1 to index 2 (2 is included):
redis_cli.lrange("mylist", 1, 2)

# Get the first element from head:
redis_cli.lpop("mylist")

# Get the last element from tail:
redis_cli.rpop("mylist")
````

## Hash
````py
# Create a hash and add a single field/value pair:
redis_cli.hset("myhash", "name", "John")

# Add more fields to the hash:
redis_cli.hset("myhash", items=["age", 30, "job", "developer"])

# Alternatively, we can use "mapping" to specify a dictionary, this would be recommended way:
redis_cli.hset("myhash", mapping={"name": "John", "age": 30, "job": "developer"})

# Check the total number of fields in a hash:
redis_cli.hlen("myhash")

# Get all fields of a hash:
redis_cli.hkeys("myhash")

# Get the value of a single field:
redis_cli.hget("myhash", "name")

# Get the values of multiple fields:
redis_cli.hmget("myhash", "name", "age")

# Check all fields and values of a hash:
redis_cli.hgetall("myhash")

# Check if a field exists in a hash:
redis_cli.hexists("myhash", "name")

redis_cli.hexists("myhash", "non-exist")

# Remove a field from a hash:
redis_cli.hdel("myhash", "name")
````

