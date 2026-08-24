# Complete Git & GitHub Mastery Checklist

## 1. Version Control Fundamentals

* [ ] What is version control?
* [ ] Why version control is needed
* [ ] Version Control System (VCS)
* [ ] Centralized vs distributed version control
* [ ] Git vs GitHub
* [ ] Git vs GitLab vs Bitbucket
* [ ] Repository
* [ ] Working directory
* [ ] Staging area
* [ ] Commit
* [ ] Branch
* [ ] Remote repository
* [ ] HEAD
* [ ] Hashes
* [ ] Git history

---

# 2. Git Installation & Configuration

* [ ] Install Git
* [ ] Check Git version
* [ ] `git --version`
* [ ] Configure username
* [ ] Configure email
* [ ] `git config`
* [ ] Local configuration
* [ ] Global configuration
* [ ] System configuration
* [ ] `.gitconfig`
* [ ] Default branch
* [ ] Git editor
* [ ] Git aliases

### Practice

* [ ] Configure Git globally
* [ ] Create useful aliases
* [ ] Inspect Git configuration

---

# 3. Creating a Repository

* [ ] `git init`
* [ ] `.git` directory
* [ ] What `.git` contains
* [ ] `git clone`
* [ ] Clone URL
* [ ] Clone using SSH
* [ ] Clone using HTTPS
* [ ] Repository structure

---

# 4. Working Directory

* [ ] Working tree
* [ ] Modified files
* [ ] Untracked files
* [ ] Tracked files
* [ ] Deleted files
* [ ] Renamed files
* [ ] `git status`

### Practice

* [ ] Create file
* [ ] Modify file
* [ ] Delete file
* [ ] Rename file
* [ ] Inspect status

---

# 5. Staging Area

One of Git's most important concepts.

* [ ] What is staging?
* [ ] Why staging exists
* [ ] `git add`
* [ ] Add one file
* [ ] Add multiple files
* [ ] Add directory
* [ ] `git add .`
* [ ] `git add -A`
* [ ] `git add -p`
* [ ] Unstage file
* [ ] `git restore --staged`
* [ ] Inspect staged changes

---

# 6. Commits

* [ ] What is a commit?
* [ ] `git commit`
* [ ] Commit message
* [ ] Good commit messages
* [ ] Atomic commits
* [ ] Commit history
* [ ] Commit hash
* [ ] Parent commit
* [ ] Multiple parents
* [ ] Commit metadata
* [ ] Author
* [ ] Committer
* [ ] Timestamp

### Commands

* [ ] `git commit -m`
* [ ] `git commit -am`
* [ ] `git commit --amend`

---

# 7. Git History

* [ ] `git log`
* [ ] `git log --oneline`
* [ ] `git log --graph`
* [ ] `git log --all`
* [ ] `git show`
* [ ] `git diff`
* [ ] `git diff --staged`
* [ ] Search commit history
* [ ] Search by author
* [ ] Search by date
* [ ] Search commit messages

---

# 8. Git Diff

* [ ] Working tree diff
* [ ] Staged diff
* [ ] Commit diff
* [ ] Branch diff
* [ ] `git diff`
* [ ] `git diff --staged`
* [ ] `git diff HEAD`
* [ ] Compare commits
* [ ] Compare branches

---

# 9. `.gitignore`

* [ ] Why `.gitignore`?
* [ ] Create `.gitignore`
* [ ] Ignore files
* [ ] Ignore directories
* [ ] Wildcards
* [ ] Negation patterns
* [ ] Global `.gitignore`
* [ ] Ignore environment files
* [ ] Ignore build output
* [ ] Ignore dependencies
* [ ] Ignore OS files
* [ ] Ignore IDE files

### Important

* [ ] `.env`
* [ ] `node_modules`
* [ ] Build folders
* [ ] Logs
* [ ] Secrets
* [ ] Temporary files

---

# 10. Git Branches

* [ ] What is a branch?
* [ ] Why branches?
* [ ] `git branch`
* [ ] Create branch
* [ ] Delete branch
* [ ] Rename branch
* [ ] Switch branch
* [ ] `git switch`
* [ ] `git checkout`
* [ ] Branch pointers
* [ ] HEAD
* [ ] Branch tracking

### Practice

