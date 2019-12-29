# 課題7レポート
原画像を「村上宗隆.png」とする．この画像は縦1976画素，横1500画素での白黒濃淡画像である．原画像を読み込み，そのヒストグラムを表示させる．

ORG = imread('村上宗隆.png');
imagesc(ORG); colormap(gray); colorbar; axis image;
pause;
imhist(ORG);
pause;

図1に原画像を，図2にヒストグラムを示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/murakami_129.jpg)  
図1 原画像

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/ヒストグラム7-1.jpg)  
図2 ヒストグラム

この原画像の濃度値は0～129となっている．この原画像の各画素における濃度値を浮動小数点で求め，その最大値および最小値を算出する．

ORG = double(ORG);
mn = min(ORG(:)); 
mx = max(ORG(:)); 

各画素の値を(元の画素値-最小濃度値) * 255/(最大濃度値-最小濃度値)に置き換える．

ORG = (ORG-mn)/(mx-mn)*255;

これで得られた結果を図3に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/murakami_255.jpg)  
図3 変換後の画像

このとき算出された画素値をuint8で0～2の8乗-1までの整数値にする．

ORG = uint8(ORG)

この処理を行った後のヒストグラムを図4に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/ヒストグラム7-2.jpg)  
図4 変換後のヒストグラム

図4からも分かるように濃度値の範囲を拡張したことで全体の画素値も拡張された．