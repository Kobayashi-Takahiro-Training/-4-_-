# 課題8レポート
原画像を「村上宗隆.jpg」とする．これを白黒濃淡画像で表示し，濃度値128で二値化する．結果を図1，2に示す．

ORG = imread('村上宗隆.jpg'); 
ORG = rgb2gray(ORG); 
imagesc(ORG); colormap(gray); colorbar;
pause;
IMG = ORG > 128;
imagesc(IMG); colormap(gray); colorbar;

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_0.jpg)  
図1 原画像

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_3.jpg)  
図2 原画像

この二値化された画像をラベリングをする．ラベリングされた画像を図3に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/ラベリング.jpg)  
図3 ラベリングされた画像

ラベリングは同じ連結成分の画素に同一の番号を与える処理である．この処理をそれぞれの連結成分に対して行うことで分離し識別する．
