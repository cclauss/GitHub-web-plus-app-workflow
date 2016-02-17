Here is a workflow for forking, then creating a pull request from within python.  Requires PyGitHub
```
from github import Github
g = Github(user,pass)
u = g.get_user()
other_repo = g.get_repo('cclauss/GitHub-web-plus-app-workflow')
mine = other_repo.fork()
# now modify something 
other_repo.create_pull(title='test pull, feel free to ignore',body='Here is an alternate method, using pygithub', base='master',head='jsbain:master')
```
