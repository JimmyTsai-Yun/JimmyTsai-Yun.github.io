---
layout: post
title: 多鏡頭跨場景人員追蹤：從問題定義到系統設計
subtitle: 工廠安全監測中的 Re-ID 挑戰與解法
tags: [computer-vision, multi-camera, re-identification, deep-learning]
readtime: true
---

在工廠環境中，工人與機械手臂共享作業空間，**即時掌握人員位置**是避免碰撞事故的關鍵。
然而當環境中有多支監視攝影機時，要跨鏡頭持續追蹤同一個人，遠比想像中困難。

---

## 問題在哪？

單鏡頭追蹤（Single-Camera Tracking）相對成熟，但跨鏡頭面臨三大挑戰：

1. **視角差異** — 同一個人從不同角度看起來完全不同
2. **遮蔽（Occlusion）** — 人員被設備或其他工人擋住，導致 ID 遺失
3. **外觀相似** — 工廠人員通常穿著相同工作服，難以區分

---

## 解法架構

我在 Stony Brook University 的研究中複現了 CVPR Workshop 2024 的多鏡頭追蹤框架，核心思路是結合**幾何一致性**與 **Re-ID 特徵**：

```
輸入：N 支攝影機的即時影像
  │
  ▼
[YOLOv8] 各鏡頭偵測人員 bounding box
  │
  ▼
[幾何一致性] 2D IoU + Epipolar constraint + Homography affinity
  │
  ▼
[Re-ID] State-aware appearance feature matching
  │
  ▼
輸出：跨鏡頭統一 ID + 3D 位置估計
```

### 幾何一致性為什麼重要？

單靠外觀特徵（Re-ID）容易在工廠環境中誤配對，因為工作服太相似。
加入幾何約束後，系統會先確認「這兩個偵測結果在 3D 空間中是否合理共存」，大幅降低誤配率。

---

## 虛擬資料集的角色

真實工廠資料難以取得（隱私、標注成本），我們用 **Unity** 建構虛擬工廠場景：

- 可自由配置鏡頭角度、光線、人員數量
- 自動生成 ground truth 標注
- 支援極端情境（高遮蔽率、低光源）測試

---

## 部署優化：TensorRT

研究驗證後，推論速度是部署的瓶頸。
以 TensorRT 對 YOLOv8 + Re-ID 模型進行量化與圖優化後，延遲從 **~120ms 降至 ~35ms**，達到接近即時的處理速度。

---

## 小結

| 技術 | 作用 |
|------|------|
| YOLOv8 | 人員偵測 |
| Epipolar geometry | 跨鏡頭幾何驗證 |
| Re-ID network | 外觀特徵比對 |
| TensorRT | 推論加速 |
| Unity | 虛擬訓練資料生成 |

這個系統目前能在 4 鏡頭配置下穩定運作，未來方向是擴展到更大規模場景與動態鏡頭配置。
