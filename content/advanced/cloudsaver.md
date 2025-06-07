---
title: "CloudSaver 资源搜索"
weight: 6
menu:
  main:
    parent: "advanced"
    name: "CloudSaver"
    weight: 6
---

## 什么是 CloudSaver？

CloudSaver 是一个网盘资源搜索工具，本项目集成了 CloudSaver 的搜索功能，可以方便地搜索和转存天翼云盘资源。

## 部署说明

### 1. 部署 CloudSaver 服务
首先需要自行部署 [CloudSaver](https://github.com/jiangrui1994/CloudSaver) 服务。

### 2. 配置 CloudSaver
在"媒体"中配置 CloudSaver：

![CloudSaver配置](images/cloudsaver/image.png)
需要填写以下信息：
- 服务地址：CloudSaver 的访问地址，例如 `http://localhost:8008`
- 账号：CloudSaver 的登录账号
- 密码：CloudSaver 的登录密码

## 使用方法

### 1. Web 界面搜索

1. 点击页面右下角的`···`按钮, 在展开的工具栏中点击CloudSaver
2. 在搜索框中输入关键词
3. 点击搜索按钮
4. 在搜索结果中可以：
   - 查看资源详情
   - 复制分享链接
   - 一键创建转存任务

{{< figure src="images/cloudsaver/cloudsaver.png" title="CloudSaver配置">}}

### 2. Telegram 机器人搜索

1. 使用 `/search_cs` 命令进入搜索模式
2. 直接输入关键词搜索
3. 搜索结果支持：
   - 点击复制链接
   - 输入编号直接创建任务
4. 使用 `/cancel` 退出搜索模式
   - 也可以等待 3 分钟自动退出

<div style="display:flex">
{{< figure src="images/bot/2.jpg" title="CloudSaver资源索">}}
{{< figure src="images/bot/3.jpg" title="资源转存">}}
</div>

## 搜索技巧

1. 关键词搜索
   - 使用空格分隔多个关键词
   - 支持中文和英文混合搜索
   - 建议使用准确的资源名称

2. 结果筛选
   - 系统会自动过滤非天翼云盘资源
   - 相同分享链接只显示一条
   - 优先显示分享时间较新的资源

3. 资源转存
   - 点击创建任务后会自动解析目录结构
   - 可以选择需要转存的文件夹
   - 支持设置保存位置

## 注意事项

1. 服务配置
   - 确保 CloudSaver 服务可以正常访问
   - 配置变更后会自动清除登录状态
   - 建议使用docker容器名作为地址, 具体操作请咨询AI助手

2. 使用限制
   - 搜索结果仅显示天翼云盘资源
   - 部分资源可能已失效
   - 访问码会自动填充（如果有）

## 常见问题

1. 搜索无结果
   - 检查 CloudSaver 服务是否正常
   - 尝试使用不同的关键词
   - 确认账号密码是否正确

2. 无法创建任务
   - 检查分享链接是否有效
   - 确认天翼云盘账号状态
   - 查看存储空间是否足够

3. 搜索结果不准确
   - 尝试使用更精确的关键词
   - 注意资源的更新时间
   - 可以通过标题判断资源质量