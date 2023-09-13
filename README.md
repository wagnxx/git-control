# git-control

### 简介


- git 命令操作

1. 版本控制

- .ignore
- stash
  + git stash save '修改了xx'   // 保存一个进度
  + git stash apply stash@{0}  // 恢复一个进度
  + git stash drop stash@{0}   // 删除这个进度

- log
  - git log --oneline   --author='myanme' --before='2018-09-22'  // (1 week / 3 days)
  - git log --oneline --grep='index'
  - git log --oneline --graph --decorate --all -10 

-  branch
  + git brach 'new brach'
  + git checkout newbrach
  + git diff main..mobile-feature (index.html) // 两个分支的区别
  +  git branch -m bugfix bugfix-1   // 重命名分支  -m(move)
  + git branch -d bugfix-1           // 删除分支

- merge
  - git merge mobile-feature   // 当前分支在main ,把mobile-feture合并的main  fast foward
  - 有冲突的情况,
  + git merge mobile-featre
  + 解决冲突
  + git commit                // Merge branch 'mobile-feature' into main

- remote //远程修改
  + git branch -r  // 查看远程分支  
  + git push origin mobile-feature 

  + git fetch
  + github 创建 pull request,选择好分支 send pullrequest
  + github 接受方 merge pull request ,confirm
  + 添加贡献者,setting-->collaboration add xxx

- tag
  +   git tag   // list
  + git tag v0.1
  + git tag -a v0.1 -m '20220304'
  + git tag -a v0.0333df33 -m 'init'
  + git show v0.0
  + git tag -d v0.0   // 删除
  + git push origin v0.1
  + git push --tags

## GIT lint

### git hooks
1. set customer hooks dir (缺点，必须的执行)：
```bash
git config 'core.hooksPath' .customGitHooks
```
2. create hook file, eg: pre-commit

### Husky
- create a "core.hooksPath" dir,
### lint-staged
- config husky hook shell file condition