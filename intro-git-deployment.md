# Introducing Git Deployment
## Website Deployment using Git

Requirements tools for archive our purpose of deploy a website, also we will
using GitHub pages as our host for the site.

* Git
* [GitHub](https://github.com) account
* You webpage the you want to deploy

Note: you should got already setup your ssh configuration with you GitHub
account, if you don't have yet just take a look to the offcial documentation of
[Adding a new SSH key to your GitHub account](https://goo.gl/zKoW6a).

---

On our GitHub profile, lets clic con new repositori for create one, name it as you like.

* picture 1
* picture 2
* picture 3

Lets start with localizing our source file where we stored our webpage; here's mine.

```bash
$ pwd
/fulvio/projects/fulvio_page
```
```bash
$ tree
.
├── css
│   ├── bootstrap.css
│   ├── bootstrap.min.css
│   └── scrolling-nav.css
├── index.html
└── js
├── bootstrap.js
├── bootstrap.min.js
├── jquery.easing.min.js
├── jquery.js
└── scrolling-nav.js

2 directories, 9 files
```

From here we will start to use git's commands, firsly starting the local repository
by typing on the shell.

```bash
$ git init
```

so the the shell will response with a message saying:
```bash
Initialized empty Git repository in /fulvio/projects/fulvio_page/.git/
```

Basically said that with already created an empty Git repository - ```.git```
which it's hidded by default, this directory contain couples of file that will
help us to handle our reposities, lets make a look inside this famous dir just 
to know what the command generated.

```bash
$ cd .git/
```
```bash
$ pwd
/fulvio/projects/fulvio_page/.git
```
```bash
$ tree
.
├── HEAD
├── config
├── hooks
│   ├── ctags -> /Users/fulvio/dotfiles/git_template/hooks/ctags
│   ├── post-checkout -> /Users/fulvio/dotfiles/git_template/hooks/post-checkout
│   ├── post-commit -> /Users/fulvio/dotfiles/git_template/hooks/post-commit
│   ├── post-merge -> /Users/fulvio/dotfiles/git_template/hooks/post-merge
│   ├── post-rewrite -> /Users/fulvio/dotfiles/git_template/hooks/post-rewrite
│   ├── pre-commit -> /Users/fulvio/dotfiles/git_template/hooks/pre-commit
│   └── prepare-commit-msg -> /Users/fulvio/dotfiles/git_template/hooks/prepare-commit-msg
├── info
│   └── exclude -> /Users/fulvio/dotfiles/git_template/info/exclude
├── objects
│   ├── info
│   └── pack
└── refs
├── heads
└── tags

8 directories, 10 files
```

Here is [more about ```git init```](https://goo.gl/j2Kg5R)

Ok! now we know what how to initizaliy a Git repository, but what we really need
its to push up to GitHub our website, and for achivie this first we have to
_clone_ our remote repo with the local one using the command `git remote` and
also we need the _remote url_ of the repo on GitHub.

```bash
$ git remote add origin git@github.com:fulvi0/my_page.git
```

After added the remote branch we can check if everything it's ok bit typing:

```bash
$ git remote -v
origin	git@github.com:fulvi0/my_page.git (fetch)
origin	git@github.com:fulvi0/my_page.git (push)
```
Note: the flag `-v` its **verbose** and show the remote url; [here more about
`git remote`](https://goo.gl/wGWIxx).

After got ready our remote reposity on our local one lest see the status of our
local repo added then the the _commit_ branch and _commit_ the files.

```bash
$ git status
On branch master

Initial commit

Untracked files:
(use "git add <file>..." to include in what will be committed)

css/
fonts/
index.html
js/

nothing added to commit but untracked files present (use "git add" to track)
```
Then will add those files untacked to our _Master_ branch, but we are missing
some step before add the files and is **fetch** and **pull** from the remote
repo, in this case its because we were setting up the repository in GitHub we
added a `README.md` file or local repo; if you skip this step you will get an 
error message saing `fatal: Not possible to fast-forward, aborting.`

To avoid such error lets run the following commands on the terminal.

```bash
$ git fetch && git pull origin master
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From github.com:fulvi0/my_page
* [new branch]      master     -> origin/master
From github.com:fulvi0/my_page
* branch            master     -> FETCH_HEAD
```

Now we can add all the files to the _master_ branch

```bash
$ git add --all
```

Lets check the status again for see the differente after added the files.

```bash
$ git status
On branch master

Initial commit

Changes to be committed:
(use "git rm --cached <file>..." to unstage)

new file:   css/bootstrap.css
new file:   css/bootstrap.min.css
new file:   css/scrolling-nav.css
new file:   fonts/glyphicons-halflings-regular.eot
new file:   fonts/glyphicons-halflings-regular.svg
new file:   fonts/glyphicons-halflings-regular.ttf
new file:   fonts/glyphicons-halflings-regular.woff
new file:   fonts/glyphicons-halflings-regular.woff2
new file:   index.html
new file:   js/bootstrap.js
new file:   js/bootstrap.min.js
new file:   js/jquery.easing.min.js
new file:   js/jquery.js
new file:   js/scrolling-nav.js
```

And we'll _commit_ and add a message to identify our changes using the command
[`git commit`](https://goo.gl/bUeeZh).

```bash
$ git commit -m "I will push my webpage source code to github"
  [master (root-commit) 5d9f73e] I will push my webpage source code to github
14 files changed, 9706 insertions(+)
  create mode 100755 css/bootstrap.css
  create mode 100755 css/bootstrap.min.css
  create mode 100755 css/scrolling-nav.css
  create mode 100755 fonts/glyphicons-halflings-regular.eot
  create mode 100755 fonts/glyphicons-halflings-regular.svg
  create mode 100755 fonts/glyphicons-halflings-regular.ttf
  create mode 100755 fonts/glyphicons-halflings-regular.woff
  create mode 100755 fonts/glyphicons-halflings-regular.woff2
  create mode 100755 index.html
  create mode 100755 js/bootstrap.js
  create mode 100755 js/bootstrap.min.js
  create mode 100755 js/jquery.easing.min.js
  create mode 100755 js/jquery.js
  create mode 100755 js/scrolling-nav.js
  ```
  Before _push_ to our repo on GitHub we have to



  Lets push this commits changes using `git push`

  ```bash
  $
  ```
