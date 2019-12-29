# 課題6レポート
「村上宗隆.jpg」を原画像とする．

ORG=imread('村上宗隆.jpg');
ORG = rgb2gray(ORG);
imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，白黒で表示した．この結果を図１に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_0.jpg)  
図1 白黒の原画像

この白黒画像をディザ法によって二値化する．

IMG = dither(ORG); 
imagesc(IMG); colormap(gray); colorbar;

これによって得られた結果を図2に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/dither.jpg)  
図2 ディザ法

ディザ法は原画像の各画素と画素位置にあらかじめ用意したディザマトリクスの値を比較し，二値化する方法である．元の画素の値がディザマトリクス以上の値なら1(白)に，それ未満なら0(黒)にする．
