#課題4レポート

画像をグレースケール画像に変換し，そのときのヒストグラムを確認する．

    ORG=imread('neko.jpg'); % 原画像の入力
    ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
    imagesc(ORG); colormap(gray); colorbar;

によって原画像を表示した結果を図1に示す．

![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/4_1.jpg)  
図1 グレースケール  

この画像の濃度ヒストグラムを表示する．

    imhist(ORG); % ヒストグラムの表示
    
ヒストグラムを表示した結果を図2に示す．

![濃度ヒストグラム](https://github.com/natorinep/my_image_processing/blob/master/image/4_2.jpg)  
図2 濃度ヒストグラム

図2よりこの画像は40,240辺りの分布が多い．中間付近の濃度が少なめなので比較的白黒の差が大きい画像である．
また0や255付近の分布も低いためあまり白のみや黒のみの画素は少ないと言える．
