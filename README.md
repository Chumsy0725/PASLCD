# Pose-Agnostic Scene-Level Change Detection (PASLCD)
The dataset and the code will be released here.

## PASLCD Dataset
We introduce a new real-world dataset containing image sequences collected from ten challenging scenes captured using an iPhone following random and independent trajectories. Among the five indoor and five outdoor scenes, three from each are forward-facing and the remaining two are 360&deg;. See below for details and visualizations:

| Scene | Indoor/Outdoor | FF/360&deg; | Changes (click to expand) |
| :----| :----: | :----: | :---: |
| Cantina | Indoor | FF | [![Thumbnail1](thumbnail1.png)](image1.png) |
| Lounge | Indoor | FF | [![Thumbnail1](thumbnail1.png)](image1.png) |
| Printing Area | Indoor | FF | [![Thumbnail1](thumbnail1.png)](image1.png) |
| Lunch Room | Indoor | 360&deg; | [![Thumbnail1](thumbnail1.png)](image1.png) |
| Meeting Room | Indoor | 360&deg; | [![Thumbnail1](thumbnail1.png)](image1.png) |
| Garden | Outdoor | FF | [![Thumbnail1](thumbnail1.png)](image1.png) |
| Pots | Outdoor | FF | [![Thumbnail1](thumbnail1.png)](image1.png) |
| Zen | Outdoor | FF | [![Thumbnail1](thumbnail1.png)](image1.png) |
| Playground | Outdoor | 360&deg; | [![Thumbnail1](thumbnail1.png)](image1.png) |
| Porch | Outdoor | 360&deg; | [![Thumbnail1](thumbnail1.png)](image1.png) |

Each scene contains images from two *reference* (pre-change) instances &mdash; referred to as *Instance 1* and *Instance 2* in the paper and dataset &mdash; one *inference* (post-change) image set and labelled ground truth masks from the camera poses of the inference set. Each reference instance contains 50&ndash;109 images stored in ```<Scene>/<Instance_#>/input_orig```. Each inference set contains 25 images stored in ```<Scene/<Instance_#>/input_orig_test``` and their respective masks in ```<Scene>/<Instance_#>/gt_mask```. Between either reference instance and the inference set, there are 5&ndash;16 relevant structural and surface-level changes. These changes are listed in ```changes.txt``` under each ```<Scene>/<Instance_#>``` combination. Comparing *Instance 1* with the inference set tests change detection under consistent lighting conditions, while comparing *Instance 2* with the inference set tests change detection under different lighting conditions. See below for the directory structure:

<pre>
├── /
│   ├── Cantina
│   │   ├── Instance_1
│   │   │   ├── changes.txt
│   │   │   ├── gt_mask
│   │   │   │   ├── Inst_1_test_IMG_nnnn.png
│   │   │   │   ├── ... 
│   │   │   ├── input_orig
│   │   │   │   ├── Inst_1_IMG_####.png
│   │   │   │   ├── ... 
│   │   │   ├── input_orig_test
│   │   │   │   ├── Inst_1_test_IMG_####.png
│   │   │   │   ├── ... 
│   │   ├── Instance_2
│   │   │   ├── changes.txt
│   │   │   ├── gt_mask
│   │   │   │   ├── Inst_2_test_IMG_nnnn.png
│   │   │   │   ├── ... 
│   │   │   ├── input_orig
│   │   │   │   ├── Inst_2_IMG_####.png
│   │   │   │   ├── ... 
│   │   │   ├── input_orig_test
│   │   │   │   ├── Inst_2_test_IMG_####.png
│   │   │   │   ├── ... 
│   ├── Lounge
│   ├── ...
</pre>
