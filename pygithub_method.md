Here is a workflow making use of [pygithub](https://github.com/PyGitHub/PyGithub.git)

1) Create new repo:

```python
from github import Github
g = Github(user,pass)   #or, g=Github(token) where token is personal Oauth token
u= g.get_user()
my_new_repo=u.create_repo('new_repo')
# then use stash to pull from github.
```

2)  Fork an existing repo

```python
other_repo = g.get_repo('cclauss/GitHub-web-plus-app-workflow')
mine=u.fork_repo(other_repo)
```

3) Create a pull request (after using stash to push to your own github)
```python
# call create_pull on the repo you want to pull INTO.  base = name of branch in that repo.  head = name of YOUR repo, as user:branch
other_repo.create_pull(title='A web-free example, using only python',
                       body='here is a simple example using pygithub to fork a repo, then create a pull request',
                       base='master',
                       head='jsbain:master')
```

