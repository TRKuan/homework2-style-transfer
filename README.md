# Homework 2 (Style-Transfer) 
## Training MUNIT

## Inference one image in multiple style

## Compare with other method
## Neural-style
### Intro
With CNN,it recontruct the content image and the style image seperately
### Approach
![](https://imgur.com/SGk7Hwg)
利用pre-trained VGG19 model提取圖片不同layer的特徵，作為圖像和風格的特徵。

•	Content:在network中，較低層級保留較多的原始圖像，而較高層級中雖然沒有細節的pixel但保留了high level的內容feature，因此可以利用高層的特徵來對圖像做recontruct。
•	Higher layers in the network capture the high-level content in terms of objects and their arrangement in the input image but do not constrain the exact pixel values of the reconstruction. 
•	Style:在原本的CNN架構上建立新的feature space來提取風格的特徵。作法為計算不同layer所產生的不同feature之間的correlations。在reconstruction中，該結果確實獲得的原始影像的texture、color等特徵。
#### Loss Function
-	Ltotal(p⃗,⃗a,⃗x) = αLcontent(p⃗,⃗x) + βLstyle(⃗a,⃗x)
-	Content loss : 原圖與預測圖的content feature差距
-	Style loss : 原圖與預測圖的style feature差距


