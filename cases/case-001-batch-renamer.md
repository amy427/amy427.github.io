---
layout: page
title: Case 001 - 批量重命名（Batch Renamer）
permalink: /cases/case-001-batch-renamer/
---

## 需求（用户视角）
我有一堆图片/文件需要按规则统一命名（例如 img_1、img_2…），手工改名费时且容易错。

## 输入
- 一个文件夹（包含若干图片或文件）
- 命名规则：前缀 + 序号（可自定义起始序号）

## 方案
- 支持只处理图片：jpg/jpeg/png/webp
- 先 dry-run 预览，确认无误再执行
- 发现重名冲突立即停止，避免覆盖

## 输出
- 文件按顺序重命名完成（可复用同一规则处理新文件夹）

## 交付物（可复现）
- 工具页：/tools/batch-renamer/
- 源码仓库：https://github.com/amy427/tools-lab/tree/main/batch_renamer
- 一键运行（Windows）：run_windows.bat

## 验收标准
1. dry-run 模式：只显示“旧名 -> 新名”，文件名不变  
2. 执行模式：文件名变为 img_1 / img_2 ...（或自定义前缀）  
3. 若目标文件名已存在：程序停止并提示冲突文件

## 复盘与下一步优化
- 增加：按修改时间排序 / 跳过特定文件名规则（后续迭代）
- 增加：输出重命名清单（csv）
