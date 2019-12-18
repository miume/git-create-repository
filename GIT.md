##工作区

- ##### 电脑里的本地项目

  ```js
  /**会用暂存区全部或指定的文件替换工作区的文件
  * 会清除未提交到暂存区的改动
  */
  git checkout -- [file] 
  git checkout .
  
  /**会用HEAD指向的master分支中的全部或者部分文件替换暂存区和以及工作区未添加暂存区的改动*/
  git checkout HEAD .
  git checkout HEAD <file>
  
  
  /**查看文件修改后的差异(工作区和暂存区文件的差异)*/
  git diff [file]
  
  ```

/**删除未跟踪的文件*/
  rm file1
  ```
  

## 版本库（工作区有一个隐藏目录.git，属于Git版本库）

- ##### 暂存区stage：git自动创建第一个分支master，以及指向master的一个指针HEAD

  ```js
  /**将untracked状态文件到暂存区*/
  git add [file1] [file2]
  git add [dir]
  git add .
  
  
  /**从暂存区删除文件，而工作起则不做出改变*/
  git reset HEAD [file]
  git rm --cashed [file]
  
  /**不仅将文件从暂存区删除，并且也从工作区删除*/
  git rm [file] -f   
  
  /**修改文件名称 将a.text名称修改为b.text*/
  git mv a.text b.text
  
  ```

  

## 本地仓库

```js
/**将暂存区内容提交到本地仓库*/
git commit -m [message]
git commit [file1] [file2] -m [message]

/**提交工作区自上次commit之后的变化，直接到仓库区，（对新文件无效）*/
git commit -a

/**使用一次新的commit，替代上一次提交
* 如果代码没有任何变化，则用来改写上一次commit的提交信息
*/
git commit --amend -m [message]

/**若提交过后发现有个文件改错了,可以修改file文件*/
git commit [file] --amend 
git commit --amend  //修改提交说明

/**撤销上一次提交commit*/
git reset --hard HEAD~1

/**撤销提交 回滚修改，重新生成一个新的提交*/
git revert <commitID>
  
/**撤销本地仓库的提交
* --hard:撤销并删除相应的更新
* --soft:撤销相应的更新，把这些更新的内容放到暂存区stage中
*/
git reset --hard HEAD^
git reset --hard HEAD~1
git reset --hard commitID

/**想要恢复被撤销的提交*/
git reflog    //查看仓库中所有的分支的所有更新记录
git  reset --hard commitID

/**删除已提交的文件(删除工作区和暂存区中的文件)*/
git rm -f [file]

```



## 远程仓库



## 忽略文件 .gitignore

- 忽略文件中的空行或以#开始的行将会被忽略
- *星号代表任意多个字符，问好（？）代表一个字符，方括号[abc]代表可选字符范围，大括号{string1,string2}代表可选的字符串等
- 感叹号（!）表示例外规则，将不被忽略
- /temp：仅忽略项目根目录下的文件，不包括其它目录temp ** ？？？？？？**
- build/ ：表示忽略build/目录下的所有文件

## 重要Git命令

```js
/**新建一个分支，与指定的远程分支建立追踪关系*/
git branch --track [branch][remote-branch]

git branch --set-upstream [branch][remote-branch]

/**选择一个commit，合并进当前分支*/
git cherry-pick [commit]

/**删除远程分支*/
git push origin --delete [branch-name]
git branch -dr [remote/branch]

/**将工作区的修改暂时放到暂存区*/
git shash
git stash pop   //将暂存区的内容恢复到工作区
```



## 新建分支与切换分支

- 每次提交，Git都把它们串成一条时间线，这个时间线就是一个分支

- 主分支master分支，Head指向当前分支，master指向提交

  ![img](https://img2018.cnblogs.com/blog/63651/201809/63651-20180920210647291-1528543055.png)

  - Git创建一个分支很快，增加一个dev指针，改改HEAD的指向，工作区的文件都没有任何变化

    ```js
    git checkout -b new-branch
    ```

    

![git-br-dev-fd](https://www.liaoxuefeng.com/files/attachments/0013849088235627813efe7649b4f008900e5365bb72323000/0)

- 合并分支：将master指向dev的当前提交

  ```js
  git merge new-branch
  ```

  ![git-br-ff-merge](https://www.liaoxuefeng.com/files/attachments/00138490883510324231a837e5d4aee844d3e4692ba50f5000/0)

- 删除分支：删除dev指针即可

  ```js
  git branch -d new-branch
  ```

  ![git-br-rm](https://www.liaoxuefeng.com/files/attachments/001384908867187c83ca970bf0f46efa19badad99c40235000/0)



## 创建项目

```js
mkdir project
cd project
git init
echo '#project' >> README.md
git add .
git commit -m "first commit"
git remote add origin url.    //添加远程主机
git push -u origin master   //第一次提交 -u
```



## git clone克隆

```js
/**git clone支持多种协议
* 除了https，还支持SSH、Git、本地文件协议等
*/
git clone url
```



[https://www.cnblogs.com/best/p/7474442.html]:参考文章

