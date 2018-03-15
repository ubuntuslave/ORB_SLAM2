# Running examples

## Monocular Examples

### TUM Dataset

1. Download a sequence from http://vision.in.tum.de/data/datasets/rgbd-dataset/download and uncompress it.

2. Execute the following command. Change `TUMX.yaml` to `TUM1.yaml`,`TUM2.yaml` or `TUM3.yaml` for freiburg1, freiburg2 and freiburg3 sequences respectively. Change `PATH_TO_SEQUENCE_FOLDER`to the uncompressed sequence folder.

```
./Examples/Monocular/mono_tum Vocabulary/ORBvoc.bin Examples/Monocular/TUMX.yaml PATH_TO_SEQUENCE_FOLDER
```

In my case, I use a *binary* file for the Vocabulary (loads faster). Thus, for the *rgbd_dataset_freiburg1_360* sequence, (for which ORB-SLAM does very bad), you run:

    ./Examples/Monocular/mono_tum Vocabulary/ORBvoc.bin Examples/Monocular/TUM1.yaml /Volumes/Nifty/Downloads2/data/TUM/RGBD/rgbd_dataset_freiburg1_360

The *rgbd_dataset_freiburg1_desk* sequence works better:

    ./Examples/Monocular/mono_tum Vocabulary/ORBvoc.bin Examples/Monocular/TUM1.yaml /Volumes/Nifty/Downloads2/data/TUM/RGBD/rgbd_dataset_freiburg1_desk

## RGB-D Example

### TUM Dataset

1. Download a sequence from http://vision.in.tum.de/data/datasets/rgbd-dataset/download and uncompress it.

2. Associate RGB images and depth images using the python script [associate.py](http://vision.in.tum.de/data/datasets/rgbd-dataset/tools). We already provide associations for some of the sequences in *Examples/RGB-D/associations/*. You can generate your own associations file executing:

```
python associate.py PATH_TO_SEQUENCE/rgb.txt PATH_TO_SEQUENCE/depth.txt > associations.txt
```

3. Execute the following command. Change `TUMX.yaml` to `TUM1.yaml`,`TUM2.yaml` or `TUM3.yaml` for freiburg1, freiburg2 and freiburg3 sequences respectively. Change `PATH_TO_SEQUENCE_FOLDER`to the uncompressed sequence folder. Change `ASSOCIATIONS_FILE` to the path to the corresponding associations file.

```
./Examples/RGB-D/rgbd_tum Vocabulary/ORBvoc.bin Examples/RGB-D/TUMX.yaml PATH_TO_SEQUENCE_FOLDER ASSOCIATIONS_FILE
```

In my case, I use a *binary* file for the Vocabulary (loads faster). Thus, for the *rgbd_dataset_freiburg1_desk* sequence:

    ./Examples/RGB-D/rgbd_tum Vocabulary/ORBvoc.bin Examples/RGB-D/TUM1.yaml /Volumes/Nifty/Downloads2/data/TUM/RGBD/rgbd_dataset_freiburg1_desk Examples/RGB-D/associations/fr1_desk.txt

## Stereo Examples

### KITTI Dataset

1. Download the dataset (grayscale images) from http://www.cvlibs.net/datasets/kitti/eval_odometry.php 

2. Execute the following command. Change `KITTIX.yaml` to `KITTI00-02.yaml`, `KITTI03.yaml` or `KITTI04-12.yaml` for sequence 0 to 2, 3, and 4 to 12 respectively. Change `PATH_TO_DATASET_FOLDER` to the uncompressed dataset folder. Change `SEQUENCE_NUMBER` to 00, 01, 02,.., 11. 

```
./Examples/Stereo/stereo_kitti Vocabulary/ORBvoc.txt Examples/Stereo/KITTIX.yaml PATH_TO_DATASET_FOLDER/dataset/sequences/SEQUENCE_NUMBER
```

In my case, I use a *binary* file for the Vocabulary (loads faster). Thus, I ran:


    ./Examples/Stereo/stereo_kitti Vocabulary/ORBvoc.bin Examples/Stereo/KITTI00-02.yaml /Volumes/Nifty/Downloads2/data/KITTI/data_odometry_gray/dataset/sequences/00
