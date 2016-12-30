# 課題１レポート

画像に対して1/2サンプリングを行っていき原画像からどうのような変化が起こるかを確認する．

    ORG=imread('neko.jpg'); % 原画像の入力  
    imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図１に示す．

![原画像](https://github.com/natorinep/my_image_processing/blob/master/image/1_1.jpg)

図1 原画像

この画像は縦1600画素，横1068画素のディジタルカラー画像である．
原画像を1/2サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．なお，拡大する際には，単純補間するために「box」オプションを設定する．

    IMG = imresize(ORG,0.5); % 画像の縮小  
    IMG2 = imresize(IMG,2,'box'); % 画像の拡大

1/2サンプリングの結果を図２に示す．

![1/2サンプリング](https://github.com/natorinep/my_image_processing/blob/master/image/1_2.jpg)

図2 1/2サンプリング

同様に原画像を1/4サンプリングするには，画像を1/2倍に縮小したIMGをさらに1/2倍し，4倍に拡大する．すなわち，

    IMG = imresize(ORG,0.5); % 画像の縮小  
    IMG2 = imresize(IMG,4,'box'); % 画像の拡大

となる．1/4サンプリングの結果を図３に示す．

![1/4サンプリング](https://github.com/natorinep/my_image_processing/blob/master/image/1_3.jpg)

図3 1/4サンプリング

同様に繰り返し，1/8，1/16，1/32サンプリングまで行う．
サンプリングの結果を図４～６に示す．

![1/8サンプリング](https://github.com/natorinep/my_image_processing/blob/master/image/1_4.jpg)

図4 1/8サンプリング

![1/16サンプリング](https://github.com/natorinep/my_image_processing/blob/master/image/1_5.jpg)

図5 1/16サンプリング

![1/32サンプリング](https://github.com/natorinep/my_image_processing/blob/master/image/1_6.jpg)

図6 1/32サンプリング

このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生する．
