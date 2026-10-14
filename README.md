# public-pages

公开 HTML 内容页（解释页 / 报告 / 可视化），发布在 GitHub Pages。

**站点：** https://argsno.github.io/public-pages/

## 这个仓库是什么

存放一切**可以公开**的网页内容。当有人（或 agent）说「用公开的 HTML 解释一下 X」时，
产出物就落在这里，而不是聊天里发附件。

## 内容红线

本仓库是 **public**，任何提交都视为永久公开（历史 commit 也可被检索）。
以下内容**禁止**进入本仓库：

| 类别 | 例子 |
|---|---|
| 凭据 | API key、token、密码、私钥、数据库连接串、cookie |
| 个人信息 | 真实姓名与联系方式的对应、住址、证件号、家属信息、聊天记录 |
| 内部资料 | 未公开的合同 / 财务 / 路线图、内网地址、私有系统拓扑 |
| 第三方受限内容 | 付费墙正文全文、未授权图片与字体 |

需要引用的，只保留**来源链接 + 概要**，不放全文。

## 目录结构

```
/
├── index.html            # 站点目录页，新增页面后同步更新
├── .nojekyll             # 关闭 Jekyll 处理
└── <主题>/index.html     # 单篇内容页（自包含，CSS/JS 内联，不依赖外部 CDN）
```

## 新增一个页面

1. 建目录 `mkdir <slug> && cd <slug>`
2. 写 `index.html`：自包含、响应式、首屏先给结论、能表格就表格
3. 更新根目录 `index.html` 的页面列表
4. `git add -A && git commit -m "add: <主题>" && git push`
5. 推送后约 1 分钟生效，地址为 `https://argsno.github.io/public-pages/<slug>/`

## 发布配置

- GitHub Pages，build type `legacy`，source = `main` 分支根目录 `/`
- 不需要 `gh-pages` 分支，也不需要 Actions workflow
