# FRESCO - Official PyTorch Implementation


**FRESCO: Spatial-Temporal Correspondence for Zero-Shot Video Translation**<br>
[Shuai Yang](https://williamyang1991.github.io/), [Yifan Zhou](https://zhouyifan.net/), [Ziwei Liu](https://liuziwei7.github.io/) and [Chen Change Loy](https://www.mmlab-ntu.com/person/ccloy/)<br>
in CVPR 2024 <br>
[**Project Page**]() | [**Paper**]() | [**Supplementary Video**]() | [**Input Data and Video Results**]() <br>

**Abstract:** *The remarkable efficacy of text-to-image diffusion models has motivated extensive exploration of their potential application in video domains.
Zero-shot methods seek to extend image diffusion models to videos without necessitating model training.
Recent methods mainly focus on incorporating inter-frame correspondence into attention mechanisms. However, the soft constraint imposed on determining where to attend to valid features can sometimes be insufficient, resulting in temporal inconsistency.
In this paper, we introduce FRESCO, intra-frame correspondence alongside inter-frame correspondence to establish a more robust spatial-temporal constraint. This enhancement ensures a more consistent transformation of semantically similar content across frames. Beyond mere attention guidance, our approach involves an explicit update of features to achieve high spatial-temporal consistency with the input video, significantly improving the visual coherence of the resulting translated videos.
Extensive experiments demonstrate the effectiveness of our proposed framework in producing high-quality, coherent videos, marking a notable improvement over existing zero-shot methods.*

**Features**:<br>
- **Temporal consistency**: use robust intra-and inter-frame constraint with better consistency and coverage than optical flow alone.
- **Zero-shot**: no training or fine-tuning required.
- **Flexibility**: compatible with off-the-shelf models (e.g., [ControlNet](https://github.com/lllyasviel/ControlNet), [LoRA](https://civitai.com/)) for customized translation.


## Updates
- [03/2023] Code is released.
- [03/2024] This website is created.

### TODO
- [x] Add webUI.
- [x] Upload paper to arXiv, release related material

## Installation

1. Clone the repository. 

```shell
git clone git@github.com:williamyang1991/FRESCO.git --recursive
cd FRESCO
```

2. You can simply set up the environment with pip based on the `requirements.txt`
- We have tested on torch 2.0.0/2.1.0 and diffusers 0.19.3
- If you use new versions of diffusers, you need to modify [my_forward()](https://github.com/williamyang1991/FRESCO/blob/fb991262615665de88f7a8f2cc903d9539e1b234/src/diffusion_hacked.py#L496)

3. Run the installation script. The required models will be downloaded in `./model`, `./src/ControlNet/annotator` and `./src/ebsynth/deps/ebsynth/bin`.
- Requires access to huggingface.co

```shell
python install.py
```

4. You can run the demo with `run_fresco.py`

```shell
python run_fresco.py ./config/config_music.yaml
```

