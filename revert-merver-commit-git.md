To revert the changes introduced by the `hot_fix` branch into the `development` branch, you can use a few methods depending on the situation and your preferences. Here are the most common approaches:

### Method 1: Revert the Merge Commit

If you merged `hot_fix` into `development` with a merge commit, you can revert that specific merge commit using `git revert`.

1. **Find the Merge Commit Hash**:
   ```sh
   git log --oneline --graph
   ```
   Identify the hash of the merge commit from the log.

2. **Revert the Merge Commit**:
   ```sh
   git revert -m 1 <merge-commit-hash>
   ```
   Here, `-m 1` indicates that we are reverting the first parent of the merge commit (i.e., the `development` branch).

3. **Push the Reverted Changes**:
   ```sh
   git push origin development
   ```

### Method 2: Reset to a Previous Commit

If you want to discard the changes completely and reset the `development` branch to the state before the merge, you can use `git reset`. This approach rewrites history, so it should be used carefully, especially if the branch is shared with others.

1. **Find the Commit Before the Merge**:
   ```sh
   git log --oneline
   ```
   Identify the hash of the commit before the merge.

2. **Reset the Branch**:
   ```sh
   git checkout development
   git reset --hard <commit-before-merge-hash>
   ```

3. **Force Push the Changes** (if shared with others):
   ```sh
   git push --force origin development
   ```

### Method 3: Create a Revert Commit (Safe for Shared Repositories)

If you want to revert the changes but do not want to rewrite history, you can create a new commit that undoes the changes introduced by the `hot_fix` branch.

1. **Identify the Changes Introduced by `hot_fix`**:
   ```sh
   git log --reverse --ancestry-path <commit-hash-of-development-before-merge>..<merge-commit-hash>
   ```

2. **Revert the Changes**:
   ```sh
   git revert <commit-hash1> <commit-hash2> ...
   ```
   Revert each commit introduced by `hot_fix`.

3. **Push the Reverted Changes**:
   ```sh
   git push origin development
   ```

### Choosing the Right Method

- **Method 1** is straightforward if you want to undo the merge commit while preserving the history of what was done.
- **Method 2** is more drastic as it removes the merge commit and all subsequent commits, effectively rewriting history.
- **Method 3** is the safest for shared repositories as it does not rewrite history but rather creates a new commit that undoes the changes.

Choose the method that best fits your workflow and team collaboration practices.
