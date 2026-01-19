# NexusMailPurge - PT网站邮箱批量删除插件

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Tampermonkey](https://img.shields.io/badge/tampermonkey-adapted-brightgreen.svg)

专为 NexusPHP PT网站设计的浏览器油猴插件，帮助用户快速批量删除邮箱中的邮件，支持翻页操作。

## ✨ 主要功能

- 🗑️ **批量删除邮件** - 支持选中多个邮件进行批量删除
- 🤫 **静默执行** - 不弹出确认，自动连续删除直至完成或手动停止
- 📊 **状态栏提示** - 顶部状态栏显示剩余页数、错误与完成信息
- ♻️ **自动恢复** - 重新进入页面时自动恢复未完成的批量删除
- 🛑 **停止功能** - 删除过程中可随时手动停止
- 🎨 **美观界面** - 与PT网站风格保持一致的现代化界面

## 🚀 安装方法

### 方法一：直接安装（推荐）

1. 确保您的浏览器已安装 [Tampermonkey](https://www.tampermonkey.net/) 或 [Greasemonkey](https://www.greasespot.net/) 扩展
2. 点击下面的链接直接安装脚本：
   [点击一键安装](https://raw.githubusercontent.com/0x1st/NexusMailPurge/main/nexus-mail-purge.user.js)
   
   [镜像安装（jsDelivr）](https://cdn.jsdelivr.net/gh/0x1st/NexusMailPurge@main/nexus-mail-purge.user.js)

   或复制链接手动安装：
   ```
   https://raw.githubusercontent.com/0x1st/NexusMailPurge/main/nexus-mail-purge.user.js
   ```
3. 在弹出的安装页面点击"安装"按钮
   
   提示：如果 Raw 链接无法访问，请使用上方 jsDelivr 镜像，或在 Tampermonkey 管理面板中选择“添加新脚本”，将 `nexus-mail-purge.user.js` 内容复制粘贴后保存。

### 方法二：手动安装

1. 下载 `nexus-mail-purge.user.js` 文件
2. 打开 Tampermonkey 管理面板
3. 点击"添加新脚本"
4. 删除默认内容，粘贴下载的脚本内容
5. 按 `Ctrl+S` 保存脚本

## 📖 使用说明

### 基本操作

1. **访问邮箱页面**
   - 登录您的PT网站
   - 进入邮箱页面（messages.php 或 message.php）
   - 插件会自动在页面顶部添加操作工具栏

2. **选择邮件**
   - 可以单独勾选需要删除的邮件
   - 使用"删除当前页"时，脚本会自动全选并删除当前页所有邮件

3. **批量删除**
   - 🗑️ 点击"批量删除选中"按钮删除已选中的邮件
   - 🗑️ 点击"删除所有页面"按钮删除邮箱中的所有邮件

### 界面说明

```
┌────────────────────────────────────────────────────────────────────────┐
│ 🗑️ 删除选中  🗑️ 删除当前页  🗑️ 删除所有页  🛑 停止删除  剩余页数 3 页  │
└────────────────────────────────────────────────────────────────────────┘
```

- **删除选中**: 删除当前页面已勾选的邮件
- **删除当前页**: 自动全选并删除当前页所有邮件
- **删除所有页**: 自动按页连续删除直至清空
- **状态信息**: 顶部状态栏显示剩余页数与执行状态

### 安全特性

- 🤫 **静默模式**: 无弹窗确认，点击后直接执行
- 📊 **状态栏显示**: 提示剩余页数、错误与完成信息
- 🛑 **停止功能**: 删除过程中可以随时停止操作
- ♻️ **自动恢复**: 重新进入页面自动恢复未完成任务

## ⚙️ 配置选项

当前版本为静默模式，无需配置；删除流程的等待与恢复逻辑内置于脚本。

## 🔧 技术规格

- **兼容性**: 支持所有基于 NexusPHP 的 PT网站
- **浏览器**: Chrome, Firefox, Edge, Safari（需安装对应的用户脚本管理器）
- **依赖**: Tampermonkey 或 Greasemonkey 扩展
- **技术栈**: 纯 JavaScript (ES6+)，无外部依赖

## 🛡️ 隐私与安全

- ✅ **纯本地运行**: 脚本完全在浏览器本地运行，不会向第三方服务器发送数据
- ✅ **开源透明**: 所有代码开源，可自由审查和修改
- ✅ **权限最小化**: 仅请求必要的浏览器权限
- ✅ **数据安全**: 不收集、存储或传输任何个人信息

## 🐛 故障排除

### 常见问题

**Q: 插件没有显示工具栏？**
A: 请确保：
- 已正确安装 Tampermonkey 扩展
- 脚本已启用且匹配规则正确
- 当前页面是邮箱页面（URL包含 mailbox.php）

**Q: 删除操作失败？**
A: 可能的原因：
- 网络连接问题，请检查网络状态
- PT网站服务器繁忙，请稍后重试
- 邮件已被删除或不存在

**Q: 删除速度很慢？**
A: 为了避免对服务器造成压力，脚本内置了适当的等待与刷新节奏；实际速度取决于站点响应与页面结构。

### 调试信息

如果遇到问题，请：
1. 观察页面顶部状态栏信息
2. 确认站点邮箱页面为 messages.php 或 message.php
3. 打开浏览器开发者工具（F12）并查看控制台（Console）是否有错误

## 📝 更新日志

### v1.0.0 (2025-11-14)
- 🎉 首次发布
- ✨ 实现批量删除邮件功能
- 🤫 改为静默执行，无确认弹窗
- 📊 顶部状态栏显示进度与错误信息
- 🎨 美观的用户界面设计

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

1. Fork 本项目
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## ⭐ 支持项目

如果这个插件对您有帮助，请考虑：
- ⭐ 给项目点个星
- 🐛 报告问题和建议
- 🔄 分享给其他PT用户
- 💡 贡献代码和想法

## 📞 联系方式

- 项目主页: https://github.com/0x1st/NexusMailPurge
- 问题反馈: https://github.com/0x1st/NexusMailPurge/issues

---

**免责声明**: 本插件仅供学习和个人使用，请遵守相关PT网站的使用条款。使用本插件造成的任何后果由用户自行承担。
