
<p align="center">
<div style="text-align: center;">
    <img src="assets/teaser.png" alt="Teaser" width=100% >
</div>
<div align="center">

# InternScenes: A Large-scale Interactive Indoor Scene Dataset with Realistic Layouts

</div>
</p>
<div align="center">
    <a href='https://github.com/InternRobotics/InternScenes'><img src='https://img.shields.io/badge/Paper-arXiv-%232986fc'></a> &nbsp;
    <a href='https://huggingface.co/datasets/InternRobotics/InternScenes'><img src='https://img.shields.io/badge/Data-HuggingFace-%23fe236d?&logo=huggingface'></a> &nbsp;
    <a href='https://marjordcpz.github.io/InternScenes.github.io'><img src='https://img.shields.io/badge/Home-Website-05a4a7?'></a> &nbsp;
</div>


## 🏡 Introduction

  <p>
      <strong>InternScenes</strong> comprises approximately <strong>40,000 diverse scenes</strong> and <strong>1.96M 3D objects</strong> that cover <strong>15 common scene types</strong> and <strong>288 object classes</strong>, which is roughly <strong>10 times larger than existing datasets</strong>.
  </p>

## 💡 Highlights

  <div class="section">
    <p>Existing 3D scene datasets often suffer from:</p>
    <ul>
      <li>❌ Limited diversity or simulatability</li>
      <li>❌ Sanitized layouts lacking small items</li>
      <li>❌ Severe object collisions</li>
    </ul>
  </div>

  <div class="section">
    <p>Accordingly, InternScenes integrates a wide variety of scenes, and particularly, preserves small items for complex layouts, resolve collisions, and further incorporates interactive objects, thus ensures:</p>
    <ul>
      <li>📊 <strong>Large scale</strong>: 40,000 diverse scenes including 1.96M 3D objects covering 288 object classes.</li>
      <li>🚪 <strong>Realistic layouts</strong>: preserving massive small objects to strictly align with real-world scanned scenes.</li>
      <li>🕹️ <strong>Interactivity</strong>: 20% interactive objects inside covering 16 common types, such as cabinets, microwaves, ovens, and fridges.</li>
    </ul>
  </div>

  ### Which tasks will benefit from our dataset?
  <ul>
   <li> ✅ 3D scene reconstruction
   <li> ✅ 3D scene understanding
   <li> ✅ Scene layout generation
   <li> ✅ Embodied navigation
  </ul>

  ### What's included to support these tasks?
  
   1. Convenient and efficient scene rendering scripts;
   2. Detailed object semantic information;
   3. Unified format and coordinate system for scene layouts;
   4. Various trajectories for embodied navigation.

  For the usage of our dataset, please refer to [the tutorials](#-tutorial).

## 🪄 News
  - <code>2025/07</code> InternScenes-Real2Sim v1.0 released.

## 📋 Table of Contents
  - [🏡 Introduction](#-introduction)
  - [💡 Highlights](#-highlights)
  - [🪄 News](#-news)
  - [📋 Table of Contents](#-table-of-contents)
  - [⚙️ Getting Started](#️-getting-started)
  - [📖 Tutorial](#-tutorial)
  - [📋 TODO List](#-todo-list)
  - [🧷 Citation](#-citation)
  - [📄License](#license)
  - [🥰 Acknowledgements](#-acknowledgements)


## ⚙️ Getting Started
### Installation

1. Clone this repository.

```bash
git https://github.com/InternRobotics/InternScenes.git
cd InternScenes
```

2. Create an environment and install basic dependencies.

```bash
conda create -n internscenes python=3.10 -y  
conda activate internscenes
pip install -r requirements.txt
```

3. (optional) Install Isaac-Sim 4.1.0 for rendering *.usd files and convertion *.glb files.
```bash
# Make sure your conda environment is activated.
pip install torch==2.4.0 --index-url https://download.pytorch.org/whl/cu118
pip install isaacsim==4.1.0 isaacsim-extscache-physics==4.1.0 isaacsim-extscache-kit==4.1.0 isaacsim-extscache-kit-sdk==4.1.0 --extra-index-url https://pypi.nvidia.com
```

<!-- 4. (optional) Install Blender for rendering the *.glb files.
```bash

``` -->

### Data Preparation
Please refer to the [guide](https://github.com/InternRobotics/InternScenes/tree/master/data) for downloading and organization.

```shell
InternScenes-Real2Sim/
|-- Assets_library/                 # Assets library of scenes
  |-- objaverse/                      # 1. Objaverse assets library    
  |-- hssd-models/                    # 2. HSSD assets library 
  |-- 3D-FUTURE-model/                # 3. 3D-FUTURE assets library
  |-- gr100/                          # 4. GRScenes-100 assets library
  |-- partNet-mobility/               # 5. PartNet-Mobility assets library
  |-- gen-assets/                     # 6. Generated assets library
|-- Layout_info/                   
  |-- scan_id/
    |-- StructureMesh/              # 3D mesh of the floor and walls
      |-- wall.glb     
    |-- layout.json                 # Layout json of the scene
```

The layout format is listed as follows:
```json
[
    {
        "id": 1,
        "category": "chair",
        "model_uid": "partnet_mobility/39551",
        "bbox": [
            1.041122286614026,
            -1.2630096162069782,
            0.37856578639578786,
            0.42791932981359787,
            0.4573552539873118,
            0.7564487395312743,
            1.384006110201953,
            0.0,
            -0.0
        ]
    },
   ...
]
```

## 📖 Tutorial
We provide a simple tutorial [here](https://github.com/InternRobotics/InternScenes/blob/master/tutorial/tutorial.ipynb) as a guideline for the visualization and basic usage of our dataset. Welcome to try and post your suggestions!


## 📋 TODO List
 - [x] Release the InternScenes-Real2Sim v1.0.
 - [ ] Release trajectories for each scene and rendering scripts.
 - [ ] Release the paper.
 - [ ] Polish the codes of building the InternScenes-Real2Sim.
 - [ ] Release the InternScenes-Real2Sim v2.0.
 - [ ] Release the InternScenes-Synthetic v1.0.
 - [ ] Polish the codes of building the InternScenes-Synthetic.
 - [ ] Release the InternScenes-Synthetic v2.0.

## 🧷 Citation
```BibTex
@inproceedings{InternScenes,
  title={InternScenes: A Large-scale Interactive Indoor Scene Dataset with Realistic Layouts},
  author={Zhong, Weipeng and Cao, Peizhou and Jin, Yichen and Li, Luo and Cai, Wenzhe and Lin, Jingli and Lyu, Zhaoyang and Wang, Tai and Dai, Bo and Xu, Xudong and Pang, Jiangmiao},
  year={2025},
  booktitle={arXiv},
}
```
## 📄License

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/80x15.png" /></a>

This work is under the <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.

## 🥰 Acknowledgements
- [EmbodiedScan](https://github.com/OpenRobotLab/EmbodiedScan): The scenes we retrieve are based on the annotations from EmbodiedScan, which include a large number of 9-DoF bounding boxes for small objects.
- [InternUtopia](https://github.com/OpenRobotLab/GRUtopia) (Previously GRUtopia ): Some of the high-quality 3D asset files (*.usd) in this repository are sourced from here.
- [Hunyuan3D-2.1](https://github.com/tencent-hunyuan/hunyuan3d-2.1): The textures for some of the 3D assets were generated using this model.
- [HSSD](https://github.com/3dlg-hcvc/hssd): A curated selection of object assets from this project has been used to construct our asset library.
- [PartNet-Mobility](https://github.com/haosulab/SAPIEN): A curated selection of object assets from this project has been used to construct our asset library.
- [Objaverse](https://objaverse.allenai.org/): A curated selection of object assets from this project has been used to construct our asset library.
