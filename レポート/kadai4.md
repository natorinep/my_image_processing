#課題4レポート

画像をグレースケール画像に変換し，そのときのヒストグラムを確認する．

    ORG=imread('neko.jpg'); % 原画像の入力
    ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
    imagesc(ORG); colormap(gray); colorbar;

によって原画像を表示した結果を図1に示す．
