## NodeJs, Typescript, TDD, Clean Architeture and SOLID
### Course teached by Rodrigo Manguinho

## GIT

### List configurations

```
git config --list
```

### Select edit code preferred for configurations

```
git config --local core.editor code
```

### Edit configurations (with your editor preferred)

```
git config --local --edit
```

### Creating a shorcut

```
[core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
	editor = code --wait

[alias]
	s = !git status -s
	c = !git add --all && git commit -m
	l = !git log --pretty=format:'%C(blue)%h%C(red)%d %C(white)%s - %C(cyan)%cn, %C(green)%cr'

```

**[More Info](https://git-scm.com/docs/pretty-formats)**

### [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)


### Libraries

```
git-commit-msg-linter
```
