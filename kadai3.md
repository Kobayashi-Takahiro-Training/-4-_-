#課題3レポート

「村上宗隆.jpg」を原画像とする．この画像をある輝度値以上の画素を1，そうでない画素を0に変換して表示する．

ORG=imread('村上宗隆.jpg'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

により，画像を読み込み，白黒濃淡画像に変換して表示する．表示された画像を図1に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_0.jpg)  
図1 白黒の原画像

この画像に対して，輝度値がある値以上の画素に対して1(白色)を，それ以外の画素に0(黒色)を割り当てる．このときの輝度値を閾値という．閾値は

IMG = ORG > 32;

で設定し，

imagesc(IMG); colormap(gray); colorbar;

で処理後の画像を表示する．この場合の閾値は32に設定されている．図2に表示結果を示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_1.jpg)  
図2 閾値32以上

このようにして，閾値をそれぞれ64，128，256にしてその変化を確認する．

IMG = ORG > 64;
IMG = ORG > 128;
IMG = ORG > 256;

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_2.jpg)  
図3 閾値64以上

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_3.jpg)  
図4 閾値128以上


![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_4.jpg)  
図5 閾値256以上

閾値を大きくするほど画像は黒くなっていった．つまり，この画像中にある画素の輝度値はあまり大きな値でないことが分かる．