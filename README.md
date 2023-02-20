# AUTOMATIC1111 Stable Diffusion WebUI 1.5 + ChilloutMix Checkpoint

[Go To Colab](https://colab.research.google.com/github/wibus-wee/stable_diffusion_chilloutmix_colab/blob/main/stable_diffusion_1_5_webui.ipynb) | [Prompts Collection](/prompts.md)

不附带任何 Loras，需要在 **CivitAI** 中输入自行下载，记住勾选保存加入 Additional Network 选项。默认使用 ChilloutMix Checkpoint，可另外选择 SunshineMix Checkpoint

目前已经支持 Paperspace 平台，但仍建议使用 Colab，因为目前免费使用的 Paperspace M4000 GPU 暂无 Xformers 支持，在生成图片时速度会慢于 Colab。

## 训练模型安装启动与一般安装启动区别

训练模型将会加载 `Dreambooth Extension for Stable-Diffusion-WebUI` 插件，该插件将会在生成图片时自动保存到本地，而不是直接在网页上显示。

与一般的启动不同也就只在于这里，由于 `Dreambooth Extension for Stable-Diffusion-WebUI` 的特殊性，我需要在启动前加入一些额外的代码。

```bash
export REQS_FILE="./extensions/sd_dreambooth_extension/requirements.txt"
```

但一般情况下我们并不需要训练模型，所以我将其放在了一个单独的区块中，如果你不需要训练模型，可以不使用它，它会拖慢启动速度 ( Git Clone, Install Requirements ), 当然，这不会影响生成图片的速度。

训练模型我推荐使用 Colab，因为 Paperspace 平台的 M4000 GPU 暂无 Xformers 支持，所以在训练时速度会慢于 Colab。

### ⚠️ 注意

根据目前我所了解的信息，sd_dreambooth_extension 似乎无法很好地工作，训练效果并不理想。现在更推荐使用 [bmaltais/kohya_ss](https://github.com/bmaltais/kohya_ss) / [Akegarasu/lora-scripts](https://github.com/Akegarasu/lora-scripts)

新的 Jupyter Notebook 正在来的路上 (Power by [Akegarasu/lora-scripts](https://github.com/Akegarasu/lora-scripts)) 

- 由于 Colab 无法使用 Docker，因此大概率无法使用现存的 kohya_ss gui  ( [googlecolab/colabtools - #299](https://github.com/googlecolab/colabtools/issues/299) )

## Loras

- `(x1)` 「兼容性极佳」St. Louis (Luxurious Wheels) (Azur Lane): https://civitai.com/models/6669/st-louis-luxurious-wheels-azur-lane
- `(x1)` 「兼容性良好」Girls' Frontline-OTs-14"lightning": https://civitai.com/models/6525/girls-frontline-ots-14lightning
- `(x0.5)` 「兼容性优秀」@kbr/Korean Doll Likeness: https://civitai.com/models/7448/korean-doll-likeness
- `(x0.5)` 「兼容性中等」@kbr/Japanese Doll Likeness: https://civitai.com/models/10135
- `(x0.5)` 「兼容性中等」@kbr/Taiwan Doll Likeness  : https://civitai.com/models/7716/taiwan-doll-likeness
- `(x0.5)` 「兼容性中等」Yae Miko | Realistic Genshin (Mixed): https://civitai.com/models/8484/yae-miko-or-realistic-genshin
- `(x0.5)` 「兼容性良好」Gakki | Aragaki Yui | 新垣結衣: https://civitai.com/models/8416/gakki-or-aragaki-yui-or

## Checkpoints

- [三次元] ChilloutMix: https://civitai.com/models/6424/chilloutmix
- [二点五次元] SunshineMix (偏向插画类): https://civitai.com/models/9291/sunshinemix
- [二次元] Grapefruit (hentai model): https://civitai.com/models/2583/grapefruit-hentai-model

## 试验性 Lora

> **Warning**: Please be aware of the legal issues

- 「质量一般」liuyifei: https://civitai.com/models/8453/liuyifei
- 「兼容性较为一般」Lisa Blackpink: https://civitai.com/models/8605/lisa-blackpink
- 「与描述不匹配」Jisoo Blackpink: https://civitai.com/models/8311/jisoo-blackpink
- 「与描述不匹配，但不看描述还算可以，兼容性良好」Rosè Blackpink: https://civitai.com/models/8600/rose-blackpink

## 试验性 CheckPoints

- None

## 更新日志

### 2023.2.19

- 修复错误识别 Quadro M4000 GPU 的问题
- 新增**训练模型**安装方案 ( Power by [d8ahazard/sd_dreambooth_extension](https://github.com/d8ahazard/sd_dreambooth_extension))
- 优化 checkpoint 选择
- 修复无法读取变量的问题
- 自动检查 webUI 与 训练扩展是否被安装

### 2023.2.18

- 更新上游 ChilloutMix 最新版本
- 更新 Prompts Collection
- 兼容 Paperspace 平台（ Free GPU ）
- 导出全部生成图片
- 使用 `nvidia-smi` 查看 GPU 信息
- 检查 GPU 是否支持 Xformers
- 优化变量传递

### 2023.2.17

- 新增 SunshineMix Checkpoint 作为 2.5D 作画的第二选择

### 2023.2.16

- 由于中途可能会出现突然退出的情况，所以提供多了一个再次启动的方案

---

> Created by [@wibus-wee](https://github.com/wibus-wee)
>
> Reference: [camenduru/stable-diffusion-webui-colab](https://github.com/camenduru/stable-diffusion-webui-colab)
