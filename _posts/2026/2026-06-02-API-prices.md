---
layout: post
title: 2026-06-02-大模型API价格
categories: [AI]
description: 记录对比一下我想用的几家AI的API价格
keywords: AI
date: 2026-06-02
---

记录对比一下我想用的几家AI的API价格


## Claude 

| Model | Base Input Tokens | 5m Cache Writes | 1h Cache Writes | Cache Hits & Refreshes | Output Tokens | 
| ----- | ----- | ----- | ----- | ----- | ----- | 
| Claude Opus 4.8 | $5 / MTok | $6.25 / MTok| $10 / MTok | $0.50 / MTok | $25 / MTok |
| Claude Opus 4.7 | $5 / MTok | $6.25 / MTok | $10 / MTok | $0.50 / MTok | $25 / MTok |
| Claude Opus 4.6 | $5 / MTok | $6.25 / MTok | $10 / MTok | $0.50 / MTok | $25 / MTok |
| Claude Opus 4.5 | $5 / MTok | $6.25 / MTok | $10 / MTok | $0.50 / MTok | $25 / MTok |
| Claude Opus 4.1 | $15 / MTok | $18.75 / MTok | $30 / MTok | $1.50 / MTok | $75 / MTok |
| Claude Sonnet 4.6 | $3 / MTok | $3.75 / MTok | $6 / MTok | $0.30 / MTok | $15 / MTok |
| Claude Sonnet 4.5 | $3 / MTok | $3.75 / MTok | $6 / MTok | $0.30 / MTok | $15 / MTok |

## ChatGPT
> Short: <272K; Long: >272K     
> 价格是每百万（1M）Token

| Model | Short context Input | Short context Cached input | Short context Output | Long context Input | Long context Cached input | Long context Output |
|-------|--------------------|-----------------------------|----------------------|--------------------|--------------------------|---------------------|
| gpt-5.5 | $5.00 | $0.50 | $30.00 | $10.00 | $1.00 | $45.00 |
| gpt-5.5-pro | $30.00 | - | $180.00 | $60.00 | - | $270.00 |
| gpt-5.4 | $2.50 | $0.25 | $15.00 | $5.00 | $0.50 | $22.50 |
| gpt-5.4-mini | $0.75 | $0.075 | $4.50 | - | - | - |
| gpt-5.4-nano | $0.20 | $0.02 | $1.25 | - | - | - |
| gpt-5.4-pro | $30.00 | - | $180.00 | $60.00 | - | $270.00 |

## DeepSeek

| 模型 | 上下文长度 | 输出长度 | 缓存输入 | 非缓存输入 | 输出 |
| ----- | ----- | ----- | ----- | ----- | ----- |
| DeepSeek-V4-Flash | 1M | 384K max | 0.02元/MTok | 1元/MTok | 2元/MTok |
| DeepSeek-V4-Pro | 1M | 384K max | 0.025元/MTok | 3元/MTok | 6元/MTok |

## Grok
> Grok Pricing页面能直接用markdown格式展示报价，赞！   
> 价格是每百万（1M）Token

| Model | Context | Input / 1M tokens | Output / 1M tokens |
| --- | --- | --- | --- |
| grok-4.3 | 1M | $1.25 | $2.50 |
| grok-4.20-0309-reasoning | 1M | $1.25 | $2.50 |
| grok-4.20-0309-non-reasoning | 1M | $1.25 | $2.50 |
| grok-build-0.1 | 256k | $1.00 | $2.00 |
| grok-4.20-multi-agent-0309 | 1M | $1.25 | $2.50 |

### Imagine Pricing

| Model | Cost |
| --- | --- |
| grok-imagine-image | $0.02 / image |
| grok-imagine-image-quality | $0.05 / image |
| grok-imagine-image | $0.02 / image |
| grok-imagine-image-quality | $0.05 / image |
| grok-imagine-image-quality | $0.05 / image |
| grok-imagine-image | $0.02 / image |
| grok-imagine-video | $0.050 / sec |
| grok-imagine-video-1.5-preview | $0.080 / sec |
| grok-imagine-video | $0.050 / sec |
| grok-imagine-video-1.5-preview | $0.080 / sec |
| grok-imagine-video-1.5-preview | $0.080 / sec |
| grok-imagine-video | $0.050 / sec |

### Voice Pricing

| Mode | Cost |
| --- | --- |
| Realtime | $0.05 / min ($3.00 / hr) |
| Realtime Text Input | $0.004 / message (every conversation.item.create) |
| Text to Speech | $15.00 / 1M chars |
| Speech to Text | $0.10 / hr (REST), $0.20 / hr (Streaming) |