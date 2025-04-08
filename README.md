# Description
Commands that are frequently used in CS156 labs

# 1.log into csil	

ssh username@csil.cs.ucsb.edu

# 2.log into dokku

ssh dokku-xx.cs.ucsb.edu

# 3.clone a repo

git clone url  

作用： 从远程仓库 克隆整个项目（包括代码、提交历史等） 到本地。
适用场景： 第一次从远程仓库获取项目代码时。

# 4.pull from a remote repo to local branch

git pull origin main  

作用： 从远程仓库的 main 分支拉取最新代码，并合并到当前本地分支中。
适用场景： 你已经在本地有这个仓库了，想获取远程仓库中的最新代码更新

# 5.remote lookup

git remote -v

这个命令会列出所有当前项目中配置的远程仓库及其对应的 URL，并且显示每个远程仓库的 fetch 和 push 地址。

# 6.add remote repo

git remote add starter paste-url-here

给当前 Git 仓库添加一个新的远程仓库，名字叫 starter，地址是 paste-url-here。

# 7.pull starter code into your repo

git checkout -b main   (创建一个名为 main 的新分支，并立即切换到这个分支上。)

git pull starter main

git push origin main

# 8.start webapp on localhost(http://localhost:8080)

mvn compile

mvn test

mvn spring-boot:run

# 9.deploy app to dokku

dokku apps:create app-name (create the app)

dokku git:sync your-app-name https://github.com/ucsb-cs156-s24/your-repo-name.git branch-to-deploy(To set the git branch that your dokku app will deploy on its next build, do this, using the https link for your public repo. )

(For example: dokku git:sync jpa01-cgaucho https://github.com/ucsb-cs156-s25/jpa02-cgaucho.git main)

dokku ps:rebuild app-name (to deploy)

(add https support)

dokku letsencrypt:set app-name email cgaucho@ucsb.edu

dokku letsencrypt:enable app-name

**To redeploy any time the repo changes (otherwise changes in the repo don’t affect the running app):

1.Re-sync the app with git repo, main branch

dokku git:sync jpa02-yourGithubId https://github.com/ucsb-cs156-s25/jpa02-yourGithubId.git main

2.Re-deploy the http version of the app

dokku ps:rebuild jpa02-yourGithubId

app will be deployed to: https (secure): https://jpaxx-yourGithubId.dokku-xx.cs.ucsb.edu/

# 10.some dokku commands

1.dokku apps:list

This shows all of the apps on your dokku instance.
Note that you share your dokku instance with all of the members of your team

2.dokku logs --tail jpa01-cgaucho

This shows the console output (including error messages and log messages) of your running app.
See what the app shows if you try to navigate to pages that exist, and pages that don’t exist (e.g. put /foobar in the url bar of the browser after your host url)

# 11.run the test suite

mvn test

使用 Maven 运行项目的测试阶段，执行 src/test/java 目录下的测试代码。

# 12.view jacoco report (line/branch coverage)

mvn test jacoco:report

open target/site/jacoco/index.html

check for line and branch coverage in Java and see codes not touched my "mvn test"

# 13.review pitest report (mutation testing)

mvn test pitest:mutationCoverage

open target/pit-reports/index.html

# 14.update and commit the code to origin's main branch

git add .

git status

git commit -m "comments"

git push origin main

