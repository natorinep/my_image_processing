#課題5レポート

    ORG=imread('neko.jpg'); % 原画像の入力
    ORG = rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
    imagesc(ORG); colormap(gray); colorbar;

![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/5_1.jpg)  
図1 グレースケール1  

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
    
![判別分析法1](https://github.com/natorinep/my_image_processing/blob/master/image/5_2.jpg)  
図2 判別分析法による2値化(1)

![グレースケール2](https://github.com/natorinep/my_image_processing/blob/master/image/5_3.jpg)  
図3 グレースケール2  

![判別分析法2](https://github.com/natorinep/my_image_processing/blob/master/image/5_4.jpg)  
図2 判別分析法による2値化(2)
