# 3-Dimensional-Medical-Imaging-Preprocessing

The following repository contains pre-processing codes for 3D Medical Imaging data. 

In this provided tutorial, a public abdomen dataset is extracted from: Multi-Atlas Labeling Beyong the Cranial Vault Workshop and Challenge Link: https://www.synapse.org/#!Synapse:syn3193805/wiki/217789

In this notebook, the following is covered:
1. Reading NIfTI Data [^1] and plotting
2. Different intensity normalization approaches
3. Resampling 3D CT data
4. Cropping and padding CT data
5. Histogram equalization
6. Maximum Intensity Projection (MIP) [^2] 

      ![Mouse02-spect](https://user-images.githubusercontent.com/62684338/153116321-15c60795-0edf-4adf-9d0a-d64eeab3b002.gif)



 
[^1] NIfTI => "Neuroimaging Informatics Technology Initiative"; jointly sponspored by the US National Institute of Mental Health and the National Institute of Neurological Disorders and Stroke. NIfTI defines a file format for neuroimaging data that is meant to meet the needs of the fMRI research community. In particular, NIfTI was developed to support interoperability of tools and software through a common file format. Prior to NIfTI there were a few major fMRI analysis software packages, and each used a different file format. NIfTI was designed to serve as a common file format for all of these (and future) neuroimaging software pipelines.

[^2] MIP => Recall, in scientific visualization, a "maximum intensity projection (MIP)" is a method for 3D data that projects in the visualization plane the voxels with maximum intensity that fall in the way of parallel rays traced from the viewpoint to the plane of projection. This implies that two MIP renderings from opposite viewpoints are symmetrical images if they are rendered using orthographic projection. MIP is used for the detection of lung modules in lung cancer screening programs which use computed tomography (CT) scans. MIP enhances the 3D nature of these nodules, making them stand out from pulmonary bronchi and vasculature. To improve the sense of 3D, animations are usually rendered of several MIP frames in which the viewpoint is slightly changed from one to the other, thus reating the illusion of rotation. This helps the viewer's perception to find the relative 3D positions of the object components. However, since the projection is orthographic the viewer cannot distniguish between left or right, front or back, and if the oject is rotating clockwise/anti-clockwise. Use of depth weighting during production of rotating cines of MIP images can avoid the problem of difficulty of distinguishing right from left, and clockwise vs. anti-clockwise rotation. An improvement to MIP is local maximum intensity projection. In this technique, we do not take the global maximum value, but the first maximum value that is above a certain threshold. Because, in general, we can terminate the ray earlier, thistechnique is faster and also gives somehow better results as it approximates occlusion.

