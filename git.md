## Add Friend on Repository
1. Repository
2. Settings
3. Collaborators
4. Add People
5. Enter friend's GitHub username
6. Send Invite

## Clone Repository
Both developers clone the same project.
```bash
git clone https://github.com/username/mern-project.git
```
Go inside
```bash
cd mern-project
```

## Never work on main
Check current branch
```bash
git branch
```
Output
```
* main
```
Do NOT code on this branch.

## Create Your Feature Branch
Suppose you're making authentication.
```bash
git checkout -b feature/auth
```
Your friend is making products.
```bash
git checkout -b feature/products
```
Now 
```
main

├── feature/auth
└── feature/products
```
Each developer has their own branch.

## Start Coding
Example
You create
```
Login

Register

JWT

Middleware
```

Friend creates
```

Product CRUD

Product Model

Product Controller
```
No conflicts because each works in their own branch.

## Commit Regularly

```bash
git status
```

```bash
git add .
```

```bash
git commit -m "Add login API"
```
Another commit

```bash
git commit -m "Add JWT authentication"
```
Don't wait until the whole feature is finished.

## Push Your Branch

```bash
git push origin feature/auth
```

Friend

```bash
git push origin feature/products
```

GitHub now has

```
main

feature/auth

feature/products

```

## Continue Working
Whenever you finish more work

```bash
git add .

git commit -m "Add forgot password"

git push
```

Since upstream is already set, just

```bash
git push
```

## Keep Your Branch Updated

Meanwhile your friend merged something into `main`.

Update your branch.

Go to main

```bash
git checkout main
```

Download latest code

```bash
git pull origin main
```

Go back

```bash
git checkout feature/auth
```

Merge latest main

```bash
git merge main
```
Now your branch contains the newest code.

Do this every day.

## Resolve Conflicts (If Any)

If both edited

```
server/routes/user.js
```

Git may say

``` 
Merge conflict
```

You'll see

```js
<<<<<<< HEAD

your code

=======

friend code

>>>>>>>> main
```

Edit it manually.

Keep what you need.

Then

```bash
git add .

git commit
```
Conflict resolved.

## Create Pull Request
After finishing Authentication

Push

```bash
git push
```

Go to GitHub.

You'll see

```
compare & Pull Request
```

Click it.

Choose

```
feature/auth

↓

main
```
Create Pull Request.

