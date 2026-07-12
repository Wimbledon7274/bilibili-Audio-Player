# Bilibili Audio Player

> 声明 (AI生成): 本项目核心代码及重连架构由 AI 生成并优化。
  声明 (AI生成): 本项目核心代码及重连架构由 AI 生成并优化。
  声明 (AI生成): 本项目核心代码及重连架构由 AI 生成并优化。

##  项目简介 (Purpose)

Bilibili Audio Player 是一款基于 Python 的本地流媒体音频播放器，专门为 Bilibili 的音视频及直播流设计。
核心目标是：**轻量、稳定、去画面、专注音频播放**。
不需要完整下载视频，即可通过拉取底层 m4s/m4a 流数据实现播放，支持视频合集解析、全局快捷键、以及后台静默运行。

###  核心特性
使用 yt-dlp 解析 B 站数据。内置独立的本地 HTTP 代理服务（`BiliStreamProxyHandler`），拦截到上游断流，会在后台静默重新请求直链并完成续接。
单视频、合集分P列表、甚至直播间均可解析播放（部分直播间无法正常显示直播标题，少部分直播间解析传输播放均正常，但无声音，数量少且查不到原因，摆了）。
自动过滤 URL 追踪参数
##  技术架构 (Technical Background)
采用了纯 Python 的轻量级架构：
* **GUI 框架**：`PyQt6` 
* **解析引擎**：`yt-dlp` 
* **媒体代理**：Python 原生 `http.server`
* **全局控制**：`pynput` 

## 下载与安装 (Installation)

Windows 用户，无需配置 Python 或任何代码环境，只需前往项目仓库的 Releases 页面下载打包好的 `.exe` 文件，双击直接运行。


## 🚀 使用指南 (Usage)

1.SESSDATA: 在顶部输入框填入您的 B 站网页端 `SESSDATA` Cookie。获取路径：Chrome-bilibili.com-F12-Application-cookie-SESSDATA。
Edge-bilibli.com主页地址栏左侧“小锁”的图标，点击进去，点击Cookie和站点数据-cookie-bilibili.com-cookie-SESSDATA右键SESSDATA部分-检查-展开默认高亮部分，获取完整数据。
2.将任意 B 站视频、合集或直播间链接粘贴至地址栏，点击“开始解析”。工具会自动剔除 `spm_id_from` 等长尾跟踪参数。
3. 
   - 列表双击播放，支持关键字过滤搜索。
   - 支持单曲循环、列表循环、顺序播放。
   - 支持全局多媒体快捷键（Play/Pause, Next, Previous），可在后台切歌。
4.多次解析412错误。可以尝试更新SESSDATA。或等待发布更新YT-DLP新版本。
  出现403错误，可能是网络连接被限制，更换IP或等待风控结束。
  使用过程中出现卡顿，突然停止播放，建议手动切换下一首。
  YT-DLP重大更新时才会进行后续更新。不支持其他更新方式，仓库下载后替换文件即可。

## ⚠️ 免责声明 (Disclaimer)
本项目仅供 Python 多线程架构、本地代理技术以及 AI 代码生成能力的学习与研究使用。请勿用于商业用途或高频恶意抓取。
