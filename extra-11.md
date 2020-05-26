# 开票解票 Workflow

## 开票

* 做 功能 / 解bug / refactor 前都需要先开票
* 主旨说明要做的事情，概述说明细节，如果遇到可图片说明的事项最好附上图片
* 如果要做的事情包含很多细节，请将各细节分拆成子票，不可在一张票上做很多事情

## Redmine 票状态代表的意义：

* New - 还没开始做的票。
* Implementing - 正在做的票。
* Responded - 正在讨论中的票。
* Code review - 做完正在等待 code review 的票。
* Solved - code review 完准备要 release 的票 或是 已经 release 了但有留下注解给做票的人。
* Done & Close - 已经完成的票。
* Wontfix - 不需要解决的问题。

![](https://d.pr/i/I3VJkV+)


## 解票

* 开始解票时将票状态改为 Implementing
* 在解票的时候应该每做一个段落都在票内叙述进度
* Project 内建立 branch t+票号 (例如 http://redmine.mycompany.com/issues/9345 则建立 t9345)
* Push 上 Github 后开 Pull request
* PR 名称为 branch 名字加叙述 (例如 T19345 客服后台可以给商家账号订单退款)
* 开启 PR 后将 PR 网址贴到 Redmine 票上贴上截图说明结果，并将票的状态改为 Code Review
PR 跟着票，只要票还在实作的人手中 PR 都有可能会更新。所以虽然 GitHub 上有 open 的 PR ，但只有在票被标记为 code review 并 assign 回主要管理的人的时候才 merge PR
* 如果 PR 需要 review 但是不要被马上 merge：
  - redmine 票上注明 “Don‘t merge”,   PR 上贴 "Don‘t merge" 的 label
  - 如果有需要被 merge 的时间，请在票上注明，pr Risks里写明时间

### 示范流程：

分为三个角色：实作者、Reviewer、Deployer

ex: 实作者 Jason 解完票 -> 改成 code review 状态给 reviewer Nick -> Nick review 完没问题改成 solved 给 deployer Willy -> deploy

### 解票时遇到问题处理方式：

* 遇到问题卡住时，先将子票开出来，详细叙述要做的东西、遇到的状况，让同事能在最短时间内了解状况并协助
* 解票卡住时，在确定无法解决并会拖延到完成该张票的时程，应该立刻向同事求救，以免造成更大的影响

## Github branch


* master: 随时可以 deploy，只有 develop 可以 merge 到 master
* develop: 开发主 branch，所有 PR 都 merge 到 develop
* t12345: 开发用的 branch，t+ redmine 票号，开 PR merge 到 develop

PR 的顺序应该是 t12345 -> develop; develop -> master

### 几个原则

1. 永远不直接 commit master
2. 不直接 commit 到 develop (除非 hotfix, 由 senior 处理)


## Pull Request

PR title 应该写清票号和具体解决的问题，例如 `t26410 - 完成新版币币所有的功能点`, 详细内容应该参照如下模板(一般项目中已包含 .github/PULL_REQUEST_TEMPLATE.md )。PR 说明 至少包括redmine 票号和截图，以及相关的 migration 和 rake task。

![](https://d.pr/i/diGe4h+)



### Pull Request Label

#### skip-update-notification：

当 repo master 合并分支需注意，所有的合并都会 push message 到 slack 中 `website-updates` 频道， 除非把 label 设置为  `skip-update-notification`，


#### Don‘t merge:
若不希望PR 马上被 merge，贴上  "Don‘t merge" 的 label


#### App Impact：

如果这个 pr 会对 app 产生影响，请加上App Impact

 `zapier-bug-fixes'， `zapier-features`，`zapier-improvements` :
这三个标签分辨是：bug修复，新功能，原有功能改进。
若 PR 加上 `zapier-bug-fixes'， `zapier-features`，`zapier-improvements` 相关 label，则这条 PR 会被加入到 google docs，以方便运营人员整理周报。
