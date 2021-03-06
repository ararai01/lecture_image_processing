# 課題9レポート メディアンフィルタと先鋭化
メディアンフィルターを適用し，ノイズ除去する。


まず始めに使用した原画像について説明する。

「TAN_uwanensyuhikusugi_TP_V.jpg」を原画像とする．この画像はディジタルカラー画像である．

使用した原画像を図１に示す。


![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/TAN_uwanensyuhikusugi_TP_V.jpg)  
図1 原画像

白黒濃淡画像に変換する。



ORG = imread('TAN_uwanensyuhikusugi_TP_V.jpg'); % 画像の読み込み

ORG = rgb2gray(ORG); % 白黒濃淡画像に変換

imagesc(ORG); colormap(gray); colorbar; % 画像の表示

pause;

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai9-1.png)  
図2 白黒濃淡画像

ノイズを添付する。

ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付

imagesc(ORG); colormap(gray); colorbar; % 画像の表示

pause;

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai9-2.png)  
図3 ノイズ添付画像

平滑フィルタによるノイズ除去。

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去

imagesc(IMG); colormap(gray); colorbar; % 画像の表示

pause;

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai9-3.png)  
図4 平滑化フィルタによるノイズ除去画像


メディアンフィルタによるノイズ除去。

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去

imagesc(IMG); colormap(gray); colorbar; % 画像の表示

pause;

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai9-4.png)  
図5 メディアンフィルタによるノイズ除去画像

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;

![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai9-5.png)  
図6 フィルタの設計
