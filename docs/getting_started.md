## Installation
Follow https://github.com/fundamentalvision/BEVFormer/blob/master/docs/install.md to prepare the environment.

## Preparing Dataset
1. Download the gts and annotations.json we provided. You can download our imgs.tar.gz or using the original sample files of the nuScenes dataset.

2. Download the CAN bus expansion data and maps [HERE](https://www.nuscenes.org/download).

3. Organize your folder structure as below：
```
Occupancy3D
├── projects/
├── tools/
├── ckpts/
│   ├── r101_dcn_fcos3d_pretrain.pth
├── data/
│   ├── can_bus/
│   ├── occ3d-nus/
│   │   ├── maps/
│   │   ├── samples/     # You can download our imgs.tar.gz or using the original sample files of the nuScenes dataset
│   │   ├── v1.0-trainval/
│   │   ├── gts/
│   │   └── annotations.json
│   │ 
│   ├── occ3d-test/
│   │   ├── maps/
│   │   ├── samples/     # You can download our imgs.tar.gz or using the original sample files of the nuScenes dataset
│   │   ├── v1.0-test/
│   │   └── annotations.json
```


4. Generate the info files for training and validation:
```
python tools/create_data.py occ --root-path ./data/occ3d-nus --out-dir ./data/occ3d-nus --extra-tag occ --version v1.0-trainval --canbus ./data --occ-path ./data/occ3d-nus
``` 

5. Generate the info files for test split:
```
python tools/create_data.py occ --root-path ./data/occ3d-test --out-dir ./data/occ3d-test --extra-tag occ --version v1.0-test --canbus ./data --occ-path ./data/occ3d-test
``` 

## Training
```
./tools/dist_train.sh projects/configs/bevformer/bevformer_base_occ.py 8
```

## Testing
```
./tools/dist_test.sh projects/configs/bevformer/bevformer_base_occ.py work_dirs/bevformer_base_occ/epoch_24.pth 8
```
You can evaluate the F-score at the same time by adding `--eval_fscore`.

## Test Submission
Test the baseline model on the test split with 8 GPUs, and generate the npz files and submission data to be submit to the official evaluation server.
```
./tools/dist_test.sh projects/configs/bevformer/bevformer_base_occ_test.py work_dirs/bevformer_base_occ/epoch_24.pth 8 --format-only --eval-options 'submission_prefix=./occ_submission'
```

### Performance

model name|weight| split |mIoU | others | barrier | bicycle | bus | car | construction_vehicle | motorcycle | pedestrian | traffic_cone | trailer |  truck | driveable_surface | other_flat | sidewalk | terrain | manmade | vegetation | 
----|:----------:| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :----------------------: | :---: | :------: | :------: |
bevformer_base_occ|[Google Drive](https://drive.google.com/file/d/1NyoiosafAmne1qiABeNOPXR-P-y0i7_I/view?usp=share_link)| val | 23.67 | 5.03 | 38.79 | 9.98 | 34.41 | 41.09 | 13.24 | 16.50 | 18.15 | 17.83 | 18.66 | 27.7 | 48.95 | 27.73 | 29.08 | 25.38 | 15.41 | 14.46 | 
bevformer_base_occ|[Google Drive](https://drive.google.com/file/d/1NyoiosafAmne1qiABeNOPXR-P-y0i7_I/view?usp=share_link)| test | 23.7 | 10.24 | 36.77 | 11.7 | 29.87 | 38.92 | 10.29 | 22.05 | 16.21 | 14.69 | 27.44 | 23.13 | 48.19 | 33.1 | 29.8 | 17.64 | 19.01 | 13.75 | 

