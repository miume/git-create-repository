##github常见操作和常见错误
###1. fatal: remote origin already exists.   
解决办法：先输入 git remote rm origin
        再输入 git remote add origin git@github.com:miume/gitdemo.git
          
      
###2.fatal: Could not read from remote repository.

      解决办法：删除当前key，然后重新生成key