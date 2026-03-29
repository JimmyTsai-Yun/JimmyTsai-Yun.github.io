---
layout: page
title: 蔡承耘 Jimmy Tsai
subtitle: AI Engineer | Computer Vision | Construction & Manufacturing
---

土木工程背景出身，深耕電腦視覺與深度學習的 AI 工程師。核心定位在於**將 AI 技術落地於建築、營建與製造場域**，擅長將感測器資料、影像辨識與工程知識整合為可實際運作的系統。

從工地人員行為辨識、3D 空間重建、多鏡頭人員追蹤，到工程圖說一致性驗證，每一個專案都從真實問題出發，以嚴謹的工程思維解決它。

📧 jimmytsai1017@gmail.com ｜ 📍 Taichung, Taiwan

---

## Education

**國立臺灣大學 National Taiwan University**
Master's — Civil Engineering (Construction Engineering & Management)
*2023 – 2025* ｜ GPA 4.1/4.3（書卷獎 Dean's Award）

**國立臺灣大學 National Taiwan University**
Bachelor's — Civil Engineering
*2019 – 2023* ｜ GPA 3.7/4.3

---

## Experience

**Stony Brook University — Visiting Scholar**
*Feb 2025 – Aug 2025*

研究工廠環境下的多人跨鏡頭定位與重識別系統。以 Unity 建構虛擬工廠場景，複現 CVPR Workshop 2024 多鏡頭追蹤框架，並以 TensorRT 優化推論速度。

**Stantec Consulting Services Inc. — Summer Intern**
*Jun 2024 – Aug 2024*

數位創新部門實習。使用 LangChain、Google Gemini 與 VectorDB（Chroma）開發 RAG 原型系統，支援內部法規與案例檢索。

**NTUCE-NCREE AI Research Center — Summer Intern**
*Jun 2022 – Aug 2022*

以 ROS 和 RTAB-Map 對 RGB-D 相機與 LiDAR 進行 SLAM 性能評測，開發感測器融合 pipeline，有效量測範圍達 20m（為純 RGB-D 的 4 倍）。

---

## Publication

**Multi-granular Crew Activity Recognition for Construction Monitoring**
*Automation in Construction* (SCI Journal) — Nov 2025
Tsai Cheng Yun, Mik Wanul Khosiin, Jacob J. Lin, Chuin-Shan Chen
National Taiwan University

提出多粒度工班活動辨識框架，以 Graph Neural Network（GNN）與 self-attention 機制整合空間與語意資訊，在鋼筋、模板、混凝土澆置作業資料集上達到整體 F1 Score 70.31%。

---

## Projects

**工程設計文件多模態一致性驗證系統** ｜ *Apr 2025*
結合 AutoLISP 從 AutoCAD 萃取幾何資料，以 YOLO + GPT-4o 解析圖說，自動比對多份文件間的設計數值，並開發 GUI 供工程人員操作。

**多人跨鏡頭定位與追蹤系統** ｜ *Feb – Aug 2025 @ Stony Brook University*
建構 Unity 虛擬工廠場景生成訓練資料，複現幾何一致性多鏡頭追蹤框架（CVPR Workshop 2024），以 TensorRT 加速部署。

**工地人員多粒度行為辨識** ｜ *2023 – 2025（碩士論文）*
以 GNN 對工人空間關係進行圖結構建模，設計階層式多粒度辨識架構，同步輸出個人動作、小組組成與施工任務分類。

**低成本室內平面圖自動生成** ｜ *May 2023*
使用 iPhone 影片配合 COLMAP（SfM）重建室內 3D 點雲，以 RANSAC + Hough Transform 自動提取牆面線段並輸出 2D 向量平面圖。

**Global Motion Compensation 視訊穩定系統** ｜ *May 2024*
實作特徵點匹配與 homography 估算的全域運動補償 pipeline，解決相機移動造成的視訊抖動問題。

---

## Skills

| 類別 | 技術 |
|------|------|
| 程式語言 | Python、C、C++ |
| 深度學習框架 | PyTorch、OpenCV |
| 目標偵測 / 追蹤 | YOLO、SAHI、TensorRT |
| 3D 視覺 | COLMAP（SfM）、RANSAC、Hough Transform |
| 多模態 AI | GPT-4o（VLM）、LangChain、Gemini、Chroma |
| 圖神經網路 | GNN（PyTorch Geometric） |
| BIM / CAD | Revit API（C#）、AutoCAD API（AutoLISP）、SketchUp |
| 感測器融合 | ROS、RTAB-Map、LiDAR、RGB-D |
| 虛擬環境 | Unity3D |
| 開發工具 | Git、Docker、SQL、Flask、Gradio |
| 語言 | 中文（母語）、英文（TOEIC 880） |

---

## Research Interests

- 建築 / 製造場域的電腦視覺應用
- 多鏡頭人員定位、追蹤與重識別
- 工地安全監測與施工生產力分析
- BIM 資料自動化萃取與一致性驗證
- 3D 點雲重建與空間理解
