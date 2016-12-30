#課題3レポート
画像の2値化の際の閾値を変えることでどのような画像になるか確認する．  
閾値は輝度値によって変更する．

原画像をグレースケールに変換した画像を図1に示す．

    ORG=imread('neko.jpg'); % 原画像の入力
    ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換

    imagesc(ORG); colormap(gray); colorbar; % 画像の表示
    pause;
    
![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/3_1.jpg)  
図1 グレースケール  

閾値を64，輝度値が64以上の画素を1，その他を0として表示した画像を確認する．

    IMG = ORG > 64; % 輝度値が64以上の画素を1，その他を0に変換  
    imagesc(IMG); colormap(gray); colorbar;

表示した画像を図2に示す．

![閾値64](https://github.com/natorinep/my_image_processing/blob/master/image/3_2.jpg)  
図2 閾値64

同様に閾値を96，128,192とした画像を表示する．

    IMG = ORG > 96; % 輝度値が96以上の画素を1，その他を0に変換
    imagesc(IMG); colormap(gray); colorbar;
    pause;

    IMG = ORG > 128; % 輝度値が128以上の画素を1，その他を0に変換
    imagesc(IMG); colormap(gray); colorbar;
    pause;

    IMG = ORG > 192; % 輝度値が192以上の画素を1，その他を0に変換
    imagesc(IMG); colormap(gray); colorbar;

これらの結果を図3,4,5に示す．

![閾値96](https://github.com/natorinep/my_image_processing/blob/master/image/3_3.jpg)  
図3 閾値96

![閾値128](https://github.com/natorinep/my_image_processing/blob/master/image/3_4.jpg)  
図4 閾値128

![閾値192](https://github.com/natorinep/my_image_processing/blob/master/image/3_5.jpg)  
図5 閾値192

輝度値の最大が256でその半分の閾値は128となる．閾値が大きくなる毎に黒が占める面積は大きくなっている．
128以下の場合全体的に白が占める割合が大きく128を超えると黒が多くなっている．閾値64や閾値192は猫と分かり辛い結果になった．
原画像の各色の輝度値により左右されるため2値化の場合は閾値を正しく設定しないと第三者から見て理解できない画像になる可能性があるため注意する．
