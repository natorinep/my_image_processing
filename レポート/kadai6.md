#課題6レポート
画像をグレースケール化し，閾値128で2値化を行った場合とディザ法による2値化の場合と比較する．

    ORG=imread('neko.jpg'); % 原画像の入力
    ORG = rgb2gray(ORG);
    imagesc(ORG); colormap(gray); colorbar; % 画像の表示

原画像をグレースケールにした画像を図1に示す．

![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/6_1.jpg)  
図1 グレースケール1  

閾値128で2値化する場合次のようなプログラムになる．

    IMG = ORG>128; % 128による二値化
    imagesc(IMG); colormap(gray); colorbar; % 画像の表示
    
結果を図2に示す．

![閾値128での2値化](https://github.com/natorinep/my_image_processing/blob/master/image/6_2.jpg)  
図2 閾値128での2値化  

次にディザ法による2値化を行う．次のプログラムによって2値化を行う．

    IMG = dither(ORG); % ディザ法による二値化
    imagesc(IMG); colormap(gray); colorbar; % 画像の表示

結果を図3に示す．

![ディザ法による2値化](https://github.com/natorinep/my_image_processing/blob/master/image/6_3.jpg)  
図3 ディザ法での2値化   

図2,図3より閾値128での2値化と比べディザ法での2値化は濃淡が分かりやすくなっている．
ディザ法での2値化は漫画のトーンのようにドットの密度によって濃淡を表しているため，比較的原画像のグレースケールに近い画像となっていることが分かる．
