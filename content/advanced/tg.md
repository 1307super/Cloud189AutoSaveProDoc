---
title: "TG机器人"
weight: 2
menu:
  main:
    parent: "advanced"
    name: "TG机器人"
    weight: 2
---


## 配置机器人

### 1. 创建机器人
1. 在 Telegram 中搜索 [@BotFather](https://t.me/BotFather)
2. 发送 `/newbot` 命令
3. 按提示设置机器人名称
4. 获取 Bot Token（请妥善保管，不要泄露）

### 2. 系统配置
1. 进入系统设置页面
2. 在"Telegram 机器人"区域找到 机器人设置
3. 填入 Bot Token和Chat Id(如果不知道Chat Id，可只填写Bot Token, 保存后打开TG机器人发送命令/chat_id即可)
4. 启用 点亮 TG 创任务
5. 保存设置

### 3. 开始使用
1. 在 Telegram 中搜索你创建的机器人
2. 发送 `/help` 查看帮助信息

## 常用命令

### 基础命令
- `/help` - 显示帮助信息
- `/accounts` - 显示账号列表
- `/tasks` - 显示任务列表
- `/execute_all` - 执行所有任务
- `/fl` - 显示常用目录列表
- `/fs` - 添加常用目录
- `/search_cs` - 搜索资源
- `/cancel` - 取消当前操作
- `/chat_id` - 获取Chat Id
- `/conf` - 机器人配置

### 任务操作
- `/execute_[ID]` - 执行指定任务
- `/strm_[ID]` - 生成 STRM 文件
- `/emby_[ID]` - 通知 Emby 刷新
- `/dt_[ID]` - 删除指定任务

### 目录操作
- `/df_[ID]` - 删除指定常用目录

## 使用流程

### 1. 账号管理
1. 发送 `/accounts` 查看账号列表
2. 选择要使用的账号
3. 如果没有账号，请先在 Web 界面添加

### 2. 常用目录管理
1. 发送 `/fl` 查看当前账号的常用目录
2. 发送 `/fs` 进入目录选择模式
3. 在目录树中操作：
   - 点击文件夹名称：进入下级目录
   - 点击返回按钮：回到上级目录
   - 点击确认按钮：保存当前目录
   - ✅ 标记：表示已添加为常用目录
4. 使用 `/df_[ID]` 删除不需要的常用目录

### 3. 创建转存任务
1. 直接发送天翼云盘分享链接
2. 支持的链接格式：
   - 普通链接：`https://cloud.189.cn/t/xxxxx`
   - 带访问码：`https://cloud.189.cn/t/xxxxx（访问码：xxxx）`
   - 批量转存: 直接粘贴所有分享链接即可, 无需单独处理, 系统会自动识别并转存
3. 发送链接后选择保存目录
4. 如果目标位置有同名文件夹：
   - 选择"是"：删除原文件夹后保存
   - 选择"否"：取消任务创建

### 4. 任务管理
1. 发送 `/tasks` 查看任务列表
2. 可用操作：
   - `/execute_[ID]`：立即执行任务
   - `/strm_[ID]`：生成 STRM 文件
   - `/emby_[ID]`：刷新 Emby 库
   - `/dt_[ID]`：删除任务
3. 使用 `/execute_all` 执行所有未完成任务

### 5. 资源搜索
1. 发送 `/search_cs` 进入搜索模式
2. 直接输入关键词搜索
3. 搜索结果支持：
   - 点击复制链接
   - 发送编号创建任务
4. 退出搜索模式：
   - 发送 `/cancel`
   - 3分钟无操作自动退出

## 使用技巧

1. 快速操作
   - 保存常用目录，方便重复使用

2. 任务管理
   - 定期清理以失败和已完结的任务

3. 安全建议
   - 不要将 Bot Token 泄露给他人
   - 定期检查机器人运行状态
   - 重要操作建议在 Web 界面执行

## 常见问题

1. 机器人无响应
   - 检查 Bot Token 是否正确
   - 确认系统设置中已启用机器人
   - 尝试重新启动机器人
   - 检查`科学`是否异常

2. 任务创建失败
   - 确认分享链接格式正确
   - 检查访问码是否正确
   - 确认存储空间充足

3. 目录选择问题
   - 确认账号已正确选择
   - 检查目录权限设置
   - 尝试重新进入目录选择模式
  
## 预览图

<div style="display:flex">
{{< figure src="/Cloud189AutoSaveProDoc/images/bot/1.jpg" title="帮助命令">}}
{{< figure src="/Cloud189AutoSaveProDoc/images/bot/5.jpg" title="任务列表">}}
{{< figure src="/Cloud189AutoSaveProDoc/images/bot/2.jpg" title="CloudSaver资源索">}}
{{< figure src="/Cloud189AutoSaveProDoc/images/bot/3.jpg" title="资源转存">}}
</div>