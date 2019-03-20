# Homework 2 (Style-Transfer) 
## Training MUNIT

## Inference one image in multiple style

## Compare with other method
### Neural-style
#### Approach
![](https://i.imgur.com/SGk7Hwg.png)

Using pre-trained VGG19 model to obtian the feature from different layers as the feature of the content and the style.

- Content: We find that reconstruction from lower layers is almost perfect (a,b,c). In higher layers of the network, detailed pixel information is lost while the high-level content of the image is preserved (d,e).Higher layers in the network capture the high-level content in terms of objects and their arrangement in the input image but do not constrain the exact pixel values of the reconstruction. 
- Style: We reconstruct the style of the input image from style representations built on different subsets(new feature space) of CNN layers.The style representation computes correlations between the different features in different layers of the CNN.After the reconsctruction,the result do obtain the feature of the origin image.

##### Compare
- compare MUNIT with nueral style,from the pictures below we can see that the MUNIT preserve the details of content better than the neural-style ones,the reason of that is the higher level of CNN may lost too much pixels only preserves the objects and the arrangement of them,so after the reconstruction the output images would lost a lot of the details
