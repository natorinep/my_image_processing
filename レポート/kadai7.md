#課題7レポート
画像の画素のダイナミックレンジを0から255にする．
原画像のグレースケール化を図1に示す．

    ORG = imread('neko2.jpg'); % 画像の読み込み
    ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
    imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/7_1.jpg)  
図1 グレースケール1 

この画像のヒストグラムを表示する．

    imhist(ORG); % 濃度ヒストグラムを生成、表示

ヒストグラム結果を図2に示す．

![ヒストグラム](https://github.com/natorinep/my_image_processing/blob/master/image/7_2.jpg)  
図2 ヒストグラム1 

この画像の画素のダイナミックレンジはいま0から233となっている．なのでこれを0から255に変換する．

    ORG = double(ORG);
    mn = min(ORG(:)); % 濃度値の最小値を算出

    mx = max(ORG(:)); % 濃度値の最大値を算出
    ORG = (ORG-mn)/(mx-mn)*255;
    imagesc(ORG); colormap(gray); colorbar; % 画像の表示
    pause;
    ORG = uint8(ORG); % この行について考察せよ
    imhist(ORG); % 濃度ヒストグラムを生成、表示
    
変換後の画像の表示及びヒストグラムが図3,4となる．

![グレースケール2](https://github.com/natorinep/my_image_processing/blob/master/image/7_3.jpg)  
図3 グレースケール2 

![ヒストグラム2](https://github.com/natorinep/my_image_processing/blob/master/image/7_4.jpg)  
図2 ヒストグラム2 

この変換でダイナミックレンジが0から255となっていることが分かる．
一度doubleで画像を浮動小数点とし計算しているため，unit8を用いて8ビットの符号なし整数に変換してヒストグラムを表示させている．
