#課題レポート2

原画像であるRGBカラーの画像をグレースケールに変換する，
変換したグレースケール画像から2階調，4階調，8階調の画像を作成する．
原画像をグレースケールに変換して表示したものを図1に示す．

![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/2_1.jpg)  
図1　グレースケール

この画像は256階調のグレースケール画像となる．2階調の画像を作成するために0から127，128から256で分ける．そのため128が閾値となる．

IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  axis image;

2階調で作成した画像を図2に示す．

![2階調](https://github.com/natorinep/my_image_processing/blob/master/image/2_2.jpg)  
図2　2階調

同様に4階調は256を1/4毎に閾値とするため，プログラムは次のようになる．

IMG0 = ORG>64;  
IMG1 = ORG>128;  
IMG2 = ORG>192;  
IMG = IMG0 + IMG1 + IMG2;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

4階調の結果を図3に示す．

![4階調](https://github.com/natorinep/my_image_processing/blob/master/image/2_3.jpg)  
図3　4階調

同様に8階調のプログラムが次のようになる．

IMG0 = ORG>32;  
IMG1 = ORG>64;  
IMG2 = ORG>96;  
IMG3 = ORG>128;  
IMG4 = ORG>160;  
IMG5 = ORG>192;  
IMG6 = ORG>224;  
IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;  
imagesc(IMG); colormap(gray); colorbar;  axis image;  

8階調の結果を図4に示す．

![8階調](https://github.com/natorinep/my_image_processing/blob/master/image/2_4.jpg)  
図4　8階調

2階調だと猫ということは読み取れるが，細かい部分は分からない．階調を上げる毎に猫の毛並みや表情が読み取れるようになってくる．
