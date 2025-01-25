
## Our entire code is built based on nnSAM, and you can follow the nnSAM instructions exactly.


Install SAM-Unet depending on your use case:

```bash
conda create -n SAMUnet python=3.9
conda activate SAMUnet
pip install git+https://github.com/facebookresearch/segment-anything.git
pip install timm
pip install git+https://github.com/FYLinIC/Fluorescence-information-decryption.git
```

It is important to input "set MODEL_NAME=SAMUnet" before using it.
```bash
set MODEL_NAME=SAMUnet
```

```bash
nnUNetv2_plan_and_preprocess -d DATASET_ID --verify_dataset_integrity

nnUNetv2_train DATASET_NAME_OR_ID UNET_CONFIGURATION FOLD [additional options, see -h]

nnUNetv2_train DATASET_NAME_OR_ID UNET_CONFIGURATION FOLD --val --npz

nnUNetv2_train DATASET_NAME_OR_ID 2d FOLD

nnUNetv2_train DATASET_NAME_OR_ID 3d_fullres FOLD

nnUNetv2_predict -i INPUT_FOLDER -o OUTPUT_FOLDER -d DATASET_NAME_OR_ID -c CONFIGURATION --save_probabilities
```
