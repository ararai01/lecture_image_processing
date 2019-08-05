# 課題2レポート 階調数と疑似輪郭
２階調，４階調，８階調の画像を生成した．

まず始めに使用した原画像について説明する。
「pet_robot_man」を原画像とする．この画像はディジタルカラー画像である．
使用した原画像を図１に示す。

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/pet_robot_man.png)  
図1 原画像

clear; % 変数のオールクリア

ORG=imread('pet_robot_man.png'); % 原画像の入力

ORG = rgb2gray(ORG); colormap(gray); colorbar;

imagesc(ORG); axis image; % 画像の表示

pause; % 一時停止


によって原画像を読み込み、読み込んだ画像を白黒二値画像に変換した。
表示した結果を表２に示す。

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai2_1.png)  
図２ 白黒二値画像に変換された原画像

２段階調を生成するには画像のORGを128以上に設定する。

% ２階調画像の生成

IMG = ORG>128;

imagesc(IMG); colormap(gray); colorbar;  axis image;

pause;


２段階調画像の生成の結果を図３に示す。


![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai2_2.png)  
図３　生成した２段階調画像

４段階調を生成するには画像のORGを64以上に設定する。
IMGは階調数分作り（４階調ならIMGを４種類作り、４種類目で３種類全て足し合わせる）、白黒で画像を表示する。

% ４階調画像の生成

IMG0 = ORG>64;

IMG1 = ORG>128;

IMG2 = ORG>192;

IMG = IMG0 + IMG1 + IMG2;

imagesc(IMG); colormap(gray); colorbar;  axis image;

pause;


４段階調画像の生成の結果を図４に示す。

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai2_3.png)  
図４ 生成した４段階調画像

４段階調同様に、８段階調を生成するには画像のORGを32以上に設定する。
IMGは階調数分作り（８階調ならIMGを８種類作り、８種類目で７種類全て足し合わせる）、白黒で画像を表示する。

% ８階調について

IMG0 = ORG>32;

IMG1 = ORG>64;

IMG2 = ORG>96;

IMG3 = ORG>128;

IMG4 = ORG>192;

IMG5 = ORG>224;

IMG6 = ORG>256;

IMG = IMG0 + IMG1 + IMG2 + IMG3+ IMG4+ IMG5+ IMG6;

imagesc(IMG); colormap(gray); colorbar;  axis image;

８段階調画像の生成の結果を図５に示す。


![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai2_4.png)  
図５ 生成した８段階調画像


このように階調を変化させることができる。
