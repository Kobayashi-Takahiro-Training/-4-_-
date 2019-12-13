# 課題5レポート

「村上宗隆.jpg」を原画像とする．

ORG=imread('村上宗隆.jpg');
ORG = rgb2gray(ORG);
imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，白黒で表示した．この結果を図１に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_0.jpg)  
図1 白黒の原画像

この画像のヒストグラムを2分割し，そこから画素数，平均値，分散を算出し，

C1 = H(1:i); 
C2 = H(i+1:256);
n1 = sum(C1); 
n2 = sum(C2);
myu1 = mean(C1); 
myu2 = mean(C2);
sigma1 = var(C1); 
sigma2 = var(C2);

それらを基にクラス内分散とクラス間分散を算出する．

sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); 
sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); 

この2つの商を判別することで画像を二値化する．

if max_val<sigma_B/sigma_w
max_val = sigma_B/sigma_w;
max_thres =i;

IMG = ORG > max_thres;
imagesc(IMG); colormap(gray); colorbar;

このようにして二値化した画像を図2に表示する．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai5.jpg)  
図2 二値化画像

白黒濃淡画像は完全に二値化された画像に変換された．