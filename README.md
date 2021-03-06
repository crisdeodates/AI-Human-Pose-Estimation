# 3D Human Pose Estimation

This program is remodeled by moazzem (munnam77) forking [3d-pose-baseline](https://github.com/ArashHosseini/3d-pose-baseline/).

Please check the above URL or [README-ArashHosseini.md](README-ArashHosseini.md) for details of operation.

## Functional overview

- [Generates](https://github.com/CMU-Perceptual-Computing-Lab/openpose) a 3D human model from the human skeleton detected by [OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose).
- Output joint data when generating 3D human model
    	- By reading joint data with [3d-pose-baseline-multi](https://github.com/munnam77/3d-pose-baseline-multi)
- Analyze OpenPose data for multiple people.
	- Try to analysis for only one person.
	- Ver2.00 is now supports multiple people tracing. Please check [FCRN-DepthPrediction](https://github.com/munnam77/FCRN-DepthPrediction) for details.

### Result
<p align="center">
		<img src="/Results/original.gif", width="360">
		<img src="/Results/conmaps.gif", width="360">
		<img src="/Results/paf.gif", width="360">
		<img src="/Results/paf2.gif", width="360">
</p>

## 3D Reconstruction

<p align="center">
	<img src="/Results/3d_interpolation.gif", width="360">
	<img src="/Results/3d_interpolation2.gif", width="360">
	<img src="/Results/3d_interpolation3.gif", width="360">
</p>

### Dependencies

Install the following in python3 series

* [h5py](http://www.h5py.org/)
* [tensorflow](https://www.tensorflow.org/) 1.0 or later

### H36M data

3D skeleton information is created based on [Human3.6M](http://vision.imar.ro/human3.6m/description.php). 
Download the compressed file from below, decompress it, and place it under `data`.

[H36M Data zip (Dropbox)](https://www.dropbox.com/s/e35qv3n6zlkouki/h36m.zip) 

### Learning data

Since the original learning data hits the 260 character path limit of Windows, the path was simplified and regenerated.
Download the compressed file below, unzip it, and place it under `experiments`.

[Learning data zip (GoogleDrive)](https://drive.google.com/file/d/1v7ccpms3ZR8ExWWwVfcSpjMsGscDYH7_/view?usp=sharing) 

## Execution method

1. Analyze data with [Openpose Simple Launch Batch](https://github.com/munnam77/openpose-simple)
2. Generate data by depth estimation and person index with [Depth Estimation](https://github.com/munnam77/FCRN-DepthPrediction)
1. Run [OpenposeTo3D.bat] (OpenposeTo3D.bat)
1. You will be asked `Directory path by INDEX`, so specify the full path of` Path by person index` in 2.
	-`{Video file name} _json_ {Execution date and time} _index {Order from the left of the 0th floor}}
	-For multiple traces, separate execution is required
1. You will be asked if you want to `detailed log`. If you want to do so, enter` yes`
    -If not specified or `no`, normal log (each parameter file and 3D animated GIF)
    -In the case of `warn`, 3D animation GIF is not generated.
    -If `yes`, a detailed log is output, and a debug image is output in addition to the log message (slowly)
1. Start processing


## License
MIT
