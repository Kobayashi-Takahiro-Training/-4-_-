# 課題１レポート

「murakami.jpg」を原画像とする．この画像は縦1976画像，横1500画素のディジタルカラー画像である．

ORG=imread('murakami.png'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込む.原画像を図１に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/murakami.jpg)  
図1 原画像

原画像を1/2縮小した後，2倍に拡大すると1/2サンプリングの画像ができる．なお，拡大する際には，単純補間するために「box」オプションを設定する．


IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

1/2サンプリングの結果を図２に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/murakami2.jpg)  
図2 1/2サンプリング

1/2サンプリング画像を1/2倍に縮小した後，2倍に拡大すれば1/4サンプリング画像になる．すなわち，

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,4,'box'); % 画像の拡大

とする．1/4サンプリングの結果を図３に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/murakami4.jpg)  
図3 1/4サンプリング

1/8から1/32サンプリングは，

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,8,'box'); % 画像の拡大

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,16,'box'); % 画像の拡大

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,32,'box'); % 画像の拡大

となる．サンプリングの結果を図４～６に示す．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/murakami8.jpg)  
図4 1/8サンプリング

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/murakami16.jpg)  
図5 1/16サンプリング

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/murakami32.jpg)  
図6 1/32サンプリング

サンプリング幅を大きくするごとに，モザイクかかった画像に変化する．
