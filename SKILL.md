---
name: photo-color-extension-poster
description: Turn real photographs into 2:3 portrait travel posters with an upper photographic half and a connected original color illustration below, coordinated source colors, a tiny interacting traveler and generous ivory whitespace. Use for 实景延伸彩色插画旅行海报; not full-photo style transfer or photo grids.
---

# 实景延伸彩色插画旅行海报

## 画面合同

- 每张输入生成一张独立2:3竖版海报，上下区域各50%，中线为延伸交接基准。若旧文案同时提到55%–65%摄影，以严格50/50为准。局部过渡可沿真实地形或植物起伏，不画水平分割线。
- 上半部保留原始摄影主体、人物、建筑、动物、光线、色彩、构图和清晰度。禁止重绘、模糊、拉伸、镜像、复制或更改内容。仅允许少量等比例裁切或自然边缘延展；优先保留全部源图。不要把横图强行裁成竖图再塞入上半部。
- 下半部为原创彩色编辑插画，不再采用纯黑白线稿。提取源图3–5种颜色，低饱和、轻薄色块、自然手绘轮廓与少量铅笔笔触，保持与照片协调。不得固定套用秋日黄棕色；蓝海、夜景、雪景等按其真实配色适配。
- 从真实水面、岸线、道路、树干、山坡、建筑支架等择优选一条延伸线索，记录其源图位置与走向。连续穿过中线，不留空隙、不错位、不另起笔。摄影纹理沿真实轮廓逐渐概括为彩色插画，禁止白雾带、照片边框和断开的上下画面。
- 延伸近景，保持同一空间的视角、透视与尺度，不在下方复刻上部主体。人物与延伸物有明确接触或使用关系：脚踏连续岸线、手扶连续支架、坐在延展树根旁等；不可悬浮或成为孤立图标。
- 小人物高度为全图7%–10%，简化服饰与道具，无清晰五官，动作按照片原创。画面克制，暖白象牙纸底，极淡细纤维纹理，哑光、不泛黄。下半部建议至少65%保持安静留白。
- 配一句2–5个英文单词的温柔手写旁白，字号小，非主标题。禁止大字、网格、邮票、边框、水印、手机界面、Q版、粗黑描边、密集绘画、荧光色与厚重滤镜。

## 执行

1. 查看每张原图，登记输入文件、原尺寸、主要主体、延伸锚点、配色、人物动作与英文短句。批量任务逐张原创，不用一套动作复制所有照片。
2. 先读取并调用全局 `$legacy-imagegen`。通过其 `scripts/legacy-imagegen.ps1 edit` 传入单张原图；保持CLI 0.128.0、gpt-5.5及独立认证目录，遵循该技能的登录与运行规则。不修改其运行时，不复用App认证。
3. 使用下列提示词骨架填入图片专属细节，保存每张实际提示词。原图单独保留，成品使用独立名称。
4. 检查工具返回的真实文件；若隔离会话不能复制输出，主会话可将已经生成的文件复制到工作目录。不要猜文件名、把文本答复当成成品或以无限重试绕过失败。后端不可用时遵循legacy技能的降级规则。
5. 逐张查看成品，核对2:3尺寸、中线衔接、原图内容、彩色画风、人物比例/支撑/互动、文字、留白和禁止项。有明确缺陷时只针对该缺陷迭代，并重申保留约束。
6. 交付所有成品、提示词及逐文件清单，清单记录源图、输出、尺寸、创意、视觉检查与原图保留状态。技术尺寸检查不代替视觉检查。

## 原图保留的诚实边界

提示词要求保留不等于已经逐像素保留。生成式编辑常重构照片，必须对比源图；未验证源图像素一致时，标为“生成式编辑，非逐像素保留”，不得声称严格原图保留合格。若用户要求像素级保留，需采用其允许的原图层合成方案并验证；没有实现时明确标注限制，不擅自放宽要求。

## 提示词骨架

```text
Use case: photo-preserving editorial travel poster with original color illustration extension.
Input: supplied photo is the edit target. Preserve all source people, objects, landscape, light, color, geometry and photographic detail; no repainting, stretch, mirror, duplication or blur.
Output: one 2:3 portrait poster, upper 50% photograph, lower 50% illustration, handover anchored at exact center without hard horizontal edge or fog band. Fit source proportionally; preserve its composition with minimal crop.
Anchor: {real element, source normalized position, direction and perspective}; continuously extend it into the foreground below the center, no gap or restart.
Illustration: {source-specific original foreground and interaction}; one tiny adult traveler of 7–10% total height, visibly grounded, no detailed face; original contemporary colored editorial illustration with soft thin color shapes and relaxed hand-drawn contours.
Palette: {3–5 source-derived colors}; restrained saturation, harmonious with photo, no monochrome-only lower section.
Paper/space: neutral warm-white ivory, barely perceptible fibers, matte; generous blank paper, sparse near-ground detail; no repeated upper scene.
Text verbatim: "{2–5 word phrase}" in tiny gentle handwriting, no main headline.
Avoid: disconnection, floating figures, isolated icons, chibi, large characters/text, thick outlines, dense painting, neon, overly yellow paper, collage, stamps, grids, frames, watermark or UI.
```
