#課題5レポート

画像をグレースケール化し，判別分析法により2値化を行う．分散度が最大になる点を計算により求めて，閾値の設定をする．

    ORG=imread('neko.jpg'); % 原画像の入力
    ORG = rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
    imagesc(ORG); colormap(gray); colorbar;
    
原画像をグレースケールにした画像を図1に示す．

![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/5_1.jpg)  
図1 グレースケール1  

以下のプログラムから計算によって閾値を設定する．

    H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納
    myu_T = mean(H);
    max_val = 0;
    max_thres = 1;
    for i=1:255
    C1 = H(1:i); %ヒストグラムを2つのクラスに分ける
    C2 = H(i+1:256);
    n1 = sum(C1); %画素数の算出
    n2 = sum(C2);
    myu1 = mean(C1); %平均値の算出
    myu2 = mean(C2);
    sigma1 = var(C1); %分散の算出
    sigma2 = var(C2);
    sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出
    sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出
    if max_val<sigma_B/sigma_w
    max_val = sigma_B/sigma_w;
    max_thres =i;
    end;
    end;

    IMG = ORG > max_thres;
    imagesc(IMG); colormap(gray); colorbar;
    
この判別分析法のプログラムにより2値化された画像が図2となった．    
    
![判別分析法1](https://github.com/natorinep/my_image_processing/blob/master/image/5_2.jpg)  
図2 判別分析法による2値化(1)

得られた結果はあまり良好な結果が得られていなかった．これは原画像のグレースケール化により背景が白くなりすぎている影響かと思われる．　　そのため，別の画像(図3)を用意して判別分析法を行ってみる．

![原画像2](https://github.com/natorinep/my_image_processing/blob/master/program/neko2.jpg)  
図3 原画像2 

同様にグレースケール化，判別分析法を用いて2値化を行う．結果を図4,5に示す．

![グレースケール2](https://github.com/natorinep/my_image_processing/blob/master/image/5_3.jpg)  
図4 グレースケール2  

![判別分析法2](https://github.com/natorinep/my_image_processing/blob/master/image/5_4.jpg)  
図5 判別分析法による2値化(2)

図5より図2と比べてそれらしい2値化が得られている．  
判別分析法は画像により上手く2値化が得られない場合もあることが確認できた．対象物と背景がバランスよく配置され輝度値が均等になっている方が良好な得られると思われる．