* [ ] Create feature branch
* [ ] Switch branches
* [ ] Make different commits
* [ ] Compare branches

---

# 11. HEAD

Understand this properly.

* [ ] What is HEAD?
* [ ] HEAD points to current branch
* [ ] Detached HEAD
* [ ] `HEAD~1`
* [ ] `HEAD~2`
* [ ] `HEAD^`
* [ ] Relative references
* [ ] `HEAD~n`

---

# 12. Merge

* [ ] What is merging?
* [ ] Fast-forward merge
* [ ] Three-way merge
* [ ] Merge commit
* [ ] `git merge`
* [ ] Merge branches
* [ ] Merge conflicts
* [ ] Resolve conflicts
* [ ] Abort merge
* [ ] `git merge --abort`

### Practice

* [ ] Merge feature branch
* [ ] Create conflict intentionally
* [ ] Resolve conflict manually

---

# 13. Merge Conflicts

* [ ] Why conflicts happen?
* [ ] Conflict markers
* [ ] `<<<<<<<`
* [ ] `=======`
* [ ] `>>>>>>>`
* [ ] Resolve manually
* [ ] Stage resolved files
* [ ] Continue merge
* [ ] Abort merge
* [ ] Conflict resolution strategies

### Practice

* [ ] Same-line conflict
* [ ] Different-line conflict
* [ ] Multiple-file conflict
* [ ] Resolve conflict using VS Code
* [ ] Resolve conflict using terminal

---

# 14. Rebase

Very important.

* [ ] What is rebase?
* [ ] Rebase vs merge
* [ ] `git rebase`
* [ ] Interactive rebase
* [ ] `git rebase -i`
* [ ] Reorder commits
* [ ] Squash commits
* [ ] Fixup commits
* [ ] Edit commit
* [ ] Drop commit
* [ ] Rebase conflicts
* [ ] Continue rebase
* [ ] Abort rebase

### Important

* [ ] Why rebasing rewrites history
* [ ] Why not to casually rebase shared branches

---

# 15. Merge vs Rebase

* [ ] Fast-forward merge
* [ ] Three-way merge
* [ ] Merge commit
* [ ] Linear history
* [ ] Rewritten history
* [ ] Shared branches
* [ ] Private branches
* [ ] When to merge
* [ ] When to rebase

---

# 16. Remote Repositories

* [ ] What is a remote?
* [ ] `git remote`
* [ ] `git remote -v`
* [ ] Add remote
* [ ] Remove remote
* [ ] Rename remote
* [ ] `origin`
* [ ] `upstream`

---

# 17. Git Push

* [ ] `git push`
* [ ] Push branch
* [ ] Push tags
* [ ] `git push -u`
* [ ] Set upstream branch
* [ ] Push new branch
* [ ] Push all branches
* [ ] Force push
* [ ] `--force`
* [ ] `--force-with-lease`

### Important

* [ ] Understand why force push is dangerous
* [ ] Prefer `--force-with-lease`

---

# 18. Git Fetch

* [ ] What is fetch?
* [ ] `git fetch`
* [ ] Fetch all remotes
* [ ] Fetch specific branch
* [ ] Remote-tracking branches
* [ ] `origin/main`
* [ ] Fetch vs pull

---

# 19. Git Pull

* [ ] What is pull?
* [ ] `git pull`
* [ ] Pull with merge
* [ ] Pull with rebase
* [ ] `git pull --rebase`
* [ ] Pull conflicts
* [ ] Configure pull strategy

---

# 20. GitHub Fundamentals

* [ ] What is GitHub?
* [ ] Git vs GitHub
* [ ] GitHub repository
* [ ] Public repository
* [ ] Private repository
* [ ] README
* [ ] Repository settings
* [ ] Repository visibility
* [ ] GitHub profile
* [ ] GitHub organizations

---

# 21. GitHub Authentication

* [ ] HTTPS authentication
* [ ] Personal Access Tokens
* [ ] SSH authentication
* [ ] SSH keys
* [ ] Generate SSH key
* [ ] Add SSH key to GitHub
* [ ] Test SSH connection
* [ ] `ssh-agent`
* [ ] Deploy keys
* [ ] Fine-grained tokens

### Security

