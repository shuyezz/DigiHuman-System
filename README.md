DigiHuman - 多模态数字人交互系统

A deployable, real-time multimodal Digital Human system
基于大语言模型 + 情感分析 + 语音合成 + VRM 协议的数据驱动数字人系统

🎬 演示视频（2分钟）
👉 https://b23.tv/BV19YASz9Ed3

📌 Project Overview 项目概述

DigiHuman 是一个完整的、可部署的、多模态实时数字人交互系统。

用户可通过浏览器访问系统，与数字人进行自然语言对话。系统后端集成大语言模型、情感分析模型、语音合成模型以及实时数据驱动模块，前端基于 VRM 协议驱动 3D 虚拟形象，实现：

文本对话

语音合成

情绪驱动表情

实时唇形同步

可扩展知识图谱模块

可定制虚拟形象生成

系统采用前后端分离架构，支持模块化扩展与模型替换。

🏗 System Architecture 系统架构

系统整体采用：

Frontend：Next.js + Three.js + VRM

Backend：Flask + PyTorch

Cache：Redis

Database：MySQL

Object Storage：OSS

数据流说明

用户输入提示词

后端调用 Ollama LLM 生成文本

文本送入：

GPT-SoVITS → 语音合成

Text2Emotion → 情绪权重分析

后端生成符合 VRM 协议的数据格式

前端通过 Three.js 实时驱动模型

Redis 进行缓存复用

实现真正的“后端生成数据，前端驱动形象”的实时数据流。

🔄 实时数据驱动机制

系统基于 VRM 虚拟人协议 的数据格式：

后端生成：

text

emotion 权重

audio

前端根据数据实时渲染形象

优点：

解耦模型计算与渲染

降低前端计算压力

提升实时性

支持缓存模块复用

🛠 Tech Stack 技术栈
前端

Next.js

Three.js

VRM 协议

Material You UI

仓库地址：
👉 https://github.com/shuyezz/DigiHuman-app

后端

Flask

PyTorch

Ollama LLM

GPT-SoVITS

Text2Emotion

Redis

MySQL

仓库地址：
👉 https://github.com/shuyezz/DigiHuman-backend

🧠 核心算法设计
1️⃣ 唇形同步算法

基于论文：

A Practical and Configurable Lip Sync Method for Games

VRM 协议规定 5 个元音 (a,e,i,o,u) 作为嘴型控制维度。

构建 5×5 = 25 个元音对模板

后端使用 MFCC 频谱相关性算法识别“元音对”

从模板中匹配嘴型

特点：

计算量小

匹配速度快

实时性高

2️⃣ 表情计算模块

基于预训练模型：

emotion-english-distilroberta-base

对用户文本进行情感分类

输出七类情绪权重

数字人表情根据权重动态变化

提升交互真实感。

3️⃣ 知识图谱模块（可选）

参考 LightRAG 思路：

文本提取与分块

面向查询的摘要

构建图社区

生成全局答案

适用于领域知识增强问答。

4️⃣ 数字人可定制化

基于 Diffusion 扩散模型：

从单张图片生成完整 3D 纹理

SMPL 模型贴图生成

Three.js 渲染

实现个性化虚拟形象生成。

🚀 Deployment 部署方式
前端
git clone https://github.com/shuyezz/DigiHuman-app
pnpm install
pnpm dev
后端
git clone https://github.com/shuyezz/DigiHuman-backend
pip install -r requirements.txt
python app.py
📄 项目进展

阶段一汇报文档：
📎 

阶段一进展

📈 项目亮点总结

前后端分离架构

实时数据驱动 VRM 渲染

自研唇形同步算法

情感分析驱动表情

多模态输出（文本 + 音频 + 表情）

支持知识图谱扩展

支持个性化虚拟人生成

🎯 项目目标

构建一个：

可部署

可扩展

模块解耦

支持多模型替换

面向真实应用场景

的数字人系统框架。

🔚

这个 README 的设计目标是：

3 分钟让面试官理解你做了什么
5 分钟判断你具备系统级工程能力

而不是展示所有细节。