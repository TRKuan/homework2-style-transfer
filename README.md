# Homework 2 (Style-Transfer) 
## Training MUNIT
Trained on the summer2winter_yosemite256 dataset. Training time is about 48hrs(200k iterations). Following are the loss training curves:

![](loss_gen_total.png)
![](loss_dis_total.png)
## Inference one image in multiple style
Here we test the training results using our own photos.

summer to winter:  
![](summer2winter.png)  
winter to summer:  
![](winter2summer.png)  
We can see that although it can catch the color of the style image, it can not distinguish different object very well. Especially the winter to summer ones. Instead of getting rid of the snow, buildings are truned into green. Summer to winter ones are a bit better, but still not much snow is generated. This may due to the fact that we did not train the models long enough and it may still be under fitting. More training resources and time may lead to better results.
## Compare with other method
In this section, we compare MUNIT with Neural-style on the applications of summer to winter and winter to summer.

### Neural-style
#### Approach
![](https://i.imgur.com/SGk7Hwg.png)

- Content: In the lower layer of the network perserve alomost everything of the pictures,however in higher layers it discard most of the details but only reserve the higher information of the picture like the color and the arrangement
- Style: Compute the correlation between different features in a new feature space

#### Results
summer to winter:  
![](summer2winter_ns.png)  
winter to summer:  
![](winter2summer_ns.png)  

### Compare MUNIT with nueral style
-  From the images above, we can see that the MUNIT ones preserves the details of content better than the neural-style ones. The reason is that while higher level of CNN layers can capture the content of the image, it may lost per pixel detail of the original image. So after the reconstruction, the output images only captures the heigh level idea of the content and lost a lot of details.
-  Although we are comparing the applications of summer to winter or vice versa, it is worth noticing that the origial goal of nueral style is to generate artistic looking works instead of depicting photorealistic images. Images generated via nueral style do look pretty artstic and season changing is more like a side effact apart from the main goal.
-  On the other hand, The underfitting MUNIT here are not doing well. Dispite the fact that the per pixel context detail preserved very well due to the reconstruction loss, the style is not been captured well. The photorealistic nature of the image makes it looks worse. 
-  MUNIT needs lots of training resources to have a good perforomence. As we can see the images are still not better then CycleGAN after training for 48 hours. However, it still has it's potential since the sample images in the paper look pertty decent.

### Conclution
In conclution, MUNIT preserves the content better with more pixel level details. On the other hand nueral style is better at capturing heigher level content and produces a more artistic image.
