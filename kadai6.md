# 課題6レポート 画像の二値化
ディザ法によって二値化する．

まず始めに使用した原画像について説明する。
「TAN_uwanensyuhikusugi_TP_V」を原画像とする．この画像はディジタルカラー画像である．
使用した原画像を図１に示す。


![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/TAN_uwanensyuhikusugi_TP_V.jpg)  
図1 原画像

白黒濃淡画像に変換する。

ORG=imread('TAN_uwanensyuhikusugi_TP_V.jpg'); % 原画像の入力

ORG = rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換

imagesc(ORG); colormap(gray); colorbar;

pause;



![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai5-1.png)  
図2 白黒濃淡画像

ディザ法を実行




![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai5-2.png)  
図3 判別分析による二値化画像



判別分析法による二値化の確認ができた。



