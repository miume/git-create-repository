##学习git
git branch
git checkout master
git tag v1.0
git tag
git show tag v1.0

git tag v0.9 commitID

git tag -a v1.1 -m "指定标签内容"

git pull origin v1.1   //将标签v1.1推送到远程
git pull origin --tags //将本地所有未推送标签推送到远程

git tag -d v1.1
git push origin :refs/tags/v1.1  //删除远程标签（先删除本地，再删除远程）



