# Auto Feeds
> 利用 Github Actions 自动更新 feeds 仓库

### 使用须知
1. 这个 Action 用来搭建 OpenWrt 的 feeds 仓库，主要结构如下

        tree -a
        .
        ├── .github
        │   └── workflows
        │       └── main.yml    # Action 本体
        ├── main.sh             # 源码拉取脚本
        └── README.md

2. `main.sh` 记录了收集的软件包源码地址，以及一些清理操作
3. `main.yml` 定义了 Actions 的基本信息，以下列出需要修改的信息

        # 环境变量定义
        env:
        TZ: Asia/Shanghai                               # 时区设置
        REPO_NAME: oneko                                # 推送的仓库名
        USER_NAME: KimJungWha                           # 推送的用户
        USER_PASSWORD: ${{ secrets.USER_PASSWORD }}     # 推送的用户密码
        # 不太清楚为什么，使用第三方的 actions、ssh、个人令牌的方式推送会出现例如 403、读不到用户名/密码等错误，因此只能使用帐号密码的方式推送

4. 如何使用?
    * 需要先新建一个仓库，例如 [oneko](https://github.com/KimJungWha/oneko)
    * fork 本仓库
    * 修改 `main.yml` 里的定义
    * 在仓库的设置里添加 `Secret`

            Name: USER_PASSWORD
            Value: 你的 Github 密码

5. 如何运行这个 Actions?
    * 这个 Actions 支持多种运行方式，包括不限于
    * 点 star 运行
    * Actions 页面手动运行
    * commit 运行
    * 定时运行
    * ...

### 结尾
非常感谢 [kenzok8](https://github.com/kenzok8) 大佬，他的 [项目](https://github.com/kenzok8/small_action) 给了我很多灵感和帮助 (基本抄都是 dalao 的)