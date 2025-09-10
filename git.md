

## Resetting Author

For having multiple git personas and forgetting to setup the author for the
relevant persona before making some commits:

```sh
git rebase -r --root --exec "git commit --amend --no-edit --reset-author"
```
