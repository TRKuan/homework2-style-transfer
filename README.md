# Homework 2 (Style-Transfer) 
## Training MUNIT

## Inference one image in multiple style

## Compare with other method
## Neural-style
### Intro
With CNN,it recontruct the content image and the style image seperately
### Approach
![](https://i.imgur.com/SGk7Hwg.png)

Using pre-trained VGG19 model to obtian the feature from different layers as the feature of the content and the style.

- Content: We find that reconstruction from lower layers is almost perfect (a,b,c). In higher layers of the network, detailed pixel information is lost while the high-level content of the image is preserved (d,e).Higher layers in the network capture the high-level content in terms of objects and their arrangement in the input image but do not constrain the exact pixel values of the reconstruction. 
- Style: We reconstruct the style of the input image from style representations built on different subsets(new feature space) of CNN layers.The style representation computes correlations between the different features in different layers of the CNN.after the reconsctruction,the result do obtain the feature of the origin image.
#### Loss Function
-	Ltotal(p⃗,⃗a,⃗x) = αLcontent(p⃗,⃗x) + βLstyle(⃗a,⃗x)
-	Content loss : the squared-error loss between the origin and the prediction
-	Style loss : mean-squared distance between the entries of the Gram matrix from the original image and the Gram matrix of the image to be generated.


