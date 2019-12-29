# 課題9レポート
原画像を「村上宗隆.jpg」とする．原画像を図1に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_0.jpg)  
図1 原画像

この原画像に
ORG = imnoise(ORG,'salt & pepper',0.02); 
で白点状のノイズを添付する．この結果を図2に表示する．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/ノイズ.jpg)  
図2 ノイズ入り原画像

この画像に含まれたノイズを平滑化フィルタおよびメディアンフィルタによって除去する．それぞれのフィルタは

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去
IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去

によって，設定される．これによってノイズ除去された画像を図3と4に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/平滑化.jpg)  
図3 平滑化フィルタによるノイズ除去

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/メディアンフィルタ.jpg)  
図4 メディアフィルタによるノイズ除去

図3の平滑化フィルタは着目画素の周囲8画素の平均値を中央の画素の値にして平滑化を行っている．この処理では少しぼやけた画像になってしまう．
図4はメディアンフィルタ法でノイズ処理を行っている．着目画素の周囲にある画素の中央値を新たに着目画素の値としている．平滑化に比べると処理後の画像は滑らかになっている．

最後のフィルタは図5のようになっており，各画素の積和で新たに着目画素値(中央の画素値)を求めることでノイズ除去を行う．このフィルタの設計及び適用は

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用

によって行われる．これによって得られた結果を図6に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/平滑化フィルタ.PNG)  
図5 平滑化フィルタ

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/先鋭化.jpg)  
図6 先鋭化フィルタ

この画像は全体的に灰色になっている．これは図5からも分かるように中央画素の4近傍がマイナスになっており，あまり大きな画素値にならないためである．


