# EZ Gaea Node

[**下载 Windows x64 运行包 ZIP**](https://github.com/chenxin234123/EZ-GAEA-Node/releases/latest/download/EZ-Gaea-Node-Windows-x64.zip) · [版本说明与校验文件](https://github.com/chenxin234123/EZ-GAEA-Node/releases/latest)

面向 Gaea 使用者的多语言桌面节点参考助手。作者：[chenxin234123](https://www.artstation.com/chenxin234123)。

[English](README.md) · [制作思路](DESIGN.zh-CN.md) · [第三方声明](THIRD-PARTY-NOTICES.md)

可以手动搜索节点，也可以跟随 Gaea 中选中的节点，在制作地形时直接查阅本地说明。

## 下载与启动

在本仓库的 **Releases → Assets** 下载 **EZ-Gaea-Node-Windows-x64.zip**。完整解压后，进入文件夹运行 **EZ Gaea Node.exe**，无需安装向导。

请保留 EXE、Data 文件夹和配置文件的相对位置，不要只复制 EXE。GitHub 自动生成的 “Source code” 压缩包是仓库说明资料；可运行的软件是单独上传的上述 ZIP。

## 功能

- 当前包含 183 个节点的本地参考资料：介绍、参数、选项、使用场景及已有的视觉示例。
- 支持 English、简体中文、繁體中文、日本語、Deutsch、Español、Français、한국어，可单选或同时勾选多种语言。
- 保留英文节点名和参数名，方便与 Gaea 界面对照。
- 支持节点名、别名和译名搜索，搜索列表一次显示最多四行。
- 提供“识别 Gaea 节点”、置顶和识别状态颜色提示。
- 查阅不需要 AI 账号、API 密钥或联网翻译服务。

<img src="images/preview.png" width="400" alt="EZ Gaea Node 英文与日语双语显示示例">

## 运行要求

- 64 位 Windows，发布包面向 Windows 10/11，不适用于 macOS 或 Linux。
- .NET Framework 4.8 或兼容的更高 4.x 运行时，注意它与现代 .NET 不同。需要时可查阅 [Microsoft 官方安装说明](https://learn.microsoft.com/en-us/dotnet/framework/install/on-windows-and-server)。
- 自动跟随需要 Gaea 2；手动搜索无需运行 Gaea。当前识别条件包括 Gaea.exe、安装路径包含 \Gaea 2\，以及能读取属性面板。未验证所有后续 Gaea 版本。

请解压到当前账户可以写入的目录。软件会自行创建 UserData，保存使用设置和最近一次识别诊断。全新启动默认英文，随后可勾选需要的语言。识别不明确时，可以选择候选说明或手动搜索。若要重置设置，请先关闭软件，再重命名 UserData 文件夹。

## 翻译与来源

英文保留原有参考文本；简体中文沿用已有第三方译文，繁体中文由简体转换。日、德、西、法、韩文由 GPT-6 重译，每种包含 2,926 条独立的文档与界面文字。已进行翻译检查，但不等同于专业母语译者逐条审校，可同时勾选英文对照。官方没有说明的参数保持空缺，不编造内容。

这是独立第三方助手，不是 QuadSpinner 官方产品。文档来源：[官方参考目录](https://docs.gaea.app/reference)及 [Gaea2-Docs](https://github.com/QuadSpinner/Gaea2-Docs)。第三方文档的 MIT 许可保存在 Licenses 中。

## 查看更新

点击 Collapse/收起 左边的 **⋯ → 检查更新**，会在默认浏览器打开[项目页面](https://github.com/chenxin234123/EZ-GAEA-Node)。菜单文字跟随当前界面语言。它是网页快捷入口；软件不查询版本、不比较版本号，也不下载或安装更新。请在 GitHub 页面自行查看说明和下载软件。

作者署名固定为 **Created by : chenxin234123**，姓名及 ArtStation 链接编译在程序中，不读取 Author.json。

## 源码与制作思路

此仓库不公开应用程序源码或构建工程，但提供[制作思路说明](DESIGN.zh-CN.md)。第三方文档的 MIT 声明不代表整个助手程序采用 MIT 许可证。

## 应用使用许可

**个人及商业项目均可免费使用；未经作者书面授权，禁止转售或收费分发软件本身。** 个人、自由职业者、工作室和公司均可用于付费接单，无需另外购买商业许可。允许保留全部声明后免费分享完整、未修改的官方发布包。

完整应用条款见 [LICENSE.txt](LICENSE.txt)。第三方材料仍适用原有许可，包括 Gaea2-Docs 原有的 MIT 权利。

## 反馈

可通过本仓库 Issues 提交节点名称、Gaea 版本、所选语言及实际表现。截图有助于说明问题，分享前请去掉私人项目内容。

## 自愿支持

喜欢这个软件吗？底部提供 [Buy me a coffee](https://buymeacoffee.com/chenxin234123) 和支付宝二维码窗口。勾选中文时，支付宝按钮和窗口优先显示中文，即使同时勾选英文。打赏完全自愿，不影响任何功能；如若打赏失败，无需再次尝试。

支持提示和两个按钮采用右对齐的小号灰色样式。chenxin234123 名字旁的使用许可按钮显示作者提供的中英文许可原文。界面文字支持多语言，法律正文保留原文。许可和提供的二维码图片嵌入程序。
