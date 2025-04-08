# cs156cmd
Commands that are frequently used in CS156 labs

1.log into csil	

ssh username@csil.cs.ucsb.edu

2.log into dokku

ssh dokku-xx.cs.ucsb.edu

3.clone a repo

git clone url  作用： 从远程仓库 克隆整个项目（包括代码、提交历史等） 到本地。
适用场景： 第一次从远程仓库获取项目代码时。

4.pull from a remote repo to local branch

git pull origin main  作用： 从远程仓库的 main 分支拉取最新代码，并合并到当前本地分支中。
适用场景： 你已经在本地有这个仓库了，想获取远程仓库中的最新代码更新

5.remote lookup
git remote -v
(这个命令会列出所有当前项目中配置的远程仓库及其对应的 URL，并且显示每个远程仓库的 fetch 和 push 地址。)

6.add remote repo
git remote add starter paste-url-here
(给当前 Git 仓库添加一个新的远程仓库，名字叫 starter，地址是 paste-url-here。)

7.pull starter code into your repo
git checkout -b main   (创建一个名为 main 的新分支，并立即切换到这个分支上。)
git pull starter main
git push origin main

8.start webapp on localhost(http://localhost:8080)
mvn compile
mvn test
mvn spring-boot:run
9.
