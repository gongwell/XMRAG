# 简介
 [English](https://github.com/gongwell/XMRAG/blob/main/README-EN.md)
 
这是一个0代码0开发0搭建，开箱即用的服务接口，满足个人对知识库的使用。此项目基于 Microsoft 的 kernel-memory，是一种多模态 AI 服务，专门用于通过自定义连续数据混合管道对数据集进行高效索引，并支持检索增强生成（RAG）、合成内存、提示工程和自定义语义内存处理上的二次开发。

![image](https://github.com/user-attachments/assets/2b9bf9d9-1f1e-45b3-9461-50323b4f7b7f)
![image](https://github.com/microsoft/kernel-memory/blob/main/docs/img/kernel-memory-lambda-architecture.png)

关于更多 Km 的详细介绍请查看 [Microsoft Kernel Memory](https://microsoft.github.io/kernel-memory/)

![GitHub issues](https://img.shields.io/github/issues/user/repo) ![GitHub stars](https://img.shields.io/github/stars/user/repo) ![License](https://img.shields.io/badge/license-MIT-blue.svg) ![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat&logo=microsoft-azure&logoColor=white) ![KM](https://img.shields.io/badge/KM-FFD700?style=flat&logo=book&logoColor=white) ![Microsoft](https://img.shields.io/badge/Microsoft-0078D4?style=flat&logo=microsoft&logoColor=white) ![Free](https://img.shields.io/badge/License-Free-brightgreen)


## 关于各种责任和使用要求说明

1. 对于用户，我们有做到数据隔离无论是上传数据和对话数据，但不包括数据备份，所以不要在生产环境下使用此接口。
2. 对于接口使用，我们不建议你将自己的 key 外借或开放到其他平台，注意 key 无法重置。
3. 对于上传数据不应该包含以下内容：暴力、仇恨、性和自残、反党反政府言论，不应该出现以任何形式的女权、LGBT 的内容，RAI 遵循负责任的 AI。
4. 关于对话次数和上传数据大小，表示不能调整，项目本身使用 Azure AI Search、Azure 智能文档、Azure Blob、Aoai-GPT4o、azure text-embedding-3-large、Azure  等多个 Azure 的收费服务，这样会增加成本。
5. 在使用的过程中希望大家多多提取意见，也希望大家在长时间不使用的时候，及时告诉我们回收账户。
6. 平台只提供赋能接口，需要有前端项目进行支持或进行前端开发。

## 使用说明

1. 首先登陆注册网址 [http://cq.ath.cx:8888/](http://cq.ath.cx:8888/)
2. [接口说明请查看文档](https://github.com/gongwell/XMRAG/blob/main/%E6%8E%A5%E5%8F%A3%E4%BF%A1%E6%81%AF.md)
3. 使用的示例

   一、[在FastGPT中](https://cloud.tryfastgpt.ai/app/list)
   ![屏幕截图 2024-11-21 231321](https://github.com/user-attachments/assets/1d655bed-6668-40f1-afe8-292257116a28)
   
   ![屏幕截图 2024-11-21 231242](https://github.com/user-attachments/assets/69fe3f94-95b2-4d89-ac88-7760cc0584c8)

   ![屏幕截图 2024-11-21 231310](https://github.com/user-attachments/assets/797d4392-4e2b-40eb-b661-b77c4eb87dc5)

   ![251c1672f5578ff28558438f41cd93c](https://github.com/user-attachments/assets/80a43b3f-38fc-4f24-9ee8-6b2b3cb646a1)

   二、在Copilot中
   
   [从现有 API 生成 api 插件，用于智能 Microsoft 365 Copilot 副驾驶®项目](https://learn.microsoft.com/zh-cn/microsoft-365-copilot/extensibility/build-api-plugins-existing-api?tabs=toolkit)

   三、在SK项目中

   https://github.com/microsoft/kernel-memory/blob/main/examples/302-dotnet-sk-km-chat/Program.cs

## 5. 代码示例
用户tag会和用户管道绑定，管道会在上传文件时随机产生。

### C#
```csharp
#r "nuget: Microsoft.KernelMemory.WebClient"

var memory = new MemoryWebClient("http://cq.ath.cx:8881/api/upload"); // <== URL of KM web service

// Import a file
await memory.ImportDocumentAsync("meeting-transcript.docx");
```

### Python
```
import requests

# Files to import
files = {
    "file1": ("business-plan.docx", open("business-plan.docx", "rb")),
}

response = requests.post("http://cq.ath.cx:8881/api/upload", files=files, data=data)
```


## 声明
 1、本项目主要出于教育目的方便开发人员快速进行测试，让学生党免费使用知识库，不再让科技高高在上，本项目不收费！！！🎉📚🚀（不要相信任何咸鱼）

 2、技术与合作联系邮箱xiaohei@xinghanlab.com
 
 3、[本项目由重庆埃克斯曼得技术有限公司开发并提供AI、计算服务](https://www.xmindai.cn/)
 
 ![logo](https://github.com/user-attachments/assets/ff0ec800-9045-4d62-adf9-3d10a6fcd5b9)

## 贡献
<div style="text-align: center;">
    <img src="https://github.com/azgy.png" alt="azgy's avatar" width="30" style="margin: 0 10px;" />
    <img src="https://github.com/zsbgnw12.png" alt="zsbgnw12's avatar" width="30" style="margin: 0 10px;" />
    <img src="https://github.com/zshandong.png" alt="zshandong's avatar" width="30" style="margin: 0 10px;" />
    <img src="https://github.com/googwell.png" alt="googwell's avatar" width="30" style="margin: 0 10px;" />
</div>