* [ ] Never commit tokens
* [ ] Never commit passwords
* [ ] Never commit private keys
* [ ] Rotate leaked credentials

---

# 22. GitHub README

* [ ] README structure
* [ ] Project description
* [ ] Features
* [ ] Installation
* [ ] Usage
* [ ] API documentation
* [ ] Screenshots
* [ ] Architecture
* [ ] Environment setup
* [ ] Contributing
* [ ] License

---

# 23. GitHub Issues

* [ ] What are Issues?
* [ ] Create issue
* [ ] Issue title
* [ ] Issue description
* [ ] Labels
* [ ] Assignees
* [ ] Milestones
* [ ] Issue comments
* [ ] Close issue
* [ ] Reopen issue
* [ ] Link commits to issues

---

# 24. GitHub Projects

* [ ] GitHub Projects
* [ ] Board view
* [ ] Table view
* [ ] Issues
* [ ] Tasks
* [ ] Status
* [ ] Priority
* [ ] Milestones
* [ ] Project automation

---

# 25. Pull Requests

One of the most important GitHub concepts.

* [ ] What is a Pull Request?
* [ ] Feature branch
* [ ] Push branch
* [ ] Create PR
* [ ] PR title
* [ ] PR description
* [ ] Reviewers
* [ ] Assignees
* [ ] Labels
* [ ] Draft PR
* [ ] PR comments
* [ ] Code review
* [ ] Requested changes
* [ ] Approve PR
* [ ] Merge PR
* [ ] Close PR

---

# 26. Pull Request Strategies

* [ ] Merge commit
* [ ] Squash and merge
* [ ] Rebase and merge
* [ ] Understand differences
* [ ] When to use each
* [ ] Branch cleanup after merge

---

# 27. Code Review

* [ ] Why code review?
* [ ] Review changes
* [ ] Inline comments
* [ ] Suggest changes
* [ ] Review conversations
* [ ] Approve
* [ ] Request changes
* [ ] Review checklist
* [ ] Security review
* [ ] Performance review
* [ ] Maintainability review

---

# 28. Collaboration Workflow

Learn a real team workflow.

* [ ] Clone repository
* [ ] Create branch
* [ ] Make changes
* [ ] Commit
* [ ] Push
* [ ] Create PR
* [ ] Code review
* [ ] Fix requested changes
* [ ] Update PR
* [ ] Merge
* [ ] Delete branch
* [ ] Sync local repository

---

# 29. Branching Strategies

* [ ] Feature branches
* [ ] GitHub Flow
* [ ] Git Flow
* [ ] Trunk-based development
* [ ] Release branches
* [ ] Hotfix branches
* [ ] Main branch
* [ ] Development branch
* [ ] Feature branches

### Understand

* [ ] When each strategy makes sense
* [ ] Advantages
* [ ] Disadvantages

---

# 30. Git Tags

* [ ] What is a tag?
* [ ] Lightweight tags
* [ ] Annotated tags
* [ ] `git tag`
* [ ] Create tag
* [ ] Delete tag
* [ ] Push tag
* [ ] Version tags
* [ ] Semantic versioning

---

# 31. Releases

* [ ] GitHub Releases
* [ ] Release notes
* [ ] Tags
* [ ] Versioning
* [ ] Changelog
* [ ] Release assets
* [ ] Pre-releases
* [ ] Stable releases

---

# 32. Semantic Versioning

* [ ] MAJOR
* [ ] MINOR
* [ ] PATCH
* [ ] Breaking changes
* [ ] New features
* [ ] Bug fixes
* [ ] Pre-release versions

---

# 33. Git Stash

* [ ] What is stash?
* [ ] `git stash`
* [ ] `git stash push`
* [ ] `git stash list`
* [ ] `git stash pop`
* [ ] `git stash apply`
* [ ] `git stash drop`
* [ ] Stash specific files
* [ ] Stash untracked files

### Practice

* [ ] Save unfinished work
* [ ] Switch branches
* [ ] Restore work

---

# 34. Git Restore

* [ ] `git restore`
* [ ] Restore working file
* [ ] Restore staged file
* [ ] Restore from commit
* [ ] Restore specific file
* [ ] Difference between restore and reset

---

# 35. Git Reset

Understand this carefully.

