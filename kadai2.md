# 課題２レポート

「村上宗隆.jpg」を原画像とする．この画像は縦1976画像，横1500画素のディジタルカラー画像である．

ORG=imread('村上宗隆.jpg');
ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image;

で画像を読み込み，読み込んだ画像を白黒で表示する．結果を図1に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/murakami_mono.jpg)  
図1 白黒の原画像

この画像を2階調表現する場合，黒(256)の半分の値(128)で場合分けする必要がある．

IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;

2階調画像を図2に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/2_murakami.jpg)  
図2 2階調画像

このように元の白黒画像を2^N個分の値の区域ができるようにすると2^N階調画像が生成できる．4階調，8階調画像の生成は以下のようになる．

4階調
IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;
imagesc(IMG); colormap(gray); colorbar;  axis image;

8階調
IMG0 = ORG>32;
IMG1 = ORG>64;
IMG2 = ORG>96;
IMG3 = ORG>128;
IMG4 = ORG>160;
IMG5 = ORG>192;
IMG6 = ORG>224;
IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 +IMG5 + IMG6;
imagesc(IMG); colormap(gray); colorbar;  axis image;

図3，4に4階調画像，8階調画像を示す．


![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/4_murakami.jpg)  
図3 4階調画像


![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/8_murakami.jpg)  
図4 8階調画像

階調の数を増やすごとに画像はより鮮明に表示されることが分かる．