# 新功能发布如何同步全公司

## 主要三个阶段：

* 开发前
* 开发中
* 开发完

## 需要同步的功能：

符合以下条件之一的功能：

1. 指挥官任务相关
2. 开发需要至少一周时间
3. 上线后超过 50% 的 Users 会发现

## 同步：

* 负责同步的人：Project Owner
* 同步方式：使用 Feature Roadmap Trello board

### 开发团队 Roadmap

开发团队的 Roadmap目前采用 trello 方式管理，分为：Web Roadmap 以及 Api & Client Roadmap。目的是让所有团队成员都知道最新的开发进度。

#### 开发进度具体包括：

* 有哪些新功能要上线 （What）
* 在什么时候上线 （When）
* 现在进度如何 （How is it）

#### 如何通过Roadmap了解开发进度

* Roadmap 只列出大功能，不列小功能
* 在某个项目状态变更时会有 Slack 通知打到 All-Hands 确保大家得知最新讯息，所以 你不需要随时关注这个 Roadmap

想知道所有的功能现在的进度，根据你的需求，有几种做法：

* 直接看看板
* 点击右上方“日历”按钮得知每个新功能预期的上线时间
* 点击右上方的“显示菜单”-> “筛选卡片”来筛选你想要看到的功能

想知道为什么有功能 Delay 了，你可以：

* 点击你想知道的功能，进去看留言
* 每个功能都会有一个负责人，如果你在这里找不到为什么 Delay 的资讯，请联系负责人，负责人有义务更新资讯

### 开发团队如何使用Roadmap

开发团队的 Roadmap目前采用 trello 方式管理，分为：Web Roadmap 以及 Api & Client Roadmap。


#### 谁负责更新 Roadmap（Who）

每个功能 / Client 都会有一个负责人，负责人需要及时更新 Roadmap

#### 哪些东西要放到 Roadmap（What）

满足以下任何一点的功能：

* 产品指挥官会议提到的功能
* 会直接影响用户的新功能
* 要开发超过三天的功能
* 团队成员都很关注的功能

另外 各 Client 负责人需要在 Todo List 下更新未来 两到三周的开发计划
指挥官会议后，产品负责人会将会议中提到的 web 部分更新至 Web Roadmap

#### 什么时候该更新 Roadmap（When）

* 有新功能的时候 => Roadmap Todo 里新增 Card
* 功能上线了 => 将 Card 更新至相应的已上线列表里，如果是web功能，更新至五十三周已上线
* 时程 Delay 了 => 在 Roadmap Card以及相应的 redmine 票里中留言告知团队为什么 Delay，并更新预估时间

#### 怎么新增 Roadmap（How）

如果你是 Api & Client 团队

* 打上标题 标题为 版本号+主要功能，如 「iOS-OTC 广告管理」
* 加上正确的 Label:  根据 client 分类，如 「iOS-OTC」
* 在详情里添加具体 feature/bug/优化内容
* 估算预计开发的时间，如果无法估算就设定为一个 Sprint (一周)
* 在 Roadmap 的描述中贴上主要的 Readmine 连结
* Assign 成为为自己，代表你是负责人
* 这样就完成了

如果你是 web 团队

* 打上标题 标题为 Web+主要功能，如 「Web  周年庆活动」
* 加上正确的 Label：根据周分类，如「五十三周」
* 在详情中添加具体 feature/bug/优化内容
* 估算预计开发的时间，如果无法估算就设定为一周
* 在 Roadmap 的描述中贴上主要的 Readmine 连结
* Assign 成为为自己，代表你是负责人
* 这样就完成了
