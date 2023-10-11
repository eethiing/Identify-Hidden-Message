# Identify-Hidden-Message

## Description 
--------------------------------------------------
In this challenge, two images were given, a reference image and a template image. Both images looks the same through naked eyes but there is actually a hidden message behind the images. Computer vision techniques is applied to idenitfy the message.

Reference Image : 

![reference](https://github.com/eethiing/Identify-Hidden-Message/assets/85276977/b313047b-9e45-44b6-9533-1be252cbc257)

Template Image :

![template](https://github.com/eethiing/Identify-Hidden-Message/assets/85276977/2897ccbf-6b46-4e5c-8bdc-ec486785ea17)

## Techniques Applied 
-------------------------------------------------
The challenge begins with reading the reference and template images and converting them to grayscale. The reason for converting the images to grayscale is that it makes it easier to process the images in later stages. The cv2.subtract function was applied to find the differences between both images, but no differences were initially found, resulting in an entirely black output.

Next, bitwise XOR is used, as it checks whether both pixels are greater than 0 for it to be considered true. Another technique tested was absdiff(). The absdiff function computes the absolute difference between two images. Both methods produced similar results, so we decided to use the output of absdiff because the characters appeared to be more connected.

To fill in the gaps, morphological processing was applied, involving closing and dilation. The MORPH_ELLIPSE kernel with a size of 3x3 for closing and a square kernel with a size of 3x3 for dilation. Both processes were applied to the output of absdiff. To enhance the contrast of the output, histogram equalization was performed on the results of both the closing and dilation operations. After histogram equalization, adaptive thresholding was applied to both outputs to segment the characters for a clearer output.

The hidden message extracted from the processed images is 'SWEAT'. This was my final output and it might differs from others. 
![image](https://github.com/eethiing/Identify-Hidden-Message/assets/85276977/2e9eec26-a2f1-430a-ab91-167d6207fa9e)








