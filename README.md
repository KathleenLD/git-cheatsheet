# What Do All These Words In My Terminal Mean? #

I'm learning how to use `git` and finding it quite difficult. In order to help myself
learn, I'm writing up a cheat sheet. Right now I'm just listing out the
terms that I keep seeing and know I need to define. Eventually I'll add
easy-to-understand definitions so that I can reference this while I work.

This isn't going to be a full blown tutorial, because many people have already done
that excellently. As the repo title suggests, this is only going to be a cheat sheet.

## Important Terms

- `-h` = you may pass git -h with any git command to have it provide additional help/options for that command
- `origin` = convention for the original remote repository. `git remote -v` will display all remote repos
- `remote`
- `local`
- `master`
- `branch`
- `checkout`
- `-m`
- `-d` = delete
- `-D` = Unlike -d, this deletes an unmerged branch, ignoring the warning that it is unmerged and will be lost
- `-u` = set upstream (usually used: `git push -u origin <local branch>)
- `-a` = usually means --all but these options can all differ depending on command they are passed in with
- `push`
- `fetch`
- `pull`
- `clone`
- `fork`
- `add`
- `status`
- `merge`
- `stage`
- `HEAD`
- `reset` = this lets you clean up your master if you've messed it up and it's awkwardly out of sync with the upstream ([How to Reset Your Github Fork](http://scribu.net/blog/resetting-your-github-fork.html))
- `rebase` = "Rebase helps to cut up commits and slice them into any way that you want them served up, and placed exactly where you want them. You can actually rewrite history with this command, be it reordering commits, squashing them into bigger ones, or completely ignoring them if you so desire." ([Intro to rebase](http://gitready.com/intermediate/2009/01/31/intro-to-rebase.html)) **note that you should never rebase a branch that has been pushed/merged and/or is one somebody else is working in** Git will prevent you from pushing a branch that has been rebased unless you push with `--force`
- `.gitignore`
- `diff`
- `fsck` = useful for data integrity validation and recovery of git repo
- `hash/sha/commit id` = this term refers to the commit ID. It is generally a long SHA1 value that may look like fcaed834ace0b9b5a8cff09d9d397031305978df. You only need the first few characters to refer to that commit, provided those characters are unambiguous. (i.e., git co fcaed83 will checkout the previously mentioned commit without requiring the entire commit ID, as git can infer the commit from this shorthand hash)

## Lingering Questions

- Why do `checkout <branch>` and `checkout <file>` seem to do such different things?
  - [This](http://stevelosh.com/blog/2013/04/git-koans/#one-thing-well) is not a satisfying answer.

- Why is `HEAD` in all caps?
  - HEAD is all caps to differentiate it from a regular 'head.' There are multiple heads in a git repository. You can view them in project/.git/refs/heads. Each commit is or has a "head" and uppercase HEAD refers to the currently active branch or commit.

- How do I take 20 commits and squash them into 1 big commit?
  - This is done using rebase. `git rebase -i` will put you into an interactive rebase mode where you can choose which commits to omit, squash, etc. **rebase** rewrites git history and is therefore dangerous. It's useful to keep a clean linear git history but you can almost always avoid using it in favor of `merge`

- I committed something but forgot to include a file, or would like to change the message of the commit, may I?
  - Add the file using `git add ..` and then type `git commit --amend` to ammend this change to the last commit. You may also issue the `--amend` command without adding/changing any files and your text editor will open and allow you to revise the commit message. Note that `--amend` essentially does a rebase and caveats on rebasing should be taken into account. You will not be able to push a rebased branch that has been pushed previously without using `--force`

## Recommended Tools

[Atlassian SourceTree](http://www.sourcetreeapp.com/) is a free and awesome tool for working with git, visualizing an entire git repo, and pretty much doing anything you'd do from the commandline, plus more like creating pull requests directly from your desktop.

## Resources

- [git daily workflow](https://www.sonassi.com/wp-content/uploads/2012/07/simple_git_daily_workflow.pdf)-- One page workflow
- [git - the simple guide](http://rogerdudler.github.io/git-guide/)
- [try git](http://try.github.io/) Code School course
- [GitHub support materials](https://help.github.com/)
- [GitHub Training](http://training.github.com/web/git-foundations/)
- [Git tips for beginners](http://markjberger.com/blog/git-tips-for-beginners-interested-in-open-source)
- [Don't be afraid to commit](http://dont-be-afraid-to-commit.readthedocs.org/en/latest/) (Python/Django-focused, but a great resource nonetheless)
- [Think Like A Git](http://think-like-a-git.net)
- [Git and GitHub Secrets](http://zachholman.com/talk/git-github-secrets/)
- [More Git and GitHub Secrets](http://zachholman.com/talk/more-git-and-github-secrets/)
- [Understanding Git](http://www.sbf5.com/~cduan/technical/git/)
- [GitHub Glossary](https://help.github.com/articles/github-glossary)

