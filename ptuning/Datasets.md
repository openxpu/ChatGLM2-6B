# ChatGLM2-6B-PT 数据集准备
本仓库实现了对于 ChatGLM2-6B 模型基于 [P-Tuning v2](https://github.com/THUDM/P-tuning-v2) 的微调。P-Tuning v2 将需要微调的参数量减少到原来的 0.1%，再通过模型量化、Gradient Checkpoint 等方法，最低只需要 7GB 显存即可运行。

下面将用一个简单数据集为例介绍该模型的微调使用方法。

## 对话数据集

该模型支持使用多轮对话数据对模型进行微调，可以提供聊天历史，例如以下是一个三轮对话的训练数据：

```json lines
{"prompt": "你是谁", "response": "我叫某某某", "history": []}
{"prompt": "描述一下你自己", "response": "我是一名程序员", "history": [["你是谁", "我叫某某某"]]}
{"prompt": "你有什么技术特长", "response": "熟练掌握编程语言：Java、Python等；熟悉常用的开发框架：Spring、Hibernate等；具备良好的数据结构和算法基础。", "history": [["你是谁", "我叫某某某"], ["描述一下你自己", "我是一名程序员"]]}
{"prompt": "请介绍一下JAVA语言特性", "response": "Java 技术特长体现在其平台独立性、面向对象编程、多线程支持、强大的类库、安全性、大型企业应用开发和开源生态系统等方面", "history": []}
```
您可以根据自己的需求，将自有数据进行以上形式的整理并微调出符合自己预期的LLM模型，祝您使用愉快！
```



