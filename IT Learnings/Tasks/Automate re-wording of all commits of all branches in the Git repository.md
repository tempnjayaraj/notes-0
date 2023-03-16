---
type: task
last-modified-date: 21-02-2023
creation-date: 21-02-2023, 22-02-2023, 23-02-2023
parent-topic: Source Code Management, Shell Scripting, GitLab
parent-project: Smith and Nephew DevOps
tags: Shell Scripting
task-type: feature
completed-date: 23-02-2023
---

### Print all commit messages in current branch
```bash
git log --pretty=format:'%h %s' | awk '{for(i=2;i<=NF;i++) printf "%s ", $i; print ""}'
```

### Print all commit hashes in current branch
```bash
git log --pretty=format:'%h %s' | awk '{print $1}'
```

### git-filter-repo
[Git Filter Repo App](https://github.com/newren/git-filter-repo.git)
This App could be used to rewrite commit messages using Python script. 
The problem with this approach was that these changes didn't create a new commit hash thereby we couldn't push it to repo.

### Succesful and Working method
We could try to use git filter-branch to solve this issue.

```bash
git filter-branch --msg-filter '
    commit_message=$(git log --format="%H" -n 1 $GIT_COMMIT | tail -n 1)
    echo "$(git log --format=%B -n 1 $commit_message)"
'
```

^d52eac

^82946f

## Script to do the task with method
```bash
cd $1 && git clone $2
cd $3
git checkout $4
git filter-branch --msg-filter ' 
commit_message=$(git log --format="%H" -n 1 $GIT_COMMIT | tail -n 1) 
echo "$(git log --format=%B -n 1 $commit_message)" 
'
git push -uf
cd ..
rm -rf $3
```


```mermaid
graph TD
A(Get Project ID from user) --> B[Get project details from /projects API]
B --> C[Get namespace from /groups API]
C --> D[Get number of branches]
D --> E[Get a single branch]
E -->  G[Get protection details if exists]
G --> H[Pass projectName, projectURL, branch to the rewrite script]
H --> I[Then the script pushes the re-written commits to the repo]
I --> J[Put back the branch protection rules]
J -->|if another branch exists| E
```