* [ ] What is reset?
* [ ] `git reset`
* [ ] Soft reset
* [ ] Mixed reset
* [ ] Hard reset
* [ ] `--soft`
* [ ] `--mixed`
* [ ] `--hard`
* [ ] HEAD movement
* [ ] Staging area changes
* [ ] Working directory changes

### Important

* [ ] Understand why `git reset --hard` is dangerous

---

# 36. Git Revert

* [ ] What is revert?
* [ ] `git revert`
* [ ] Revert a commit
* [ ] Revert merge commit
* [ ] Revert vs reset
* [ ] Safe rollback on shared branches

---

# 37. Git Reflog

Extremely useful recovery tool.

* [ ] What is reflog?
* [ ] `git reflog`
* [ ] Recover deleted branch
* [ ] Recover lost commit
* [ ] Recover after reset
* [ ] Recover after rebase
* [ ] HEAD history

---

# 38. Git Cherry-Pick

* [ ] What is cherry-pick?
* [ ] `git cherry-pick`
* [ ] Pick one commit
* [ ] Pick multiple commits
* [ ] Cherry-pick conflicts
* [ ] Continue cherry-pick
* [ ] Abort cherry-pick
* [ ] When cherry-pick is useful

---

# 39. Git Bisect

* [ ] What is bisect?
* [ ] `git bisect start`
* [ ] Good commit
* [ ] Bad commit
* [ ] Binary search through history
* [ ] Automated bisect
* [ ] Find regression

---

# 40. Git Worktrees

Advanced but very useful.

* [ ] What is a worktree?
* [ ] `git worktree`
* [ ] Create worktree
* [ ] Remove worktree
* [ ] Multiple branches simultaneously
* [ ] Worktree vs clone

---

# 41. Git Internals

This is where you move from Git user → Git expert.

* [ ] `.git` directory
* [ ] HEAD
* [ ] Index
* [ ] Objects
* [ ] Blob
* [ ] Tree
* [ ] Commit object
* [ ] Tag object
* [ ] SHA hashing
* [ ] Object database
* [ ] References
* [ ] Branch refs
* [ ] Tags
* [ ] Remote refs
* [ ] Reflog

### Commands

* [ ] `git cat-file`
* [ ] `git ls-tree`
* [ ] `git rev-parse`
* [ ] `git show-ref`
* [ ] `git update-ref`

---

# 42. Git Object Model

Understand:

```text
Commit
  ↓
Tree
  ↓
Blob
```

* [ ] Blob objects
* [ ] Tree objects
* [ ] Commit objects
* [ ] Parent commits
* [ ] Object hashes
* [ ] Content-addressable storage
* [ ] Immutable objects

---

# 43. Git Index

* [ ] What is the index?
* [ ] Staging area internals
* [ ] Working tree
* [ ] Index
* [ ] Repository
* [ ] How `git add` works
* [ ] How commit uses the index

---

# 44. Git References

* [ ] Branch refs
* [ ] Tag refs
* [ ] HEAD
* [ ] Remote-tracking refs
* [ ] Symbolic references
* [ ] Reference updates

---

# 45. Git Garbage Collection

* [ ] Unreachable objects
* [ ] Object cleanup
* [ ] `git gc`
* [ ] Repacking
* [ ] Pruning
* [ ] Pack files
* [ ] Loose objects

---

# 46. Git Performance

* [ ] Large repositories
* [ ] Repository size
* [ ] Large files
* [ ] Git LFS
* [ ] Shallow clones
* [ ] Partial clones
* [ ] Sparse checkout
* [ ] Monorepos
* [ ] Repository optimization

---

# 47. Git LFS

* [ ] Why Git LFS?
* [ ] Large binary files
* [ ] Install Git LFS
* [ ] Track files
* [ ] `.gitattributes`
* [ ] Push LFS files
* [ ] Pull LFS files
* [ ] Storage limits

---

# 48. Git Hooks

* [ ] What are Git hooks?
* [ ] Client-side hooks
* [ ] Server-side hooks
* [ ] `pre-commit`
* [ ] `commit-msg`
* [ ] `pre-push`
* [ ] `post-commit`
* [ ] Automated checks
* [ ] Code formatting
* [ ] Linting
* [ ] Tests before commit

### Build

* [ ] Custom pre-commit hook
* [ ] Prevent secrets from being committed

