#課題9レポート

画像をグレースケール化し，ノイズを付与する．そのノイズを平滑化ィルタ，メディアンフィルタ，設計によるフィルタで除去して結果を比べる．
原画像をグレースケールにした画像を図1に示す．

    ORG = imread('neko.jpg'); % 画像の読み込み
    ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
    imagesc(ORG); colormap(gray); colorbar; % 画像の表示

![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/9_1.jpg)  
図1 グレースケール  

この画像にノイズを付与する．付与した画像を図2に示す．

    ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付
    imagesc(ORG); colormap(gray); colorbar; % 画像の表示
    
![ノイズ](https://github.com/natorinep/my_image_processing/blob/master/image/9_2.jpg)  
図2 ノイズ  

このノイズをフィルタによって除去を行う．

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; % 画像の表示

平滑化フィルタによって除去した画像を図3，メディアンフィルタによって除去した画像を図4，フィルタ設計よるフィルタで除去した画像を図5に示す．

![平滑化フィルタ ](https://github.com/natorinep/my_image_processing/blob/master/image/9_3.jpg)  
図3 平滑化フィルタ  

![メディアンフィルタ](https://github.com/natorinep/my_image_processing/blob/master/image/9_4.jpg)  
図4 メディアンフィルタ  

![設計フィルタ](https://github.com/natorinep/my_image_processing/blob/master/image/9_5.jpg)  
図5 設計フィルタ  

平滑化によるフィルタではある程度ノイズが除去されているが薄くまだノイズが残っている．
メディアンフィルタによる結果は平滑化によるフィルタに比べ非常に綺麗にノイズが除去されていて，図1のグレースケールと比較してもノイズ付与前と同じような画像になっていた．
設計のフィルタはノイズ自体は無くなっているが，画像全体が灰色がかっており，図1のグレースケール画像と同じとは言えない結果となった．
