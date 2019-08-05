# 課題6レポート 画像の二値化
ディザ法によって二値化する．

まず始めに使用した原画像について説明する。
「pet_robot_man.png」を原画像とする．この画像はディジタルカラー画像である．
使用した原画像を図１に示す。


![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/pet_robot_man.png)  
図1 原画像

白黒濃淡画像に変換する。

clear; % 変数のオールクリア

ORG=imread('pet_robot_man.png'); % 原画像の入力

ORG = rgb2gray(ORG);

imagesc(ORG); colormap(gray); colorbar; % 画像の表示

pause; % 一時停止

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai5-1.png)  
図2 白黒濃淡画像

輝度値128以上のときの二値化

IMG = ORG>128; % 128による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai6-1.png)  
図3 輝度値128以上のときの二値化画像

ディザ法による二値化

IMG = dither(ORG); % ディザ法による二値化

imagesc(IMG); colormap(gray); colorbar; % 画像の表示

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai6-.png)  
図4　ディザ法による二値化画像


判別分析法による二値化の確認ができた。