---

# 49. GitHub Actions

Very important for modern development.

* [ ] What is GitHub Actions?
* [ ] Workflow
* [ ] Workflow file
* [ ] YAML basics
* [ ] Events
* [ ] Jobs
* [ ] Steps
* [ ] Runners
* [ ] Actions
* [ ] Environment variables
* [ ] Secrets
* [ ] Artifacts
* [ ] Caching

---

# 50. CI/CD with GitHub

* [ ] Run tests automatically
* [ ] Run linting
* [ ] Build application
* [ ] Run security checks
* [ ] Build Docker image
* [ ] Deploy automatically
* [ ] Environment separation
* [ ] Staging deployment
* [ ] Production deployment
* [ ] Manual approval
* [ ] Rollback

---

# 51. GitHub Security

* [ ] Repository permissions
* [ ] Collaborators
* [ ] Teams
* [ ] Branch protection
* [ ] Required reviews
* [ ] Required status checks
* [ ] Protected branches
* [ ] CODEOWNERS
* [ ] Secret scanning
* [ ] Dependabot
* [ ] Dependency alerts
* [ ] Security advisories
* [ ] Signed commits

---

# 52. Git Commit Signing

* [ ] Why sign commits?
* [ ] GPG
* [ ] SSH signing
* [ ] Configure signing
* [ ] Verify signatures
* [ ] Signed tags
* [ ] GitHub verified commits

---

# 53. Monorepos

* [ ] What is a monorepo?
* [ ] Monorepo vs multi-repo
* [ ] Repository structure
* [ ] Shared packages
* [ ] Git performance
* [ ] Workspaces
* [ ] Sparse checkout
* [ ] CI/CD for monorepos

---

# 54. GitHub Organizations

* [ ] Organization
* [ ] Teams
* [ ] Repository permissions
* [ ] Team access
* [ ] Outside collaborators
* [ ] Organization security
* [ ] Branch protection
* [ ] Organization settings

---

# 55. Open Source Workflow

* [ ] Fork repository
* [ ] Clone fork
* [ ] Add upstream
* [ ] Sync fork
* [ ] Create feature branch
* [ ] Make changes
* [ ] Push branch
* [ ] Create PR
* [ ] Respond to review
* [ ] Update PR
* [ ] Keep fork synchronized

---

# 56. GitHub Collaboration Workflow

### Team Workflow

* [ ] Clone repository
* [ ] Pull latest changes
* [ ] Create feature branch
* [ ] Work locally
* [ ] Commit frequently
* [ ] Push branch
* [ ] Open PR
* [ ] Review code
* [ ] Resolve review comments
* [ ] Resolve conflicts
* [ ] Merge
* [ ] Delete branch
* [ ] Pull latest main

---

# 57. Git Recovery

Learn how to recover from mistakes.

* [ ] Accidentally deleted file
* [ ] Accidentally deleted branch
* [ ] Wrong commit
* [ ] Wrong commit message
* [ ] Wrong files committed
* [ ] Accidental reset
* [ ] Bad rebase
* [ ] Bad merge
* [ ] Lost commit
* [ ] Force push mistake
* [ ] Recover using reflog
* [ ] Recover dangling objects

---

# 58. Common Git Problems

* [ ] Merge conflict
* [ ] Push rejected
* [ ] Non-fast-forward error
* [ ] Detached HEAD
* [ ] Wrong branch
* [ ] Uncommitted changes
* [ ] Diverged branches
* [ ] Authentication failure
* [ ] SSH failure
* [ ] Remote URL wrong
* [ ] Large file rejection
* [ ] Secret accidentally committed

---

# 59. Git Best Practices

* [ ] Small commits
* [ ] Atomic commits
* [ ] Meaningful commit messages
* [ ] Keep branches focused
* [ ] Pull before starting work
* [ ] Avoid unnecessary merge commits
* [ ] Don't commit secrets
* [ ] Don't commit generated files unnecessarily
* [ ] Review diff before commit
* [ ] Review changes before push
* [ ] Don't force-push shared branches
* [ ] Keep main stable
* [ ] Use PRs for team changes

---

# 60. Commit Message Conventions

