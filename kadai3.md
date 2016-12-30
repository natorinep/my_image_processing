#課題3レポート
画像の2値化の際の閾値を変えることでどのような画像になるか確認する．  
閾値は輝度値によって変更する．

原画像をグレースケールに変換した画像を図1に示す．

    ORG=imread('neko.jpg'); % 原画像の入力
    ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換

    imagesc(ORG); colormap(gray); colorbar; % 画像の表示
    pause;
    
![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/3_1.jpg)  
