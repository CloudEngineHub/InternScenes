# Prepare InternScenes-Real2Sim Data

## **Data Download**  

We currently host our dataset on [Hugging Face](https://huggingface.co/datasets/InternRobotics/InternScenes), but we only provide 3D assets in GLB format. 
For access to the original file formats (e.g., URDF files from PartNet-Mobility), we recommend downloading the raw data directly from their official websites. Below is a guide on how to organize the data accordingly. Detailed instructions are provided in the following sections.

1. Download the Objaverse data [HERE](https://objaverse.allenai.org/).
2. Download the HSSD data [HERE](https://huggingface.co/datasets/hssd/hssd-models).
3. Download the 3D-FUTURE data [HERE](https://tianchi.aliyun.com/specials/promotion/alibaba-3d-future).
4. Download the PartNet-Mobility data [HERE](https://sapien.ucsd.edu/browse).

The directory structure should be as below.

```shell
InternScenes-Real2Sim/
|-- assets_library/                 # Assets library of scenes
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


# Prepare InternScenes-Synthetic Data