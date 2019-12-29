# 課題レポート10

原画像を村上宗隆.jpgを白黒濃淡にした画像とする．これを図1とする．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/kadai3_0.jpg)  
図1 原画像

この画像をプレウィット法，ソベル法，キャニー法でエッジ抽出を行う．

IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）

この処理によって得られた画像を図2～4とする．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/プレウィット.jpg)  
図2 プレウィット法によるエッジ抽出

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/ソベル.jpg)  
図3 ソベル法によるエッジ抽出

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/キャニー.jpg)  
図4 キャニー法によるエッジ抽出

プレウィット法およびソベル法は図5，6のようになっている．

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/プレウィット.PNG)  
図5 プレウィット法

![原画像](https://github.com/Kobayashi-Takahiro-Training/FILE/blob/master/ソベル.PNG)  
図6 ソベル法

横方向をX軸，縦方向をY軸と定義され，ソベル法は中心画素が強調されるようになっているためプレウィット法よりもはっきりとした輪郭が抽出される．
一方，キャニー法は2つの閾値を用いてエッジ抽出を行う．一つは値が大きく，もう一つは値が小さい．大きいほうの閾値よりも大きな値の画素はエッジとなり，小さいほうの閾値より小さいとその画素はエッジとして見なさない．2つの閾値の間にある画素値は近傍がエッジの場合のみエッジになる．
