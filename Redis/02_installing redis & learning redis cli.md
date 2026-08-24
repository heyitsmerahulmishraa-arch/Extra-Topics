- ✅ Install Redis
- ✅ Start the Redis server
- ✅ Connect using the Redis CLI
- ✅ Execute basic commands
- ✅ Understand how Redis stores data internally

## What You'll Install
There are two separate programs:
```
Redis Server
        +
Redis CLI
```

### Redis Server
The server is the actual database.

It stores data and listens for requests.

```
Node.js

↓

Redis Server

↓

Memory (RAM)
```

### Redis CLI
CLI stands for **Command Line Interface**.

It is a terminal application used to communicate with the Redis Server.

Think of it like:

```
MySQL
↓

mysql CLI

MongoDB
↓

mongosh

Redis
↓

redis-cli
```

## Install Redis
The easiest and most production-like way is using **Docker**.

### Install Docker
Download and install Docker Desktop from the official site if you don't already have it.

### Pull Redis Image
```
docker pull redis
```

### Run Redis
```
docker run --name redis-server -p 6379:6379 -d redis
```

Let's understand this command:
```
docker run

Creates a new container
```
```
--name redis-server

Container name
```
```
-p 6379:6379

Host Port : Container Port
```
```
-d

Run in background
```
```
redis

Official Redis image
```

## Check Running Containers
```
docker ps
```
Output:
```
CONTAINER ID   IMAGE   PORTS
a91sd123       redis   0.0.0.0:6379->6379/tcp
```
Redis is now running.

## Connect to Redis CLI
Execute:
```
docker exec -it redis-server redis-cli
```

You should see:
```
127.0.0.1:6379>
```

Congratulations!

You are now connected to Redis.

## Your First Redis Command
Type:
```
PING
```

Output:
```
PONG
```

What happened?
```
CLI

↓

Redis Server

↓

PONG
```

This simply checks whether Redis is alive.

## SET Command
Store a value.
```
SET name "Rahul"
```

Output
```
OK
```

Memory now looks like:
```
name

↓

Rahul
```

## GET Command
Retrieve the value.
```
GET name
```

Output
```
"Rahul"
```

Redis searches the key and returns the value.

## Updating a Value
Run: 
```
SET name "Mark"
```

Output
```
OK
```

Now:
```
GET name
```

Output
```
Mark
```
Redis simply overwrites the existing value.

## Multiple Keys
```
SET city "Delhi"

SET country "India"

SET age 25
```
Memory:

```
name

↓

Amit

city

↓

Delhi

country

↓

India

age

↓

25
```

Retrieve them:

```
GET city

GET country

GET age
```

## Does Redis Care About Data Types?
If you use `SET`, Redis stores the value as a **string**.

```
SET age 25
```

Even though you typed a number, it's stored as a string value.

Redis has other data structures (Lists, Hashes, Sets, etc), which you'll learn in later chapters.

## EXISTS Command
Check whether a key exists.

```
EXISTS name
```

Output:
```
(integer) 1
```

Meaning:
```
1 = Exists
0 = Doesn't Exist
```

Example:
```
EXISTS xyz
```

Output
```
(integer) 0
```

## DEL Command
Delete a key.
```
DEL name
```

Output
```
(integer) 1
```

Now:
```
GET name
```

Output
```
(nil)
```

`(nil)` means the key doesn't exist.

## KEYS Command
See all keys
```
KEYS *
```

Output
```
1) "city"
2) "country"
3) "age"
```

**Why `*`?**
`*` is a wildcard.

Examples:
```
KEYS user:*
```

Finds all keys starting with `user:`.
```
user:1

user:2

user:5
```

## FLUSHDB
Delete all keys in the **current database**.
```
FLUSHDB
```

Output
```
OK
```

## FLUSHALL
Delete everything from **all Redis databases**.
```
FLUSHALL
```

Output
```
OK
```

⚠️ Never run `FLUSHALL` on a production server unless you intentionally want to erase all Redis data.

## TTL (Time To Live)
One of Redis's best features.

Store a key that expires automatically:
```bash
SET otp "5678" EX 60
```

Meaning:
```
OTP

↓

5678

↓

Automatically deleted after 60 seconds
```

Check remaining time:
```
TTL otp
```

Example output:
```
(integer) 42
```

After 42 seconds:
```
41

40

39

...
```

Eventually:
```
GET otp
```

Output
```
(nil)
```

The key was automatically removed.

## EXPIRE
You can also set an expiration after creating a key.
```bash
SET token "abc123"

EXPIRE token 120
```

Now the key will expire in 120 seconds.

## PERSIST
Remove the expiration.
```bash
PERSIST token
```

Now the key stays forever (until you delete it).

## TYPE
Check what kind of data a key stores.
```bash
TYPE city
```

Output
```
string
```

Later you'll also see outputs like:
- `list`
- `hash`
- `set`
- `zset`
- `stream`

## Redis Is Case-Sensitive
```bash
SET Name "John"

SET name "Rahul"
```

These are different keys.
```
Name

↓

John

name

↓

Rahul
```

## Common Beginner Mistakes
❌ Forgetting that keys are case-sensitive.

❌ Using `KEYS *` in production. It's fine for learning, but on very large databases it can be slow. In production, developers usually use the `SCAN` command instead.

❌ Storing everything forever. Temporary data like OTPs or verification tokens should usually have an expiration (`EX` or `EXPIRE`).

## Mini Practice
Run these commands in order:
```bash
PING

SET name "DOXT Ninja"

GET name

SET city "Kanpur"

GET city

EXISTS city

DEL city

EXISTS city

SET otp "123456" EX 30

TTL otp

TYPE otp

KEYS *
```

If you understand the output of each command and why it behaves that way, you've completed this chapter.

## Homework
1. Store your name, age, favorite programming language, and country in Redis.
2. Create an OTP that expires in 20 seconds.
3. Observe the TTL count down until the key disappears.
4. Create 5 keys named `user:1` through `user:5`.
5. Use `KEYS user:*` to list only those user keys.
6. Delete one key with `DEL` and verify it no longer exists using `EXISTS`.


