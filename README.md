# AUTOMATIC1111 Stable Diffusion WebUI 1.5 + ChilloutMix + Kohya's Scripts

[[Web UI] Go To Colab](https://colab.research.google.com/github/wibus-wee/stable_diffusion_chilloutmix_ipynb/blob/main/stable_diffusion_1_5_webui.ipynb) | [[LoRA Train] Go To Colab](https://colab.research.google.com/github/wibus-wee/stable_diffusion_chilloutmix_ipynb/blob/main/lora_train.ipynb) | [Prompts Collection](/prompts.md)

It does not come with any Loras, you need to type in **CivitAI** to download it yourself, and upload it to the `models/Stable-diffusion` folder. If you enable CiivitAIExtension, you can download it directly from the web UI, but remember to check Save add Additional Network option.

Paperspace is now supported, but it is still recommended to use Colab, because the free Paperspace M4000 GPU currently does not support Xformers, and the speed of generating pictures will be slower than Colab.

> **Warning**: Please note that there may be legal risks before painting. Please note whether your painting may cause controversy and negative impact on the development of the AI community. Please use it with caution.
>
> 绘画前请注意法律风险，请注意您的绘画是否可能会带来争议，对AI社区的发展造成不良的负面影响，请谨慎使用。

## Roadmap

- [x] Paperspace 平台支持
- [x] LoRA 训练 Jupyter Notebook 支持
- [ ] 使用 aria2 优化模型下载速度
- [ ] 国际化 (i18n)
  - [x] README
  - [ ] LoRA Train Notebook
  - [ ] Web UI Notebook

## 关于训练 LoRA

基于 Akegarasu/lora-scripts 制作出了稍微简单的脚本，但我更推荐你使用 [ddPn08/kohya-sd-scripts-webui](https://github.com/ddPn08/kohya-sd-scripts-webui)，它提供了 GUI，更加方便，我在 `stable_diffusion_1_5_webui.ipynb` 中也提供了对应的 SD WebUI 扩展安装方法。

需要注意的是，`Dreambooth Extension for Stable-Diffusion-WebUI` 也是一个用于训练的扩展，一般来说它与 `kohya-sd-scripts` 只需要安装一个即可，我更推荐使用 kohya-sd-scripts

## Loras

- `(x1)` 「🌟」St. Louis (Luxurious Wheels) (Azur Lane): https://civitai.com/models/6669/st-louis-luxurious-wheels-azur-lane
- `(x1)` 「👍」Girls' Frontline-OTs-14"lightning": https://civitai.com/models/6525/girls-frontline-ots-14lightning
- `(x0.5)` 「🌟」@kbr/Korean Doll Likeness: https://civitai.com/models/7448/korean-doll-likeness
- `(x0.5)` 「🆒」@kbr/Japanese Doll Likeness: https://civitai.com/models/10135
- `(x0.5)` 「🆒」@kbr/Taiwan Doll Likeness  : https://civitai.com/models/7716/taiwan-doll-likeness
- `(x0.5)` 「🆒」Yae Miko | Realistic Genshin (Mixed): https://civitai.com/models/8484/yae-miko-or-realistic-genshin
- `(x0.5)` 「👍」Gakki | Aragaki Yui | 新垣結衣: https://civitai.com/models/8416/gakki-or-aragaki-yui-or

## Checkpoints

- [2.5D] ChilloutMix: https://civitai.com/models/6424/chilloutmix
- [2.5D] SunshineMix (偏向插画类): https://civitai.com/models/9291/sunshinemix
- [2D] Grapefruit (hentai model): https://civitai.com/models/2583/grapefruit-hentai-model

## 试验性 Lora

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

- **README.md**
  - 更新「试验性 Lora」列表 | Update Experimental Lora List
  - 优化 CHANGELOG 格式 | Optimize CHANGELOG format
  - 国际化 README | Internationalize README
- **lora_train.ipynb**
  - 修复 LoRA 训练脚本中的严重错误 | Fix serious errors in LoRA training script
  - 移除无必要的平台与 GPU 检查 | Remove unnecessary platform and GPU checks
  - 新增 `export_model_dir` 选项，用于指定导出模型的目录 | Add `export_model_dir` option to specify the directory where the model is exported

### 2023.2.24

- **workflows**
  - Pull Request 时自动评论 Preview 链接 | Automatically comment on Preview link when Pull Request ( https://github.com/wibus-wee/stable_diffusion_chilloutmix_ipynb/pull/2 )
- **stable_diffusion_1_5_webui.ipynb**
  - Stable-Diffusion-WebUI 搭配安装 controlnet, openpose-editor, Kohya sd-scripts 扩展 | Install controlnet, openpose-editor, Kohya sd-scripts extension with Stable-Diffusion-WebUI
  - 移除旧有的训练模型安装方案，合并进入安装步骤 | Remove the old training model installation scheme and merge it into the installation steps ( created in 2023.2.19 )
- **lora_train.ipynb**
  - 新 Lora Train 脚本 ( Alpha ) | New Lora Train Script ( Alpha )

### 2023.2.21

- **stable_diffusion_1_5_webui.ipynb**
  - 更好的选项选择机制 | Better option selection mechanism
  - 细化区分 Paperspace 与 Colab 平台而并非靠单一 Free GPU 型号 | Fine distinction between Paperspace and Colab platforms rather than relying on a single Free GPU model

### 2023.2.19

- **stable_diffusion_1_5_webui.ipynb**
  - 修复错误识别 Quadro M4000 GPU 的问题 | Fix the problem of incorrectly identifying the Quadro M4000 GPU
  - 新增**训练模型**安装方案 | Add **Training Model** Installation Scheme ( Power by [d8ahazard/sd_dreambooth_extension](https://github.com/d8ahazard/sd_dreambooth_extension))
  - 优化 checkpoint 选择 | Optimize checkpoint selection
  - 修复无法读取变量的问题 | Fix the problem of not being able to read variables
  - 自动检查 webUI 与 训练扩展是否被安装 | Automatically check whether webUI and training extensions are installed

### 2023.2.18

- **stable_diffusion_1_5_webui.ipynb**
  - 更新上游 ChilloutMix 最新版本 | Update the latest version of the upstream ChilloutMix
  - 更新 Prompts Collection | Update Prompts Collection
  - 兼容 Paperspace 平台（ Free GPU ） | Compatible with Paperspace platform (Free GPU)
  - 导出全部生成图片 | Export all generated images
  - 使用 `nvidia-smi` 查看 GPU 信息 | Use `nvidia-smi` to view GPU information
  - 检查 GPU 是否支持 Xformers | Check if GPU supports Xformers
  - 优化变量传递 | Optimize variable passing

### 2023.2.17

- **stable_diffusion_1_5_webui.ipynb**
  - 新增 SunshineMix Checkpoint 作为 2.5D 作画的第二选择 | Add SunshineMix Checkpoint as a second choice for 2.5D painting

### 2023.2.16
- **stable_diffusion_1_5_webui.ipynb**
  - 由于中途可能会出现突然退出的情况，所以提供多了一个再次启动的方案 | Because there may be a sudden exit in the middle, there is another way to restart

---

> Created by [@wibus-wee](https://github.com/wibus-wee)
>
> Reference: [camenduru/stable-diffusion-webui-colab](https://github.com/camenduru/stable-diffusion-webui-colab)
