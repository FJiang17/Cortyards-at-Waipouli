# 打勾同步设置（一次性，约 3 分钟）

## 1. 把两个文件推到仓库 main 分支

- `waipouli_calendar_v8.html`（覆盖旧的）
- `items-done.json`（新文件，空的起始状态）

## 2. 建 GitHub token

https://github.com/settings/personal-access-tokens/new

- **Token name**: `waipouli-calendar`
- **Expiration**: 90 天（到期再建一个，换掉即可）
- **Repository access**: Only select repositories → `Cortyards-at-Waipouli`
- **Permissions** → Repository permissions → **Contents: Read and write**
  （只给这一项，其余全部 No access）
- Generate token，复制 `github_pat_...`

## 3. 把 token 交给日历

打开日历 → 工具栏 ☑ → **Add editing token** → 粘贴 → OK

存在你浏览器里，以后这台设备直接能改。

## 4. 换设备 / 给别人编辑权

☑ → **Copy editing link**，得到 `...cal.html#t=<token>`。
在新设备打开一次，token 自动存下，并立刻从地址栏抹掉。

**这个链接等于密码**，别截图、别发群里。

## 查看的人

什么都不用做 —— 普通链接打开就能看到最新勾选状态，页面每 2 分钟
自动刷新一次，切回标签页也会刷新。他们点不动（显示"View only"）。

## 状态指示（☑ 按钮上的小圆点）

| 符号 | 含义 |
|---|---|
| ● 绿 | 已保存到 GitHub |
| ◌ 蓝 | 正在保存 |
| ◉ 灰 | 只读（没 token） |
| ○ 橙 + 数字 | 离线，N 条改动排队中，联网自动补传 |
| ▲ 红 | token 被拒（过期或权限不对）|

## 注意

仓库是 public，所以 `items-done.json` 的内容任何人都能看到。
里面只有 "哪个 unit 的哪件东西装好了"，没有敏感信息。
如果不想公开，把仓库转成 private —— 代码不用改，但查看的人
也需要 token 了。
