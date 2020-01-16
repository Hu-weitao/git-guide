## git与github的简单使用教程

### 一、创建仓库

1. 点击`new`，进入创建仓库页面

![img](https://imgkr.cn-bj.ufileos.com/4550e55f-76dd-416b-b6a7-38064abae594.png)

1. 对将要创建的仓库进行一些简单的设置

![img](https://imgkr.cn-bj.ufileos.com/813a2f15-4bdf-4eef-bdf6-7208904e1a1b.jpg)

![img](https://imgkr.cn-bj.ufileos.com/a9862109-54f3-4b24-ad0e-cc21cb25ee40.png)

1. 最后再点击`create repository`就可以了。

![img](https://imgkr.cn-bj.ufileos.com/e8debde1-eb75-4a18-b461-eddfa8862eb4.png)

1. 到这我们就创建好了一个仓库。

![img](https://imgkr.cn-bj.ufileos.com/d0ce4742-445b-45ed-bdde-0a275e0fa15a.png)

### 二、使用git clone，将仓库克隆到本地

在github上创建了一个仓库，怎么把它克隆(clone)到本地呢？这时候就需要使用git来进行管理与同步。首先你需要去git官网下载[git](https://git-scm.com/)，然后安装即可。接下来我们使用git命令将仓库克隆到本地。

1. 使用SSH

![img](https://imgkr.cn-bj.ufileos.com/f9c6c705-4f8a-4340-a115-67a6f51d706d.png)

![img](https://imgkr.cn-bj.ufileos.com/a8799471-ad6f-49be-98f8-9d4d428cc404.png)

1. 在本地创建git工作区

![img](https://imgkr.cn-bj.ufileos.com/5bac9906-1b23-4213-9c84-40b0ecb93729.png)

1. 进入git工作区，打开git命令窗口 ![img](https://imgkr.cn-bj.ufileos.com/bdc4c4d2-7627-41ad-896b-1a4178b8bc19.png)

![img](https://imgkr.cn-bj.ufileos.com/cfe39d60-fd58-43b3-8a03-8f2da1e14dcb.png)

1. 使用`git clone`命令将远端仓库克隆到本地工作区

命令格式：`git clone 刚刚复制的SSH口令`

![img](https://imgkr.cn-bj.ufileos.com/c56b80ce-281d-4f56-a7c7-90f760be26ea.png)

这时候我们再打开工作区看看是不是克隆进来了：

![img](https://imgkr.cn-bj.ufileos.com/894c9065-7ebe-4262-bf03-348275c319b0.png)

![img](https://imgkr.cn-bj.ufileos.com/418389ca-7e79-4cdf-8a4d-bffd6d094be8.png)

我们可以看看这个文件夹里的隐藏文件，查看步骤如下：

![img](https://imgkr.cn-bj.ufileos.com/95f07148-57c3-42b4-b9a1-a39f9efd716f.png)

![img](https://imgkr.cn-bj.ufileos.com/e9b04a3d-f054-4d93-bca7-7dd308f47405.png)

![img](https://imgkr.cn-bj.ufileos.com/6c6ee14a-57d5-4284-97bb-fa4d817f5b5d.png)

------

如果我们要修改或添加本地仓库里的一些文件，怎么更新到远端呢？它需要经过以下三个步骤：

> 1. 使用git add命令，将工作区的修改提交到暂存区
> 2. 使用git commit命令，将修改从暂存区提交到master分支
> 3. 使用git push命令，将修改从master分支推送到远端

![img](https://imgkr.cn-bj.ufileos.com/659eeefc-6804-41d1-b06b-1a97ab468ee2.png)

### 三、使用git add，提交修改至暂存区（index或stage）

1. 首先我们需要对git工作区做一些修改，例如创建一个新的文件`first.txt`

![img](https://imgkr.cn-bj.ufileos.com/a6506821-9e05-4714-81d8-eadeab47bf99.png)

1. 使用命令`git add 文件名`

![img](https://imgkr.cn-bj.ufileos.com/83b065be-607b-47e2-a7d7-d354ba4f2011.png)

1. 到这修改已经保存在暂存区了，我们可以使用`git status`命令查看当前状态

![img](https://imgkr.cn-bj.ufileos.com/aee08409-8807-4021-8f3c-50cf5136a322.png)

同时我们可以看到`user "git reset HEAD ..." to unstage`，意思是我们可以使用这个命令`git reset HEAD 文件名`，把刚才的提交撤回。这里就不再演示了，感兴趣的同学可以去试试。

### 四、使用git commit，提交修改至本地master分支

1. 命令格式为：`git commit -m "对此次提交的简单说明"`，`-m`中`m`的意思是`message`.

![img](https://imgkr.cn-bj.ufileos.com/9a5ee09c-fc17-4815-ba14-a2c6d7894541.png)

1. 再次使用`git status`查看当前状态

![img](https://imgkr.cn-bj.ufileos.com/87ca4e8c-bbc0-437f-a7a3-029a93f3913f.png)

### 五、使用git push，将本地修改

1. 使用`git push`命令就可以将本地master中的修改提交到远端master中去了。

![img](https://imgkr.cn-bj.ufileos.com/35959874-6258-4032-ad3a-772c9ee83d81.png)

1. 这时候我们刷新github看看

![img](https://imgkr.cn-bj.ufileos.com/b47036ef-9d38-44ad-80a8-91f22b841bd5.png)

------

到这，我们已经完成了git的一些基本操作，接下来我们补充一些比较常用的其它git命令。

### 查看操作`git log`,`git show commit id`

使用`git log`命令可以查看我们所有的commit日志

![img](https://imgkr.cn-bj.ufileos.com/f0c77095-9c63-4fd5-97ed-7ebc418df0af.png)

使用`git show commit id`命令可以查看一个commit的详细信息

![img](https://imgkr.cn-bj.ufileos.com/55d59e7e-ff9f-4e80-99c7-6146ccbab741.png)

### 回滚操作`git reset commit id`

在进行push之前我们可能会进行多次commit操作，有时候我们希望能够退回到某一次commit时的状态，这时我们可以使用`git reset commit id`命令。

但请注意，push完之后再reset是没用的，reset只对本地有效！

### 拉取操作`git pull`

有时候远端修改领先与我们的本地修改，因为一个仓库可能有多人同时在修改更新，如下图所示： ![img](https://imgkr.cn-bj.ufileos.com/73c52f06-328f-4c06-9ec1-3c7ebca70d46.png)

这时候我们就需要使用`git pull`命令来拉取远端的最新状态，同步到本地。

![img](https://imgkr.cn-bj.ufileos.com/7be50ef5-e296-49b6-a565-9fb332602e09.png)

------

好的，这就是这篇文章的所有内容了，有问题欢迎留言。