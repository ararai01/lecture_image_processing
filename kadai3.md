# 課題3レポート 閾値処理
閾値処理画像を生成した．

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


輝度値が64以上の画素を1，その他を0に変換

IMG = ORG > 64; 

imagesc(IMG); colormap(gray); colorbar;

pause;


輝度値64以上の画素を１としたときの結果を図３に示す。


![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai3-1.png)  
図３　輝度値64以上の画素を１としたときの画像

同様にして輝度値96以上の画素を１としたとき、白黒で画像を表示する。

IMG = ORG > 96;

imagesc(IMG); colormap(gray); colorbar;

pause;


同様にして輝度値96以上の画素を１としたときの結果を図４に示す。

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai3-2.png)  
図４ 輝度値96以上の画素を１としたときの画像

同様にして輝度値128以上の画素を１としたとき、白黒で画像を表示する。

IMG = ORG > 128;

imagesc(IMG); colormap(gray); colorbar;

pause;

輝度値128以上の画素を１としたときの結果を図５に示す。


![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai3-3.png)  
図５ 輝度値128以上の画素を１としたときの画像

同様にして輝度値192以上の画素を１としたとき、白黒で画像を表示する。

IMG = ORG > 192;

imagesc(IMG); colormap(gray); colorbar;

輝度値192以上の画素を１としたときの結果を図５に示す。


![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai3-4.png)  
図6 輝度値192以上の画素を１としたときの画像


輝度値の変化に対応した画像の確認ができた。

