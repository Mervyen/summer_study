> 场景：取消最后一次commit

基本的知识可以观看[git总结](https://mervyen.github.io/2020/08/21/git%E6%80%BB%E7%BB%93/)

## 1.git reset --xxx HEAD~ 指令

### 1.1 --soft

> 取消commit操作，保留working tree和index的代码

`git reset HEAD~1`执行之后，会重置为上一次提交,且撤回的提交文件，其状态发生改变，变成**unCommit**状态。具体操作如下：

> 重置local repository为上一次提交的状态
>
> **不重置**Index
>
> **不重置**working tree

如图所示

![](/images/git_reset--soft.png)

### 1.2 --mixed

> 取消add和commit操作，但保留working tree的代码

该命令是 `git reset`的默认，`git reset HEAD~1`执行之后，会重置为上一次提交，且撤回的提交文件，其状态发生改变，变成**unstaged**。具体操作如下:

> 重置local repository为上一次提交的状态
>
> 重置Index为上一次的提交状态
>
> **不重置**working tree

如图所示

![](/images/git_reset--mixed.png)

### 1.3 --hard

> 取消add和commit操作，且将提交的代码从working tree删除

`git reset HEAD~1`执行之后，会重置所有的东西。ps：如果你本地有unstage，uncommit的东西，一样会被重置

>
> 重置local repository为上一次提交的状态
>
> 重置Index为上一次的提交状态
>
> 重置working tree为上一次的提交状态
