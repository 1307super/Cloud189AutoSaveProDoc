---
title: "消息通知"
weight: 5
menu:
  main:
    parent: "usage"
    name: "消息通知"
    weight: 5
---



## 一、功能简介  
消息通知服务支持接入第三方平台，实时推送任务状态、系统告警等信息。系统已**内置企业微信、Telegram、Bark、PushPlus**四大平台，同时支持自定义其他通知服务。通过灵活的参数配置和模板变量，可适配多样化的通知需求。  


## 二、内置通知平台使用说明  
### 操作入口  
1. 点击界面右下角「···」图标，展开工具栏。  
2. 点击「通知」图标进入配置界面。  

### 通用配置规则  
- **内置平台仅支持编辑URL和参数**，不可修改基础协议（如企业微信的Webhook协议）。  
- **替换模板**：`{{content}}` 会自动替换为实际消息内容（如任务完成通知、错误信息等）。  

### 1. 企业微信通知  
**配置参数**：  
- **URL**：企业微信机器人Webhook地址（格式：`https://qyapi.weixin.qq.com/cgi-bin/webhook/send?key=xxx`）。  
- **消息类型**：支持文本、markdown、图片等（需按企业微信接口规范在参数中指定）。  

**示例配置**：  
```yaml
平台类型: 企业微信
URL: https://qyapi.weixin.qq.com/cgi-bin/webhook/send?key=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
参数: {"msgtype": "text", "text": {"content": "{{content}}"}}
```

<div style="width: 100%;margin:0 auto;display: flex;">
{{< figure src="/images/message/index.png" title="自定义消息通知示意图">}}
{{< figure src="/images/message/form.png" title="自定义消息通知添加示意图">}}
</div>


### 2. 自定义通知平台

**操作步骤**

1. 点击「新增通知」按钮，选择「自定义平台」。
2. 按以下字段填写配置：
    - 名称：自定义（如 “飞书通知”）。
    - 描述：自定义（如 “飞书通知1号”）。
    - 通知 URL：目标平台的 API 地址（如飞书 Webhook 地址）。
    - 请求方式：支持GET/POST/PUT。
    - 请求类型：（如Content-Type: application/json）。
    - 请求参数：按目标平台文档填写（支持{{content}}模板变量）。

```yaml
平台名称: 飞书通知
请求方式: POST
通知URL: https://open.feishu.cn/open-apis/bot/v2/hook/xxx
请求头: {"Content-Type": "application/json"}
请求参数: {"msg_type": "text", "content": {"text": "{{content}}"}}
```

## 三、管理与调试
1. **测试通知：** 配置完成后可点击「测试推送」验证配置正确性。
3. **日志查询：** 在系统日志中可查看通知发送记录及失败原因（如 URL 无效、参数错误等）。