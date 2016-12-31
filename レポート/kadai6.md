#課題6レポート
画像をグレースケール化し，閾値128で2値化を行った場合とディザ法による2値化の場合と比較する．

  ORG=imread('neko.jpg'); % 原画像の入力
  ORG = rgb2gray(ORG);
  imagesc(ORG); colormap(gray); colorbar; % 画像の表示

原画像をグレースケールにした画像を図1に示す．
