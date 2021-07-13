### 开发中常用 git 命令

[参考](https://www.yiibai.com/git)

---

**1.基于远程分之创建本地分支（不关联远程分支，适合 bugfix 提 pr）**

```javascript
git fetch butter 远程分支名:本地分支名
```

**2.基于远程分之创建本地分支（默认会关联）**

```javascript
//  example:git checkout -b bugfix0713 butter/master
git checkout -b 本地分支名 远程分支名
```

**3.以 rebase 方式 pull 远程代码**

```javascript
git pull --rebase butter 远程分支名:本地分支名
```

**4.以 rebase 方式合并代码，使得提交线更加清晰**

```javascript
git rebase -i butter/远程分支名
```

**5.本地删除远程分支**

```javascript
git push origin --delete 0622
```

**6.移除 SourceTree 无用远程分支**

```javascript
- git remote show origin
- git remote prune origin
- 重启sourcetree
```

**7.删除本地和远程 tag 更新包**

```javascript
- git tag -d v3.90.6 // 删除本地tag
- git push upstream :refs/tags/v3.90.6 // 删除远程tag
- git reset --hard xxx // 本地回到某次提交
- git push -f upstream master// 强制推送到远程的分支
```
