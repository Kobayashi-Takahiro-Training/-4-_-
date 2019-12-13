#課題4レポート

「村上宗隆.jpg」を原画像とする．この画像を，

ORG=imread('村上宗隆.jpg'); 
ORG=rgb2gray(ORG); 
imagesc(ORG); colormap(gray); colorbar;

で白黒で表示する．表示結果を図1に示す．


![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_0.jpg)  
図1 白黒の原画像

次に

imhist(ORG); 

で画像中の濃度値のヒストグラムを表示させる．図2にヒストグラムの結果を表示する．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/ヒストグラム.jpg)  
図2　ヒストグラム

