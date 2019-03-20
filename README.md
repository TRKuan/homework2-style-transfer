# Homework 2 (Style-Transfer) 
# Training MUNIT

# Inference one image in multiple style

# Compare with other method
## Intro
透過卷積神經網路，將圖片的內容及風格分開並重建，提供一個style transfer的做法。
## Approach
利用pre-trained VGG19 model提取圖片不同layer的特徵，作為圖像和風格的特徵。
•	Content:在network中，較低層級保留較多的原始圖像，而較高層級中雖然沒有細節的pixel但保留了high level的內容feature，因此可以利用高層的特徵來對圖像做recontruct。
•	Higher layers in the network capture the high-level content in terms of objects and their arrangement in the input image but do not constrain the exact pixel values of the reconstruction. 
•	Style:在原本的CNN架構上建立新的feature space來提取風格的特徵。作法為計算不同layer所產生的不同feature之間的correlations。在reconstruction中，該結果確實獲得的原始影像的texture、color等特徵。
### Loss Function
•	Loss Function = content loss + style loss
•	Content loss : 原圖與預測圖的content feature差距
•	Style loss : 原圖與預測圖的style feature差距

