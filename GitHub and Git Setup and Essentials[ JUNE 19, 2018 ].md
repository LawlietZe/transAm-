
### GitHub 和 Git 的安装以及要点
作者: robinwieruch  
原文地址: https://www.robinwieruch.de/git-essential-commands/
  这个月，所有我的文章都由 TRUMPF Laser GmbH 所赞助。  
  我所在的工作德国公司正在生产环境中应用一个复杂的React 和 GraphQL 以及.NET tech 技术栈，去给他们来自世界各地的客户代带来高度可配置化的镭射设备用户界面。
  这些web应用一一运行在嵌入式系统中，同时作为原生应用运行在大量设备中。
    
   
当你开始使用Git的时候，它确实会让人望而却步。首先，分布式版本管理系统的想法和它的好处对于所有人并不是很清晰。其次，它有许多在命令行里用来控制Git的额外选项。
它确实会很吓人。
然而你不并不需要Git里有的复杂组合命令和选项, 对于我来说只有真正几个关键的命令在web开发中使用到。其他选项可能在处理复杂问题的时候才用到。  
在这篇文章中，我想给你简明的Git和Github的入门，如何开始使用以及怎么使用Git。之后我想展示我在十年web开发中使用的实用命令。它不是什么黑魔法，不必要对此害怕。


##### 为什么选择Git和GitHub
Git是一个版本控制系统，用于跟踪多台机器上的对文件以及文件夹, 大多数时候，这些文件和软件相关，比如说一些应用的源代码，不过它不仅仅用于软件相关的方面，
我已经遇到过许多作家以及内容营销人员使用Git去组织他们的文件以及用来与其他人合作。  
这些文件和文件夹都汇总成一个仓库(repository)，许多人可以在一个仓库上进行多人协作工作。
基本上来说，一个仓库是你项目在Git和GitHub的一个容器。
人们可以做一份仓库在本地拷贝，修改文件，以及同步所有的改动到远程仓库。
所有的合作者可以从远程仓库拉下来最新的改动到他们的本地仓库。  
然而Git是基于命令行来执行pull，modify 和 push 操作的，Github 是一个基于web的Git 平台，你可以在再Github上创建仓库，还可以与你在本地电脑上的项目
进行同步。之后，你可以在命令行使用Git去执行命令。  

##### 远程仓库 VS 本地仓库？
在Github里，一个人或者一个组织（例如：Facebook，Airbnb）可以拥有一个仓库。这些仓库可以有源代码、markdown文件、或者其他内容的文件或者整个文件项目结构。
除非整个仓库是私有的，每个人都有这个仓库的读取权限。它是一个远程仓库，因为它是你从本地机器上克隆分散出来的。  
当然每个人都能够从远程仓库复制一份代码到他们的本地。它就成为了一个本地仓库。你可以在你本地仓库上作出不在远程仓库上立刻显示出来的改动。你决定什么时候
你想把它合并到远程的仓库。
当地的仓库可以用来对源代码的测试、添加新的功能以及修复问题。最后这些本地的改动将会被merge回远程仓库。 然而，项目的参与者首先必须有对这个仓库的写入
权限。
分散的仓库，让所有具有读写权限的人作为一个小组在同一个仓库上协同合作成为了可能。一个本地的仓库是用来做更改展示，然而远程仓库是真理的唯一源泉。  
Github提供仓库私有化，但是你必须去升级支付你的Gihutb账号，一旦你的Github信息更新了，你就可以更新任何仓库只针对你可见。  

