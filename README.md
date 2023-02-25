# AUTOMATIC1111 Stable Diffusion WebUI 1.5 + ChilloutMix Checkpoint

[[Web UI] Go To Colab](https://colab.research.google.com/github/wibus-wee/stable_diffusion_chilloutmix_ipynb/blob/main/stable_diffusion_1_5_webui.ipynb) | [[LoRA Train] Go To Colab](https://colab.research.google.com/github/wibus-wee/stable_diffusion_chilloutmix_ipynb/blob/main/lora_train.ipynb) | [Prompts Collection](/prompts.md)

不附带任何 Loras，需要在 **CivitAI** 中输入自行下载，记住勾选保存加入 Additional Network 选项。默认使用 ChilloutMix Checkpoint，可另外选择 SunshineMix Checkpoint

目前已经支持 Paperspace 平台，但仍建议使用 Colab，因为目前免费使用的 Paperspace M4000 GPU 暂无 Xformers 支持，在生成图片时速度会慢于 Colab。

## Roadmap

- [x] Paperspace 平台支持
- [x] LoRA 训练 Jupyter Notebook 支持
- [ ] 使用 aria2 优化模型下载速度
- [ ] 国际化 (i18n)

## 关于训练 LoRA

> **Warning**: 训练 LoRA 前请先注意法律风险，选取了不合适素材来训练可能会带来争议，对AI社区的发展造成不良的负面影响，请谨慎选择素材。

基于 Akegarasu/lora-scripts 制作出了稍微简单的脚本，但我更推荐你使用 [ddPn08/kohya-sd-scripts-webui](https://github.com/ddPn08/kohya-sd-scripts-webui)，它提供了 GUI，更加方便，我在 `stable_diffusion_1_5_webui.ipynb` 中也提供了对应的 SD WebUI 扩展安装方法。

需要注意的是，`Dreambooth Extension for Stable-Diffusion-WebUI` 也是一个用于训练的扩展，一般来说它与 `kohya-sd-scripts` 只需要安装一个即可，我更推荐使用 kohya-sd-scripts

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

> **Warning**: 请注意法律风险。如果你不知道你在做什么，请不要使用这些模型。

试验性 LoRA 是指测试暂时还不够完整的模型，还未判断出兼容性如何，如果你想要使用这些模型，请自行判断与其他 LoRA 的兼容性。

- liuyifei: https://civitai.com/models/8453/liuyifei
- Lisa Blackpink: https://civitai.com/models/8605/lisa-blackpink
- Jisoo Blackpink: https://civitai.com/models/8311/jisoo-blackpink
- Rosè Blackpink: https://civitai.com/models/8600/rose-blackpink
- Ulzzang-6500 (Korean doll aesthetic): https://civitai.com/models/8109/ulzzang-6500-korean-doll-aesthetic
- Pure Eros Face: https://civitai.com/models/4514/pure-eros-face

## 试验性 CheckPoints

- None

## 更新日志

### 2023.2.25

- **文档**
  - 更新「试验性 Lora」列表
- **lora_train.ipynb**
  - 修复 LoRA 训练脚本中的严重错误
  - 移除无必要的平台与 GPU 检查
  - 新增 `export_model_dir` 选项，用于指定导出模型的目录

### 2023.2.24

- Pull Request 时自动评论 Preview 链接 ( https://github.com/wibus-wee/stable_diffusion_chilloutmix_ipynb/pull/2 )
- Lora Train 脚本 ( Alpha )
- Stable-Diffusion-WebUI 搭配安装 controlnet, openpose-editor, Kohya sd-scripts 扩展
- 移除旧有的训练模型安装方案，合并进入安装步骤 ( created in 2023.2.19 )

### 2023.2.21

- 更好的选项选择机制
- 细化区分 Paperspace 与 Colab 平台而并非靠单一 Free GPU 型号

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
