#課題９ メディアンフィルタと先鋭化
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




ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付

imagesc(ORG); colormap(gray); colorbar; % 画像の表示

pause;



IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去

imagesc(IMG); colormap(gray); colorbar; % 画像の表示

pause;


IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去

imagesc(IMG); colormap(gray); colorbar; % 画像の表示

pause;


f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
