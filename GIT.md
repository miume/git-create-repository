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
```



## 远程仓库



## 忽略文件 .gitignore

- 忽略文件中的空行或以#开始的行将会被忽略
- *星号代表任意多个字符，问好（？）代表一个字符，方括号[abc]代表可选字符范围，大括号{string1,string2}代表可选的字符串等
- 感叹号（!）表示例外规则，将不被忽略
- /temp：仅忽略项目根目录下的文件，不包括其它目录temp ** ？？？？？？**
- build/ ：表示忽略build/目录下的所有文件

###工作区与暂存区交互

###暂存区和本地仓库交互

###本地仓库和远程仓库交互
