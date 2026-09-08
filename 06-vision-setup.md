# 6. 接入视觉

此前 `--back-only` 纯几何，`api_called: false`。

配置（`.env`）：

```
XATOM_LLM_API_KEY=<deepseek key>
XATOM_LLM_BASE_URL=https://api.deepseek.com
XATOM_LLM_VISION_MODEL=deepseek-v4-flash-vision-exp
XATOM_LLM_THINKING=disabled
```

命令：`--vision --vision-mode always`

视觉只判正反面和开孔画面坐标，深度/壁厚仍由几何终验决定。
