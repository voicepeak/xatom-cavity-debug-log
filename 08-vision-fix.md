# 8. 修正朝向与视觉点

改动：

1. 水平 PCA 若接近 90° 横拧，直接拒绝，保住轴对齐
2. 提示词去掉 `0.5/0.55` 数字示例，要求上背/肩胛，禁止臀部和腿
3. 视觉 UV 随 yaw 转到模型坐标，不再被躯干中心覆盖

命令同前：`--vision --vision-mode always`  
输出：`e2e_demo/Hy3D_textured_00006_deepseek2`

结果：

- PCA：`sideways_pca_rejected_keep_axis_aligned_frame`
- 视觉：`view_3` 正面（眼鼻嘴），`view_0` 背面
- 建议点：`u=0.50, v=0.35`（上背）
- 实际开孔：`(-7.2, 103.3)` mm
- 耗时：14.8s