##### 开始使用Git 以及 GitHub
现在你了解了Git和GitHub了，你会在想怎么去使用它。在一堆教程和Github官网的指导下会非常简单。
首先，访问Github冰创建一个账号，然后你需要在电脑命令行上安装Git。每个操作系统都应该有一个默认命令行，但是你可以查看[开发者安装向导](https://www.robinwieruch.de/developer-setup/)
去了解我的安装配置。第三，我强烈推荐安装SSH在你的GitHub上，它不是必须的，但是保证你访问Github的安全，它可以解放当你在推送本地改动到远程时需要做的账号验证
等大量无聊的工作。  
最后，也是重要的一点，在GitHub上探索以及社交。你可以通过访问不同人和组织的简介来访问不同的仓库。你可以watch 和 star特定的仓库来获取这个仓库的更新以及
对它显示对它的赞赏。你甚至可以可以作为一个开源贡献者为仓库做出自己的贡献。   

##### 使用Git和GitHub初始化一个仓库
在开始的时候，你需要去创建一个Git仓库，你可以通过

    git init
在你本地的项目执行这个命令行操作。  
一个本地仓库有一个.git文件存放所有的信息。举个例子：commit 历史，仓库保存情况。一个 .gitignore文件可以增加忽略特定的文件，用于哪些不应该被加入
到远程的。被忽略的文件仅仅存在你本地的仓库。
    
    git init
    touch .gitignore
举个例子，你或许想要忽略.env文件，它用来存储一些你项目或者node_module/folder中的敏感环境变量，你可以这样做:
    
    .env
    node_module
当你使用了git init命令之后，你可以在Github上创建一个仓库。在这个仓库里，你可以给它命名，给它一些额外的描述以及license（例如MIT）。
不要使用单选框去增加一个README.md，让单选框先不要点击。接下来你可以获得链接你本地仓库到你远程仓库的指导。  
除此之外，你或许想在Github上添加一个README.MD文件，接下来在你的仓库里展示它。基本上这是初始化一个git项目你所需要做的事情，增加.gitignore文件，
把它连接到远程，增加changes 并执行 add, commit,最后push到序列中，你接下来在下一个部分会学会到更多这个序列的事情。  
除此之外，如果你想要一份远程仓库的拷贝，你可以通过 git clone <repository_url> 这个命令克隆一份代码到你的本地电脑上。  
在你连接本地仓库以及添加了added,committed,push操作并把你初始化的仓库推送到远程之后，你可以开始该表你的本地仓库，之后，你可以接着按照
add，commit，push操作顺序。更多关于这个可以在下一章节了解到。  
  
  ##### 推送你的改动
在过去十年间，我发现，我可以把在经常用的Github重要命令分解成为几个。这些关键命令对于我在web江湖上行走绰绰有余。  
一定拿你拥有了一个本地仓库，你想要去执行commit改动去代码库，每个commit都被看做你仓库的一个小小的里程碑，它会保存在Git历史里，你可以在命令行以及Github中
访问它。  
commit同时需要填写commit信息，你在之后的教程可以看到如何去写一个commit信息。除此之外，你的每一个commit操作都会自动的生产一个哈希值去标示它。你开始
并不需要管它，但是在后面你可以通过它去跳转到某一个特定的历史时间点去和其他commit做比较。  
只有在你的本地的commit通过push之后它才可以被远程仓库上去访问和查看。  
commit在你最终push到远程仓库之前一直存在你的本地，所以他们是不能被其他人访问和预览到到的。你可以在本地一次性集齐几个commit在你最终用push与它的
远程仓库里做同步。  
如何把你的改动推送到远程仓库呢？  
这里有一些重要的关键命令: add, commit , push操作。
首先，你可以为了下一个commit通过添加全部或者部分改动文件
```
git add. 
git add <path/to/file>
```
这些文件会由unstaged状态转化为stage状态. 你可以通过**git status**指令进行查看.当文件处于staged状态，表示它们可以被committed，同样的我们也可以
通过``` git reset HEAD <path/to/file>``` 指令把staged状态的文件还原回unstaged状态。 
其次，你可以commit操作已经处于staged状态的文件, commit操作写下相关操作的信息。有两种commit的方式。你可以通过简写commit命令去添加commit的信息
在同一行内:
```
git commit -m "<message>"
```
同时你可以用默认的commit操作去在多行文本中描述详细的commit操作的信息。
```
git commit 
```
接下来，命令行会打开一个默认的命令行编辑器。通常情况下，这个默认的命令行编辑器是vim，在vim中你可以输入你的commit信息。在这之后你可以保存和退出vim
通过 **:wq** 操作, 这个操作表示写入和退出，大多数情况下，使用commit简写就已经足够了，它写起来只有一句话的commit信息是绰绰有余的。  
现在在你进行第三步之前，你在本地已经有了多个commit。最后，第三步，你要推送所有的commits到远程仓库中，仅仅使用一句命令。
```
git push origin master
```
这三步是把你的改动从本地推送到远程的必要步骤。但是，当你与他人合作的时候，在你推送你的改变之前经常会有一些中间变动。这些变动可能是其他人已经推送改动
到远程仓库。因此你不得不在你推送自己的改动远程仓库之前把别人的改动先pull到本地。这非常的简单：
```
git pull origin master
```
然而， 我从来不直接的实用pull，取而代之的是，我使用rebase
git pull --rebase origin master  
pull rebase和 pull之间究竟有什么区别呢？ 一个基本的**git pull**会单纯的拉取所有的远程改动到你仓库的顶端(top)。然而使用一个**pull rebase**，
这是另一个方式。来自远程仓库的改动会先进入，接下来你的改动将会添加至顶端。简单说pull rebase有两个好处：

-它可以保持git history的有序性，因为你的改动总是最后添加的
-它帮助你解决冲突，如果你不小心有了冲突，你可以更轻松地调整你自己的改动。

如果你有改动不，不过还没commit，当你从远程仓库pull代码的时候，你会被通知应该先保存(stash)好你已经改动的文件。在你pull所有的改动之后，你可以
继续使用stash。在接下来的文章会讲到stash。
  ##### Git 状态，日记，历史
这里有三个关于你项目当前状态改动的命令。它们不会改变你项目，而是给你展示你项目的信息。举例子，你想要查看本地staged 和 unstaged的文件，你可以
输入
```
git status
```
你想要查看本地为unstage和当前commit的比较可以输入
```
git diff
```
你也可以随时查看commit的历史记录
```
git log
```
默认的**git log** 对大多数人没有帮助。每个commit占用了太多空间，不方便去查看历史。你可以使用下面的配置
```
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```
现在你可以用**git lg**代替git log, 试试看区别吧~
  ##### 分支
Git分支通常用来做多个用例时使用。想象你正在为你的项目添加新的功能，你想创建一个新分支去跟踪你的改动，让它独立于整个项目，更详细的来说：
从master分支独立出来。在你把分支merge到master分支之前，你可以review你的改动。  
另外一个用例是当你以开发小组的形式工作的时候，你想要给其他人在改进项目、增加新功能、修复Bug的时候能保持工作独立自由，因此，把代码从master分支
中做出分离开始很合理的，在这种情况下。**在创建branch的时候用什么关键的命令呢?** , 你可以创建一个分支，通过使用
```
git checkout -b <branch>
```
或者分支已经存在的情况下
```
git checkout <branch>
```
当分支是被其他合作的同事创建的，但是你本地仓库还不知道这个变动，你可以从远程fetch变动到本地，分支比较在远程已经被跟踪了。在这之后，你可以在你
本地切出一个分支。
```
git fetch
git checkout <branch>
```
一旦你在分支上，你可以从远程仓库pull下来最近的所有改动
```
git pull --rebase origin <branch>
```
现在你可以改动代码，``` git add .  ``` 和 ``` git commit ```来改动他们，最后接下来push它们到远程。不过不是把它们推送到远程master分支，
而是push到对应的分支
```
git push origin <branch>
```
现在你就是工作在所谓的“新功能分支”上了，其他开发者可以在这些分支上与你合作，最后merge一个 Pull Request到master分支。
  ##### Merge一个Pull Request
有的时候，你想要把一个分支merge到master分支上。你应该在merge之前使用Github操作界面去新建一个Pull Request(PR), Pull Request
操作能够有以下的帮助：助于讨论，合作review代码，提升代码质量以及跨合作者的知识分享。
在新建一个PR之前，我通常用一下几个方法切换出分支，更新所有变动并merge到我自己的代码中，同样从master分支中或许所有最近的改动，然后强制的push
所有变动去远程的本分支。
首先，当在master分支上时，更新master分支的最近改动：
```
git pull --rebase origin master
```
第二，切出分支:
```
git checkout <branch>
```
如果你还没有分支，在你准备切出分支之前,从远程fetch所有的分支在本地。
```
git fetch
git checkout <branch>
```
第三步，从远程拉取这个分支的最新改动。
```
git pull --rebase origin <branch>
```
第四步，从master分支top上rebase所有本地的变动:
```
git rebase master
```
最后一点，push所有的改动到远程分支
```
git push -f origin <branch>
```
这个分支和所有的协作人员的改动已经同步，包括你的改动和来自远程分支的改动。最后，当所有分支在远程仓库上已经更新，你可以在Github上点击
"Merge Pull Request"按钮
  ##### 解决冲突
有的时候，当你从远程pull拉去代码到本地，或者在master分支上rebase的时候，你会遇到冲突。冲突会在Git不能解决在同一文件上的多种改变。
这个在你与多人合作的时候经常发生。
举个例子，在你的分支上执行了```git rebase master```操作。命令行会告诉你，它停止工作了，然后给你展示冲突的文件。不必要恐慌，
你可以打开指定的文件并解决冲突。在文件中，你会看到改动被拆分开了: 从master分支的改动（HEAD）和来自你的分支，你会决定在这两个中哪一个是你想要的，以此来解决冲突。
在你解决所有冲突的时候你可以继续执行rebase:
```
git add .
git rebase --continue
```
如果你再次遇到冲突，你可以解决完毕之后再次执行这个命令。
  ##### Git Stash
  git stash操作往往是你在你想要永久或者暂时性丢弃一个改动的时候使用。
  ```
  git stash
  ```
  对于后者来说，当你只想暂时性的丢弃改动，在你正在进行其他任务的时候。举个例子，fix bug 或者 创建一个其他人的PR操作的时候。
  stash是一个堆（heap），你可以获取最新的stash去在你的本地仓库中使用
  ```
  git stash apply
  ```
  如果你不想丢弃所有的改动，你可以仅选择需要丢弃的文件，使用下面的操作替代:
  ```
  git checkout -- <path/to/file>
  ```
   ##### 删除分支
一旦你merge了 Pull Request, 你你通常会想删除远程和本地的分支
```
git branch -d <branch>
git push origin :<branch>
```
第一个命令删除你本地机器上的分支，第二个则是删除远程的分支。经常清理是一件好事，应该养成这样的好习惯。

   ##### 改动Rebase
我必须承认的是，这个命令不算是比较重要的，不过我我经常用它来组织我分支上的commit。 我喜欢在提出一个PR给别人之前有一个干净的分支。
把一个分支清洁意味着把commits形成一个有意义的顺序，或者是重写commit信息和'挤压'commit，挤压'commit意味着把多个commit合并成一个.
当你使用interact rebase的时候，你可以决定有多少commit 需要手动的调整.
```
git rebase -i HEAD˜<number>
```
在此之后，自从你改动过Git history,你需要强制push你的change.你一个强制Push回复该你远程仓库的git commits
```
git push -f origin master
```
通常来说你应该在使用强制push的时候谨慎一些，最好的是你在你的分支上进行处理，而不是在master分支上。在大型项目里，一个强制push在master分支上
是不被允许的。
   ##### Commit 信息守则
 当你正在和其他人合作或者是说你自己想要一个简洁的commit信息，你可以遵循git commit 信息守则.这里有几个守则，我从angular 社区里面找来了几个
 我经常遵循的守则:
- feat: 添加新特性
- fix : 一个bug修复
- docs: 一个文档更新
- style: 代码样式变动, 但是不改动实施细节
- refactor: 代码既不是修复bug，也不是新增功能
- perf: 优化性能的代码
- test: 测试你的代码
- chore: 对构建过程或辅助工具和库的更改
遵循这个语法: <type>(<scope>): <subject>
举个例子:
```
  git commit -m 'feat(todo-list) add filter feature
```
这个就是保持commit信息干净整洁的方法
   ##### Git简写
Git别称通常由built-in Git命令行来制作自己的Git 命令。别称允许你把Git 操作制作的更简洁的去组织他们。举个例子，你可以组织两行命令成一行。
   ##### Pull Request vs Issues
Pull Request(PR) 以及 issues 在多人合作的时候会用到。
当你组里一个人创建了一个分支去开发一个独立的功能的时候，这个分支最终会回归到一个PR。一个PR可以被你一个项目组里的人进行复查，你可以进行讨论，
  复查之后merge相关的代码，或者关掉这个PR。
  一个issue经常在一个分支和PR被创建之后打开。一个issue声明了在项目里的一个问题并激励大家去讨论。这些讨论最终可以形成一个作为解决问题的蓝图的说明书
 ，因此，你会创建一个基于这个issues的PR。issuer也可以被标记来保持对不同类型issuer的追踪。  
  最后，也可以私人使用PR以及issues,在一个人的项目仓库中，尽管你是一个人工作，你可以使用这些Github上的特性去保持问题和变动的更好跟踪。  
  这些Github和Git的关键点应该是你在这个领域开始时能够用到的所有东西了，你不应该被安装或者命令给难到。毕竟所有的命令被被拆解之后可以被用在几个重要的场景中。  
  几个重要的Git 命令：
  - git init
  - git clone
  - git add
  - git commit
  - git push
  - git pull -rebase
  - git fetch
  - git status
  - git log
  - git diff 
当然，还有很多的Git 命令(git bisect, git reflog) 等等你可以掌握。然后我觉得不经常用到它们。你可以一旦你需要它们再去预览它们，不必强行去记忆。
 
 
 扩展阅读:
 [The minimal Node.js with Babel Setup](https://www.robinwieruch.de/minimal-node-js-babel-setup/)
 [The minimal React + Webpack 4 + Babel Setup](https://www.robinwieruch.de/minimal-node-js-babel-setup/)
  
  
  
  
  

