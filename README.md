# 3-Dimensional-Medical-Imaging-Preprocessing

## The following repository contains pre-processing codes for 3D Medical Imaging data. 

In this provided tutorial, a public abdomen dataset is extracted from: Multi-Atlas Labeling Beyong the Cranial Vault Workshop and Challenge Link: https://www.synapse.org/#!Synapse:syn3193805/wiki/217789

In this notebook, the following is covered:
- Reading NIfTI Data [1] and plotting
- Different intensity normalization approaches
- Resampling 3D CT data
- Cropping and padding CT data
- Histogram equalization
- Maximum Intensity Projection (MIP) [2] 

     ![Mouse02-spect](https://user-images.githubusercontent.com/62684338/153116321-15c60795-0edf-4adf-9d0a-d64eeab3b002.gif)
     
    * To access repositories concerning MRI Histogram Matching, Histogram Equalization and Registration, and segmentation refer to the following:
      - **LINK
      - **LINK
      - **LINK
      - LINK
      - LINK


## **Required Libraries:**  
      * SimpleITK         
      * numpy             
      * scipy             
      * skimage           
      * cv2/OpenCV-Python        
## **Reading NIfTI Data and Plotting:**
      * ct_path = **         
      * ct_label_path = **      
      # CT
      * img_sitk = sitk.ReadImage(ct_pth, sitk.sitkFloat32) #Read CT  [3]         
      * image = sitk.GetArrayfromImage(img_sitk) #Converting sitk_metadata to image array
      #Mask
      mask_sitk = sitk.ReadImage(ct_label, sitk.sitkInt32) #Read CT
      mask = sitk.GetArrayFromImage(mask_sitk) #Converting sitk_metadata to image array [4]
      
## Intensity Normalization

## Resampling

## Crop or Padding



###### Footnotes
[1] NIfTI => "Neuroimaging Informatics Technology Initiative"; jointly sponspored by the US National Institute of Mental Health and the National Institute of Neurological Disorders and Stroke. NIfTI defines a file format for neuroimaging data that is meant to meet the needs of the fMRI research community. In particular, NIfTI was developed to support interoperability of tools and software through a common file format. Prior to NIfTI there were a few major fMRI analysis software packages, and each used a different file format. NIfTI was designed to serve as a common file format for all of these (and future) neuroimaging software pipelines.

[2] MIP => Recall, in scientific visualization, a "maximum intensity projection (MIP)" is a method for 3D data that projects in the visualization plane the voxels with maximum intensity that fall in the way of parallel rays traced from the viewpoint to the plane of projection. This implies that two MIP renderings from opposite viewpoints are symmetrical images if they are rendered using orthographic projection. MIP is used for the detection of lung modules in lung cancer screening programs which use computed tomography (CT) scans. MIP enhances the 3D nature of these nodules, making them stand out from pulmonary bronchi and vasculature. To improve the sense of 3D, animations are usually rendered of several MIP frames in which the viewpoint is slightly changed from one to the other, thus reating the illusion of rotation. This helps the viewer's perception to find the relative 3D positions of the object components. However, since the projection is orthographic the viewer cannot distniguish between left or right, front or back, and if the oject is rotating clockwise/anti-clockwise. Use of depth weighting during production of rotating cines of MIP images can avoid the problem of difficulty of distinguishing right from left, and clockwise vs. anti-clockwise rotation. An improvement to MIP is local maximum intensity projection. In this technique, we do not take the global maximum value, but the first maximum value that is above a certain threshold. Because, in general, we can terminate the ray earlier, thistechnique is faster and also gives somehow better results as it approximates occlusion.

[3] In skimage, images are simply numpy arrays, which support a variety of data types, i.e. "dtypes". To avoid distorting image intensities, we assume the images use the following dtype ranges. 
| Data Types    | Range                                |
| ------------- | -------------                        |
| uint8         | 0 to 255                             |
| uint16        | 0 to 65535                           |
| uint32        | 0 to 2<sup>32</sup>                  |
| float         | -1 to 1 or 0 to 1                    |
| int8          | -128 to 127                          |
| int16         | -32768 to 32767                      |
| int32         | -2<sup>31</sup>  to 2<sup>31</sup>-1 |

[4] Masking => image processing method in which we define a small 'image piece' and use it to modify a larger image. Masking is the process that is underneath many types of image processing, including edge detection, motion detection, and noise reduction. We are also converting an image to an array since this will importantly train a machine learning model based on the features of the image. We can mainly use NumPy library in Python to work with arrays so we can also use it to convert images to an array. Other than NumPy, we can also use Keras library in Python for the same task.
