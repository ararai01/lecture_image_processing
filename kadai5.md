# 課題5レポート 判別分析法
判別分析法によって二値化する．

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


判別分析法を実行

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

pause;



![原画像](https://github.com/ararai01/lecture_image_processing/blob/master/my_image/kadai5-2.png)  
図3 判別分析による二値化画像



判別分析法による二値化の確認ができた。