* [ ] Clear commit messages
* [ ] Imperative style
* [ ] Conventional Commits
* [ ] `feat`
* [ ] `fix`
* [ ] `docs`
* [ ] `refactor`
* [ ] `test`
* [ ] `chore`
* [ ] `perf`
* [ ] Breaking changes

---

# 61. GitHub Project Management

* [ ] Issues
* [ ] Projects
* [ ] Milestones
* [ ] Labels
* [ ] Discussions
* [ ] Pull Requests
* [ ] Releases
* [ ] Roadmaps
* [ ] Templates

### Templates

* [ ] Issue templates
* [ ] Pull request templates
* [ ] Contribution guidelines
* [ ] Code of conduct
* [ ] Security policy

---

# 62. GitHub Actions Advanced

* [ ] Matrix builds
* [ ] Job dependencies
* [ ] Conditional jobs
* [ ] Reusable workflows
* [ ] Composite actions
* [ ] Artifacts
* [ ] Caching dependencies
* [ ] Environment protection
* [ ] Deployment environments
* [ ] Secrets
* [ ] OIDC concepts
* [ ] Self-hosted runners

---

# 63. Git + Node.js Workflow

Since you're learning Node.js:

* [ ] Initialize Node project
* [ ] Create Git repository
* [ ] `.gitignore`
* [ ] Commit package files
* [ ] Don't commit `node_modules`
* [ ] Don't commit `.env`
* [ ] Branch-based development
* [ ] Pull Requests
* [ ] Run tests in GitHub Actions
* [ ] Run linting
* [ ] Build project
* [ ] Deploy from GitHub

---

# 64. Git + Linux Workflow

* [ ] Git through terminal
* [ ] SSH keys
* [ ] SSH agent
* [ ] Git aliases
* [ ] Bash scripting
* [ ] Git hooks
* [ ] Git automation
* [ ] Git on remote Ubuntu server
* [ ] Deploy using Git
* [ ] Git + systemd
* [ ] Git + CI/CD

---

# 65. Practical Projects

### Beginner

* [ ] Create local Git repository
* [ ] Practice commits
* [ ] Practice branches
* [ ] Practice merge
* [ ] Practice conflicts
* [ ] Push project to GitHub

### Intermediate

* [ ] Build project with feature branches
* [ ] Use Pull Requests
* [ ] Perform code reviews
* [ ] Create GitHub Issues
* [ ] Create Releases
* [ ] Configure branch protection

### Advanced

* [ ] Build CI pipeline
* [ ] Build CD pipeline
* [ ] Automated testing
* [ ] Automated deployment
* [ ] GitHub Actions
* [ ] Git hooks
* [ ] Signed commits
* [ ] Monorepo

### Git Internals

* [ ] Build a mini Git
* [ ] Implement blob storage
* [ ] Implement tree objects
* [ ] Implement commits
* [ ] Implement branches
* [ ] Implement checkout
* [ ] Implement basic log

---

# 66. Final Git & GitHub Mastery Checklist

* [ ] I understand version control
* [ ] I understand Git vs GitHub
* [ ] I understand working tree
* [ ] I understand staging area
* [ ] I understand commits
* [ ] I understand branches
* [ ] I understand HEAD
* [ ] I can create and manage branches
* [ ] I can merge branches
* [ ] I can resolve conflicts
* [ ] I understand rebase
* [ ] I understand merge vs rebase
* [ ] I understand remotes
* [ ] I can push and pull
* [ ] I understand fetch
* [ ] I can use GitHub
* [ ] I can create Pull Requests
* [ ] I can review code
* [ ] I understand GitHub Issues
* [ ] I understand GitHub Projects
* [ ] I can use GitHub Actions
* [ ] I can build CI/CD pipelines
* [ ] I understand Git internals
* [ ] I understand Git objects
* [ ] I understand the index
* [ ] I understand refs
* [ ] I can use reflog
* [ ] I can recover lost commits
* [ ] I can use cherry-pick
* [ ] I can use bisect
* [ ] I understand Git hooks
* [ ] I understand Git LFS
* [ ] I understand branch protection
* [ ] I understand GitHub security
* [ ] I can work with a team using Git
* [ ] I can contribute to open source
* [ ] I can safely recover from Git mistakes
* [ ] I can automate development workflows
* [ ] I can use Git as part of a production CI/CD workflow
