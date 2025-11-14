# NexusMailPurge 安装指南

## 📋 安装前准备

### 1. 安装用户脚本管理器

首先，您需要在浏览器中安装一个用户脚本管理器扩展：

#### Chrome / Edge / Opera
- **Tampermonkey** (推荐): [Chrome Web Store](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
- **Violentmonkey**: [Chrome Web Store](https://chrome.google.com/webstore/detail/violentmonkey/jinjaccalgkegednnccohejagnlnfdag)

#### Firefox
- **Tampermonkey**: [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/)
- **Greasemonkey**: [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/greasemonkey/)

#### Safari
- **Tampermonkey**: [Mac App Store](https://apps.apple.com/us/app/tampermonkey/id1482490089)

## 🚀 安装方法

### 方法一：一键安装（推荐）

1. 确保已安装用户脚本管理器
2. 点击下面的链接：
   ```
   https://raw.githubusercontent.com/styin8/NexusMailPurge/main/nexus-mail-purge.user.js
   ```
3. 浏览器会自动打开脚本安装页面
4. 点击"安装"按钮完成安装

### 方法二：手动安装

1. **下载脚本文件**
   - 右键点击 [nexus-mail-purge.user.js](nexus-mail-purge.user.js)
   - 选择"另存为"下载文件

2. **安装到 Tampermonkey**
   - 点击浏览器工具栏中的 Tampermonkey 图标
   - 选择"管理面板"
   - 点击"添加新脚本"按钮
   - 删除默认内容，粘贴下载的脚本内容
   - 按 `Ctrl+S` (Windows) 或 `Cmd+S` (Mac) 保存

3. **安装到 Greasemonkey**
   - 点击浏览器工具栏中的 Greasemonkey 图标
   - 选择"管理用户脚本"
   - 点击"新建用户脚本"
   - 粘贴脚本内容并保存

## ✅ 验证安装

1. **检查脚本状态**
   - 打开用户脚本管理器面板
   - 确认 "NexusMailPurge" 脚本已启用
   - 状态应显示为绿色或"已启用"

2. **测试功能**
   - 访问任意 PT网站的邮箱页面
   - 查看页面顶部是否出现工具栏
   - 工具栏应包含选择框和删除按钮

## 🔧 配置设置

### 脚本权限设置

确保脚本具有以下权限：
- `GM_setValue` - 保存配置
- `GM_getValue` - 读取配置
- `GM_deleteValue` - 删除配置
- `GM_notification` - 显示通知

### 匹配规则

脚本默认匹配规则为：`*://*/mailbox.php*`

如果您的PT网站使用不同的邮箱URL，可以手动添加匹配规则：

1. 打开 Tampermonkey 管理面板
2. 找到 NexusMailPurge 脚本，点击编辑
3. 在 `@match` 行下添加新的匹配规则：
   ```javascript
   // @match        *://your-pt-site.com/mailbox.php*
   // @match        *://another-site.org/mail/*
   ```
4. 保存脚本

## 🐛 常见安装问题

### 问题1：脚本无法安装
**症状**: 点击安装链接后没有反应
**解决方案**:
- 确认已正确安装用户脚本管理器
- 尝试刷新页面后重新点击
- 使用手动安装方法

### 问题2：脚本已安装但不工作
**症状**: 邮箱页面没有显示工具栏
**解决方案**:
- 检查脚本是否已启用
- 确认当前页面URL匹配脚本规则
- 查看浏览器控制台是否有错误信息

### 问题3：权限不足
**症状**: 脚本功能受限或报错
**解决方案**:
- 在脚本管理器中检查权限设置
- 确保所有 `@grant` 权限都已启用
- 重新安装脚本

### 问题4：与其他脚本冲突
**症状**: 页面显示异常或功能冲突
**解决方案**:
- 暂时禁用其他用户脚本进行测试
- 检查是否有多个邮箱相关脚本
- 调整脚本执行顺序

## 🔄 更新脚本

### 自动更新
脚本包含自动更新功能，会定期检查新版本。

### 手动更新
1. 打开脚本管理器面板
2. 找到 NexusMailPurge 脚本
3. 点击"检查更新"或重新安装

## 🗑️ 卸载脚本

如需卸载脚本：
1. 打开用户脚本管理器面板
2. 找到 NexusMailPurge 脚本
3. 点击删除或垃圾桶图标
4. 确认删除操作

## 📞 获取帮助

如果安装过程中遇到问题：

1. **查看文档**: 阅读 [README.md](README.md) 了解详细使用说明
2. **检查兼容性**: 确认您的PT网站基于 NexusPHP 框架
3. **提交问题**: 在 [GitHub Issues](https://github.com/styin8/NexusMailPurge/issues) 提交问题报告
4. **社区支持**: 在相关PT论坛寻求帮助

## 📋 系统要求

- **浏览器**: Chrome 88+, Firefox 85+, Edge 88+, Safari 14+
- **用户脚本管理器**: Tampermonkey 4.0+ 或 Greasemonkey 4.0+
- **网站兼容性**: 基于 NexusPHP 的 PT网站
- **JavaScript**: 需要启用 JavaScript

---

安装完成后，请查看 [README.md](README.md) 了解详细的使用说明。