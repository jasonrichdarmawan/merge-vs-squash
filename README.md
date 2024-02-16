1. merge and rebase is hard to review if we apply the branching strategy (A)

2. squash is easier to review if we apply the branching strategy (A)

   it is easier because we can review commits up to before the last squash i.e. a squashed commit from feature/2.

```
master
|       ^
v       |
feature/1
|       ^
v       |
feature/2 (which require feature/1)
```

3. however, squash will combine multiple commits into 1 commit. the author will not be the one who create the code.

4. to be fair, squash will store the PR reference. so we can know who make the change.

5. in fact, because squash store the PR reference, there will be more info about a change, and in PR, a written conversation can happen.

6. so, to make squash work:
   1. the `feature` branch should be done by one person.
   2. if someone need changes from your `feature` branch, it is ok to create new branch based on your `feature` branch. but:
      1. it should be avoided.
      2. if someone see a commit with multiple PR references. the most bottom PR is the `feature-2` branch.