# git configuration

```
git config --global user.name "username"
git config --global user.email "email"
```

# initialise a directory

```
git init
git add .
git commit -m "Initial commit"
git remote add origin <repo url>
git push -u origin master
```

### Configure git to use an ssh connection

```shell
git remote set-url origin git@github.com:user/repo.git
```
