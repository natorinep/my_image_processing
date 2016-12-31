#課題10レポート

画像をグレースケール化し，プレウィット法，ソベル法，キャニー法によりエッジの抽出を行う．

![グレースケール](https://github.com/natorinep/my_image_processing/blob/master/image/10_1.jpg)  
図1 グレースケール

この画像からエッジ抽出を行う．

    IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
    imagesc(IMG); colormap('gray'); colorbar;% 画像表示
    pause; % 一時停止

    IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
    imagesc(IMG); colormap('gray'); colorbar;% 画像表示
    pause; % 一時停止

    IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）
    imagesc(IMG); colormap('gray'); colorbar;% 画像表示
    pause; % 一時停止
    
それぞれの結果を図2，3，4に示す．

![プレウィット](https://github.com/natorinep/my_image_processing/blob/master/image/10_2.jpg)  
図2 プレウィット法

![ソベル](https://github.com/natorinep/my_image_processing/blob/master/image/10_3.jpg)  
図3 ソベル法

![キャニー](https://github.com/natorinep/my_image_processing/blob/master/image/10_4.jpg)  
図4 キャニー法

プレウィット法とソベル法は同じようなエッジの抽出が得られた．2つとも明暗がはっきりしているエッジ部分を抽出している．
キャニー法は他の2つと比べ少しの色の差の部分でもエッジ抽出を行っていることが分かる．
