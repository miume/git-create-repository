问题：提交代码时commit message不对或者有误该怎么修改？

- 1、修改最近一次的提交信息

```js
/**1、git commit --ammend可以修改最后一次commit的信息（未push的注释）*/
git commit --ammend 
```

- 2、修改历史的提交信息

```js
git log               //查看提交记录
git rebase -i HEAD~3  //修改最近三次的信息
```

