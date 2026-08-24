- ✅ What Redis is
- ✅ Why Redis exists
- ✅ Why companies use it
- ✅ How Redis stores data
- ✅ Memory architecture
- ✅ Persistence
- ✅ Use cases
- ✅ Basic terminology

## What is Redis?

**Redis** stands for:
- **RE**mote **DI**ctionary **S**erver

Redis in an **open-source, in-memroy data store** that can be used as:
- Databse
- Cache
- Message Broker
- Session Store
- Queue
- Pub/Sub system

Think of Redis as a **super-fast notebook kept in RAM**, while MongoDB is like a **filing cabinet on desk**.

## Why Was Redis Created?
Imagine an e-commerce website.

A user opens the home page.

Your backend does this:

```
Browser
   │
   ▼
Express Server
   │
   ▼
MongoDB
```

MongoDB reads data from disk.

Even with indexes, disk access is much slower than RAM.

If **10,000 users** request the homepage simultaneously.

```
MongoDB
↓↓↓↓↓↓↓↓↓↓↓↓↓↓
10,000 Queries
```

MongoDB becomes the bottleneck.

Redis solves this.

## Redis Workflow
Instead of asking MongoDB every time:

```
Browser
      │
      ▼
Express
      │
      ▼
Redis
      │
  Data Found?
   /       \
 Yes        No
 │           │
 ▼           ▼
Return    MongoDB
             │
             ▼
      Save to Redis
             │
             ▼
         Return Data
```

This pattern is called **Cache-Aside**

## Why Is Redis So Fast?
The biggest reason:

**Redis stores data in RAM (memory), not on disk**.

### MongoDB

```
CPU

↓

SSD / HDD

↓

Read File

↓

Return Data
```

### Redis

```
CPU

↓

RAM

↓

Return Data
```

RAM access takes **nanoseconds**, while disk access is much slower.

That's why Redis can process hundreds of thousands of operations per second on a single machine.

## RAM vs Disk

|**RAM**|**Disk (SSD/HDD)**|
|-------|------------------|
|Very fast| Slower|
|Temporary (unless persisted)| Permanent|
|Expensive| Cheaper|
|Used by Redis| Used by MongoDB|

Think of it like this:

- **RAM** = Your study desk. You can grab a book instantly.
- **Disk** = A cupboard. You need to walk over, open it, find the book, then return.

## Does Redis Lose Data?
A common misconception is:

    - "Redis stores everything in RAM, so it loses everything on restart."

Not neccessarily.

Redis supports **persistence**, which periodically saves memory to disk or logs changes. If configured, it can recover data after a restart. However, many applications intentionally use Redis for **temporary data** (like caches or sessions), where losing cached data isn't a problem because it can be recreated.

## When Should You Use Redis?
Redis is best when data needs to be:
- Read frequently
- Retrieved very quickly
- Temporary or easily regenerated
- Shared across multiple application instances

Examples:

### Login Sessions
```
User Logs In

↓

Session ID

↓

Redis
```

Every request checkes Redis instead of querying MongoDB.

### OTP Storage
```
OTP

↓

Redis

↓

Auto Expires in 5 Minutes
```

No cleanup job is needed if you use expiration.

### Product Cache
```
Product Details

↓

Redis

↓

Fast Response
```

### Shopping Cart
```
cart:user:1
```

Stored temporarily in Redis for quick updates.

### API Rate Limiting
```
User

↓

100 Requests

↓

Redis Counter

↓

Limit Exceeded
```

## Redis Is NOT a Replacement for MongoDB
Many beginners ask:
    - "If Redis is so fast, why not use only Redis?"

Because they solve different problems.

|**Redis**|**MongoDB**|
|---------|-----------|
|RAM|Disk|
|Extremely fast|Fast|
|Best for temporary or frequently accessed data|Best for permanent application data|
|Key-Value oriented|Document-oriented|
|Commonly used for caching, sessions, queues|Commonly used as the primary database|

In a MERN application, they often work together.
```
Frontend

↓

Express

↓

Redis (Fast Cache)

↓

MongoDB (Permanent Data)
```

## What Does Redis Store?
Redis stores data as **key-value pairs**.

Example:
```
name

↓

John
```

Here:
```
Key   = name

Value = John
```

Another example:
```
product:101

↓

iPhone 17
```

Or:
```
user:25

↓

{
  name: "Rahul",
  age: 25
}
```

The **Key** is how you look up the data. The **value** is what is stored.

## What Is a Key?
Think of a key the label on a locker.

```
Locker 101

↓

Laptop
```

you don't search every locker you go directly to locker 101.

Similarly:
```
user:15

↓

User Information
```

## Naming Keys
Good naming conventions make large applications easier to maintain.

Examples:
```
user:1

user:25

cart:user:5

product:10

otp:+919999999999

session:abc123
```

Avoid vague keys like:
```
data

test

abc

hello
```

because they don't describe what's stored.

## Common Redis Use Cases in MERN
|**Feature**|**Why Redis?**|
|-----------|--------------|
|Login sessions|Fast session lookup|
|JWT refresh tokens|Quick validation and revocation|
|OTP verification|Built-in expiration|
|Product cache|Faster page loads|
|Shopping cart|Fast updates|
|Leaderboards|Efficient sorted data|
|Notifications|Pub/Sub|
|Email jobs|Background queues|
|Chat|Real-time messaging support|
|Rate limiting|Atomic counters|

## Important Terms
- **Key**:Identifier used to access data.
- **Value**:The stored data.
- **TTL (Time to Live)**:How long a key should exist before it expires.
- **Cache**:A copy of data kept for faster access.
- **Persistence**:Saving Redis data from memory to disk.
- **Eviction**:Automatically removing keys when memory is ful (depending on configuration).

## Summary
Redis is:
- An in-memory data store.
- Extremely fast because it primarily works from RAM.
- Commonly used alongside databases like MongoDB.
- Excellent for caching, sessions, OTPs, queues, and rate limiting.
- Based on key-value storage with additional powerful data structures.

## Exercises
Before moving to the next topic, make sure you can answer these questions:

1. Why is Redis generally faster than MongoDB?
2. Why isn't Redis usually used as the only database in a MERN application?
3. What is a key-value store?
4. What is caching, and why does it imporve performance?
5. What is the diiference between RAM and disk storage?
6. Give five real-world features in a MERN application where Redis is a good fit.
7. What is TTL, and when would you use it?
8. Why are good key names important?

