## 前言

最近大火的 ChatGPT 提供了一系列 API 接口，可以调用多种模型进行对话，应用场景包括：

- 起草电子邮件或其他书面文件
- 编写代码
- 回答有关一组文件的问题
- 创建会话代理
- 为您的软件提供自然语言界面
- 一系列科目的导师
- 翻译语言
- 模拟视频游戏中的角色等等

## 准备

1. 注册一个 OpenAI 账号。
2. 配置 Python 开发环境，要求 **Python >= 3.7.1**。

## 获取开发密钥

1. 打开 [OpenAI API 密钥页面](https://platform.openai.com/account/api-keys)。
2. 点击 “Create new secret key”。
3. 输入任意密钥名称并生成密钥。
4. 复制密钥，注意：密钥只在生成时可见，未保存需重新生成。

## 开发

### 安装 OpenAI 库

bash
pip install openai


### 创建脚本

新建一个脚本文件 `helloai.py`，代码如下：

python
import os
import openai

# 填入你的 OPENAI_API_KEY
openai.api_key = "OPENAI_API_KEY"

# 调用 ChatGPT API
completion = openai.ChatCompletion.create(
  model="gpt-3.5-turbo",
  messages=[
    {"role": "user", "content": "Hello!"}
  ]
)

# 输出生成的内容
print(completion.choices[0].message)

# 输出完整响应
print(completion)


### 运行脚本

运行以下命令：

bash
python ./helloai.py


返回示例输出：

plaintext
Hello there, how may I assist you today?
{
  "id": "chatcmpl-123",
  "object": "chat.completion",
  "created": 1677652288,
  "choices": [{
    "index": 0,
    "message": {
      "role": "assistant",
      "content": "\n\nHello there, how may I assist you today?",
    },
    "finish_reason": "stop"
  }],
  "usage": {
    "prompt_tokens": 9,
    "completion_tokens": 12,
    "total_tokens": 21
  }
}


## 代理问题

由于众所周知的原因，直接调用 OpenAI API 可能会遇到网络连接问题。解决方案如下：

1. 全局科学上网。
2. 设置代理：

python
openai.proxy = "http://127.0.0.1:1080"


## 参数说明

### `model` 参数

`model` 参数指定使用的模型，目前支持以下模型：

- gpt-4
- gpt-4-0314
- gpt-4-32k
- gpt-4-32k-0314
- gpt-3.5-turbo
- gpt-3.5-turbo-0301

**GPT-3.5 模型说明：**

| 模型名称          | 描述                                   | 最大 Token | 训练数据截止时间 |
|-------------------|----------------------------------------|------------|------------------|
| gpt-3.5-turbo     | 功能最强大的 GPT-3.5 模型，优化聊天场景 | 4,096      | 2021 年 9 月     |
| gpt-3.5-turbo-0301| 2025年1月 1 日的快照版本            | 4,096      | 2021 年 9 月     |

### `messages` 参数

`messages` 参数是当前对话的列表，格式如下：

python
messages = [{"role": "user", "content": "Hello!"}]


- **system**：系统角色，用于提供初始说明。
- **user**：用户提问的内容。
- **assistant**：ChatGPT 返回的内容。

多轮对话需要将之前的对话内容和返回消息一并放入 `messages` 参数中。例如：

python
messages = [
    {"role": "system", "content": "你是一个知识丰富的助手。"},
    {"role": "user", "content": "2022 年世界杯冠军是谁？"},
    {"role": "assistant", "content": "2022 年世界杯冠军是阿根廷。"},
    {"role": "user", "content": "在哪举行？"}
]


### Token 的概念

OpenAI 按照对话和生成的 Token 数量计费。可以通过 `max_tokens` 参数控制生成返回的最大 Token 数量。

官方 Token 统计工具：[OpenAI Tokenizer](https://platform.openai.com/tokenizer)

## 完整示例

以下是一个命令行交互式示例，用户可以输入问题并获取回答：

python
import openai

openai.api_key = "OPENAI_API_KEY"

while True:
    user_input = input("请输入你的问题：")
    if user_input.lower() in ["exit", "quit"]:
        break

    response = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=[
            {"role": "user", "content": user_input}
        ]
    )
    print("ChatGPT:", response.choices[0].message["content"])


---

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard)