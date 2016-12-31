#課題8レポート

画像をグレースケール化し，それぞれの連結成分にラベルをつける．

    ORG = imread('neko.jpg'); % 画像の読み込み
    ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
    imagesc(ORG); colormap(gray); colorbar; % 画像の表示

原画像をグレースケールにした画像を図1に示す．

![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/8_1.jpg)  
図1 グレースケール  

この画像を閾値128で2値化したものを図2に示す．

    IMG = ORG > 128; % 閾値128で二値化
    imagesc(IMG); colormap(gray); colorbar; % 画像の表示

![2値化](https://github.com/natorinep/my_image_processing/blob/master/image/8_2.jpg)  
図2 2値化

この2値化画像から連結成分にラベルをつける．結果が図3となった．

    IMG = bwlabeln(IMG);
    imagesc(IMG); colormap(jet); colorbar; % 画像の表示
    
![ラベル](https://github.com/natorinep/my_image_processing/blob/master/image/8_3.jpg)  
図3 ラベル付け

図3より2値化の黒い部分は青，白い部分を画像の左から連結成分毎に暖色の色をつけていっている．
