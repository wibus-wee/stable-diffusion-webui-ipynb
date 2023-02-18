# Prompts Collections - 标签集合

先介绍两种标签：

- **SFW**: Safe For Work - 较为安全
- **NSFW**: Not Safe For Work - **不安全 请勿在有客人的地方打开此类图片**

大部分为 `SFW` 标签

## `[SFW]` Cat ears + Blue eyes

<details>
  <summary> <h3>Demo</h3> </summary>
  <img src="https://user-images.githubusercontent.com/62133302/219822038-e60ff34c-f231-4a9a-a2fc-18de6af63415.png">
</details>

### Prompts

```
best quality, ultra high res, (photorealistic:1.4), 1 white child, (ulzzang-6500:1.0), smiling, (PureErosFace_V1:1.0), ((detailed facial features)), alluring blue eyes, photographed on a Canon EOS R5, 50mm lens, F/2.8, HDR, 8k resolution, ulzzang-6500, (kpop idol), aegyo sal, from side, looking at camera, cat ears, sports bra,
```

### Negative prompts

```
paintings, sketches, (worst quality:2), (low quality:2), (normal quality:2), lowres, normal quality, ((monochrome)), ((grayscale)), skin spots, acnes, skin blemishes, age spot, glans
```

### Others

- Steps: 25
- Sampler: DPM++ 2M Karras
- CFG scale: 7
- Size: 512x512
- Model: chilloutmix
- AddNet Enabled: True
- AddNet Module 1: LoRA, AddNet Model 1: koreanDollLikeness_v10(e2e472c06607), AddNet Weight A 1: 0.5, AddNet Weight B 1: 0.5, 
- AddNet Module 2: LoRA, AddNet Model 2: stLouisLuxuriousWheels_v1(034b97419349), AddNet Weight A 2: 1, AddNet Weight B 2: 1

## [SFW] Blue long hair


<details>
  <summary> <h3>Demo</h3> </summary>
  <img src="https://user-images.githubusercontent.com/62133302/219822684-365dcffc-5f40-460a-8638-4869bbc8624e.png">
</details>

### Prompts

```
best quality, blue long hair, ultra high res, (photorealistic:1.4), 1girl,silver dress
```

### Negative prompts

```
EasyNegative, paintings, sketches, (worst quality:2), (low quality:2), (normal quality:2), lowres, normal quality, ((monochrome)), ((grayscale)), skin spots, acnes, skin blemishes, age spot, glans,extra fingers,fewer fingers,
```

- Steps: 25, 
- Sampler: DPM++ 2M Karras, 
- CFG scale: 7, 
- Model: chilloutmix, 
- AddNet Enabled: True, 
- AddNet Module 1: LoRA, AddNet Model 1: koreanDollLikeness_v10(e2e472c06607), AddNet Weight A 1: 0.5, AddNet Weight B 1: 0.5, 
- AddNet Module 2: LoRA, AddNet Model 2: stLouisLuxuriousWheels_v1(034b97419349), AddNet Weight A 2: 1, AddNet Weight B 2: 1
