#課題レポート2

原画像であるRGBカラーの画像をグレースケールに変換する，
変換したグレースケール画像から2階調，4階調，8階調の画像を作成する．
原画像をグレースケールに変換して表示したものを図1に示す．

![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/2_1.jpg)  
図1　グレースケール

この画像は256階調のグレースケール画像となる．2階調の画像を作成するために0から127，128から256で分ける．そのため128が閾値となる．

IMG = ORG>128;  
imagesc(IMG); colormap(gray); colorbar;  axis image;

2階調で作成した画像が図2となる．

![2階調](https://github.com/natorinep/my_image_processing/blob/master/image/2_2.jpg)  
図1　2階調
