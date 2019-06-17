# 課題2レポート 階調数と疑似輪郭
２階調，４階調，８階調の画像を生成した．

まず始めに使用した原画像について説明する。
「pet_robot_man」を原画像とする．この画像は縦420画素，横560画素のディジタルカラー画像である．
使用した原画像を示す。

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/pet_robot_man.png)  
図1 原画像

clear; % 変数のオールクリア

ORG=imread('pet_robot_man.png'); % 原画像の入力
ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image; % 画像の表示
pause; % 一時停止

によって原画像を読み込み、読み込んだ画像を白黒二値画像に変換した。
表示した結果を表２に示す。

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/pet_robot_man.png)  
図２ 変換された原画像

% ２階調画像の生成
IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;
pause;

% ４階調画像の生成
IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;
imagesc(IMG); colormap(gray); colorbar;  axis image;
pause;

% ８階調については，各自検討してください．
IMG0 = ORG>32;
IMG1 = ORG>64;
IMG2 = ORG>96;
IMG3 = ORG>128;
IMG4 = ORG>192;
IMG5 = ORG>224;
IMG6 = ORG>256;
IMG = IMG0 + IMG1 + IMG2 + IMG3+ IMG4+ IMG5+ IMG6;
imagesc(IMG); colormap(gray); colorbar;  axis image;
