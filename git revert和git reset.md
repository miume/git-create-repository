## git深入学习

### git reset 和git revert的区别

- ### git rest有两个参数

  - #### git reset --soft [--hard] commitID

    - ##### git reset --soft commitID：表示这个commitID之后的所有commit修改都会重新退回到git缓存区中

    - ##### git reset --hard commitID（只针对本地操作）：git会直接丢弃这个commitID之后的所有修改

    - ##### 问题：git reset --hard只针对本地操作，不会对远程服务器进行同样操作

    - ##### 解决：git revert commitID（撤销对某个commit的提交），生成一次新的commit冲抵原来的commit

  - ### head：当前分支的最近一次提交后的版本（代表最新的版本）

    - head^：上一个版本
    - head^^：上上一个版本
    - head~x：表示距离最新版本的之前几个版本