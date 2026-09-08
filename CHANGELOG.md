# 迭代日志

按时间顺序记录每一次调试。每条对应一次 git commit。

## 2026-09-07 读懂算法

- 会话：Codex `kan` / 分析算法实现
- 结论：几何搜索 + 射线测量 + 布尔切削，不是 ML 定位器
- 文档：`01-algorithm.md`

## 2026-09-07 提出加速方案

- 基线 73s，瓶颈在加载、朝向、视觉门、选面
- 方案：粗到细、代理网格、跳过 1.1 循环、射线缓存
- 文档：`02-speed-plan.md`

## 2026-09-08 73s → 57s

- 向量化朝向、粗搜精搜、跳过视觉门
- 输出 `Hy3D_textured_00006_opt`
- 文档：`03-speed-57s.md`

## 2026-09-08 57s → 16s

- 默认减到 5 万面，适配 FDM
- 输出 `Hy3D_textured_00006_print50k`
- 文档：`04-print-50k.md`

## 2026-09-08 16s → 11.5s

- 跳过二次修网格、空壳诊断；选面收到 16 点
- 输出 `Hy3D_textured_00006_print50k_fast`
- 文档：`05-speed-11s.md`

## 2026-09-08 接入 DeepSeek 视觉

- 模型 `deepseek-v4-flash-vision-exp`，`--vision-mode always`
- 文档：`06-vision-setup.md`

## 2026-09-08 第一次视觉跑偏

- 50k 网格被 PCA 拧 82°，视觉抄示例坐标
- 开孔落到 `(8.0, 44.7)`，不是上背
- 文档：`07-vision-wrong.md`
