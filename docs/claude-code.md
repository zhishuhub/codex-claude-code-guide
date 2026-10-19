# Claude Code 一键配置教程（Windows / Mac）

把 Claude Code 接到智枢，用 Claude Opus、Sonnet、Fable 写代码。配置工具会顺带装好 Claude Code 命令行版；电脑上装了 Claude 桌面版的话，也一起配好。

[← 返回目录](../README.md)

## 1. 登录并选择 Claude

[打开智枢并登录](https://zhishuhub.com/sign-up?aff=zbD0)，确认账户余额充足。

[打开安装配置向导](https://zhishuhub.com/guide?aff=zbD0)，选择「Claude」（Claude Code）和你的电脑系统。

## 2. 选线路

| 线路 | 适合 |
|---|---|
| 性价比线路（推荐） | 日常写代码，更便宜 |
| 自建线路 | 对稳定性要求高，价格较高 |

以后想换线路，回到向导选另一条，重新运行一次配置工具即可。

## 3. 一键配置

命令行版不用单独安装，配置工具会自动装好；版本太旧的会自动升级。桌面版是可选的，需要的话在向导里点「下载桌面版（可选）」。

### Windows

1. 点「下载配置工具」，浏览器询问时选「保留」。
2. 双击运行。没装 Claude Code 的话会自动安装，约 100 MB。
3. 打开一个新的终端窗口，输入 `claude` 回车。

### Mac

1. 点「生成命令」，再点「复制命令」。
2. 打开「终端」，粘贴完整命令并回车。
3. 打开一个新的终端窗口，输入 `claude` 回车。

装了 Claude 桌面版的，重启桌面版后生效。

## 4. 发消息验证

在 Claude Code 里发一句「你好，请用中文回复」，收到正常回复就配好了。

## 手动配置

不想用配置工具，也可以自己改配置文件。

1. 在智枢控制台「API 密钥」页点「创建 API 密钥」，分组选 `claude`（性价比线路）或 `ccmax满血官key转发`（自建线路），复制生成的密钥。
2. 打开配置文件：Mac 是 `~/.claude/settings.json`，Windows 是 `C:\Users\你的用户名\.claude\settings.json`，没有就新建。
3. 写入下面这段，把密钥换成你自己的：

   ```json
   {
     "env": {
       "ANTHROPIC_BASE_URL": "https://zhishuhub.com",
       "ANTHROPIC_AUTH_TOKEN": "sk-你的密钥",
       "ANTHROPIC_MODEL": "claude-opus-5-5"
     }
   }
   ```

4. 打开一个新的终端窗口，运行 `claude`。

文件里原来有别的设置的话，只把 `env` 里这三项合并进去，别整份覆盖。可用的模型名以 [模型价格](https://zhishuhub.com/pricing?aff=zbD0) 页为准。用别家中转站的话，把地址和密钥换成对应的就行。

手动配置只覆盖基础连接；Opus / Sonnet / Haiku 各档模型、版本兼容和桌面版，一键配置会一起处理。

## 常见问题

### 想切回官方账号登录

在智枢首页找到 Claude Code 的一键配置，点「切回官方版」。它会去掉智枢的连接设置，其余设置保留，之后用你的 Claude 账号重新登录即可。

### 输入 `claude` 提示找不到命令

关掉当前终端，重新打开一个新的再试。配置工具装好命令行版后，旧窗口读不到新路径。

### Windows 提示「Windows 已保护你的电脑」

点「更多信息」，再点「仍要运行」。

### 提示配置码过期或已使用

配置码 30 分钟内有效，只能用一次。回网站重新生成即可。

### 配置后没有回复

先看账户余额，再关掉终端重新打开、重新运行 `claude`。还不行就到 [QQ 群](https://qm.qq.com/q/UXdEAUEFCC)（群号 1106399716）求助，不要公开密钥或完整配置命令。
