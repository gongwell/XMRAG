# Introduction
[中文](https://github.com/gongwell/XMRAG/blob/main/README.md)

This is a zero-development, zero-code, zero-construction, out-of-the-box service interface that meets the needs of personal use of the knowledge base. The project is based on Microsoft's kernel-memory, a multi-modal artificial intelligence service dedicated to efficient indexing of data sets through a custom continuous data mixing pipeline, and supports retrieval-augmented generation (RAG), synthetic memory, prompts Engineering and custom secondary development. Semantic memory processing.

![image](https://github.com/user-attachments/assets/2b9bf9d9-1f1e-45b3-9461-50323b4f7b7f)
![image](https://github.com/microsoft/kernel-memory/blob/main/docs/img/kernel-memory-lambda-architecture.png)

For more detailed information about Km, please see [Microsoft Kernel Memory](https://microsoft.github.io/kernel-memory/)

![GitHub issues](https://img.shields.io/github/issues/user/repo) ![GitHub stars](https://img.shields.io/github/stars/user/repo) ![License](https://img.shields.io/badge/license-MIT-blue.svg) ![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat&logo=microsoft-azure&logoColor=white) ![KM](https://img.shields.io/badge/KM-FFD700?style=flat&logo=book&logoColor=white) ![Microsoft](https://img.shields.io/badge/Microsoft-0078D4?style=flat&logo=microsoft&logoColor=white) ![Free](https://img.shields.io/badge/License-Free-brightgreen)

##  Explanation of various responsibilities and usage requirements

1. For users, we have achieved data isolation, whether it is uploaded data or conversation data, but not including data backup, so do not use this interface in a production environment.
2. For interface use, we do not recommend that you lend or open your key to other platforms. Note that the key cannot be reset.
3. The uploaded data should not contain the following content: violence, hatred, sex and self-harm, anti-party and anti-government speech, and should not contain any form of feminist and LGBT content. RAI follows responsible AI.
4. Regarding the number of conversations and the size of uploaded data, it is said that it cannot be adjusted. The project itself uses multiple Azure paid services such as Azure AI Search，Aoai-GPT4o，azure text-embedding-3-large，Azure Ai Documents, and Azure Blob, which will increase costs.
5. During the use process, I hope everyone will extract more opinions, and I also hope that everyone will tell us in time to recycle the account when it is not used for a long time.
6. The platform only provides an enabling interface, which requires front-end projects to support or carry out front-end development.

##  Instructions

1. First log in to the registration website [http://cq.ath.cx:8888/](http://cq.ath.cx:8888/)
2. [For interface description, please refer to the document](https://github.com/gongwell/XMRAG/blob/main/APi-EN.md)
3. Example of use

   1. [In FastGPT](https://cloud.tryfastgpt.ai/app/list)
   ![屏幕截图 2024-11-21 231321](https://github.com/user-attachments/assets/1d655bed-6668-40f1-afe8-292257116a28)

   ![屏幕截图 2024-11-21 231242](https://github.com/user-attachments/assets/69fe3f94-95b2-4d89-ac88-7760cc0584c8)

   ![屏幕截图 2024-11-21 231310](https://github.com/user-attachments/assets/797d4392-4e2b-40eb-b661-b77c4eb87dc5)

   ![251c1672f5578ff28558438f41cd93c](https://github.com/user-attachments/assets/80a43b3f-38fc-4f24-9ee8-6b2b3cb646a1)

   2. In Copilot

      [Generate API plugins from existing APIs for intelligent Microsoft 365 Copilot® projects](https://learn.microsoft.com/zh-cn/microsoft-365-copilot/extensibility/build-api-plugins-existing-api?tabs=toolkit)

   3. In SK projects
      
       https://github.com/microsoft/kernel-memory/blob/main/examples/302-dotnet-sk-km-chat/Program.cs


## 5. Code Examples
The user tag will be bound to the user pipeline, and the pipeline will be randomly generated when uploading files.

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


## Declaration
1. This project is free of charge

2. This project was developed and computing services were provided by Chongqing Exmand Technology Co., Ltd.
    [https://www.xmindai.cn/]

 ![logo](https://github.com/user-attachments/assets/ff0ec800-9045-4d62-adf9-3d10a6fcd5b9)


## Contributors
<div style="text-align: center;">
    <img src="https://github.com/azgy.png" alt="azgy's avatar" width="30" style="margin: 0 10px;" />
    <img src="https://github.com/zsbgnw12.png" alt="zsbgnw12's avatar" width="30" style="margin: 0 10px;" />
    <img src="https://github.com/zshandong.png" alt="zshandong's avatar" width="30" style="margin: 0 10px;" />
    <img src="https://github.com/googwell.png" alt="googwell's avatar" width="30" style="margin: 0 10px;" />
</div>
 
