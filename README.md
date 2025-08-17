# AutoGreen 2025可用

让你的 GitHub 自动保持提交状态 <b style="color:green">常绿</b>！

## 原理

**🔥(σ｀д′)σ🔥我找了一圈同类项目，找不到 Use this template 按钮，都没把仓库设置为模板仓库的，所以我只能自己写了**

使用 GitHub Actions 的定时任务功能，每隔一段时间自动执行 `jobs` 任务合集，就是 [ci.yml](https://github.com/QiYiJun/autogreen/blob/main/.github/workflows/ci.yml) 文件里的那个`jobs`）

执行完毕任务合集后，运行时会将运行时间当作内容追加到changes.txt文件末尾，提交信息为 `"update changes.txt"`

有关 Github Action 的原理，可查看官方文档 [Github Action 简介](https://docs.github.com/cn/actions/learn-github-actions/introduction-to-github-actions)

## 使用

**✨(๑•̀ㅂ•́)و✨ 好消息！这个仓库已设置为模板仓库，你可以直接使用了！以下是使用方法和需要修改的内容**

- 点击右上角 **Use this template** 按钮使用本 GitHub 仓库模板<br/>
- ⏲️定时 [ci.yml 文件的第 8 行](https://github.com/QiYiJun/autogreen/blob/main/.github/workflows/ci.yml#L8) 你可以自定义 `定时规则`
- 📋信息 [ci.yml 文件的第 22、23 行](https://github.com/QiYiJun/autogreen/blob/main/.github/workflows/ci.yml#L22-L23) 填你自己的 `GitHub账号邮箱` 和 `昵称`
- **⚠️千万不要 fork，因为 fork 项目的动态并不会让你变绿**
- **⚠️定时规则的时间是 UTC 时间，所以请不要问为什么到点了没跑**
- **⚠️还有 Actions 得排队，毕竟不是在自己机器上跑的，到点没跑的等个十几分钟再去看**

## 定时

定时语法，用空格分隔，每个字段代表一个时间单位

```plain
# 这对用过青龙面板的人来说是小菜一碟的对吧

┌───────────── 分 (0 - 59)
│ ┌───────────── 时 (0 - 23)
│ │ ┌───────────── 日 (1 - 31)
│ │ │ ┌───────────── 月 (1 - 12 或 JAN-DEC)
│ │ │ │ ┌───────────── 星期 (0 - 6 或 SUN-SAT)
│ │ │ │ │
│ │ │ │ │
│ │ │ │ │
* * * * *
```

每个时间字段的含义

| 符号 | 描述     | 举例                                        |
| ---- | -------- | ------------------------------------------- |
| `*`  | 任意值   | `* * * * *` 每天每小时每分钟                |
| `,`  | 值分隔符 | `1,3,4,7 * * * *` 每天每小时的 1 3 4 7 分钟 |
| `-`  | 范围     | `1-6 * * * *` 每天每小时的 1-6 分钟         |
| `/`  | 每       | `*/15 * * * *` 每天每隔 15 分钟             |

**注**：由于 GitHub Actions 的限制，如果设置为 `* * * * *` 实际的执行频率为每 5 分执行一次。

## License

[auto-green](https://github.com/QiYiJun/autogreen) is released under the MIT License. See the bundled [LICENSE](./LICENSE) file for details.