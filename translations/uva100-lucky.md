---
title: "The 3n + 1 problem"
date: 2001-11-22 00:00
probid: 100
uvaid: 36
translator: "Luckycat"
transource: "Lucky 貓"
transurl: "http://luckycat.kshs.kh.edu.tw/homework/q100.htm"
categories:
- "Volume - 001"
tags:
- "模擬"
- "建表"
- "線段樹"
- "靜態區間查詢問題"
---

考慮以下的演算法：

1. 輸入 n
2. 印出 n
3. 如果 n = 1 則**結束**
4. 如果 n 是奇數 那麼 $n\leftarrow{3n+1}$
5. 否則 $n\leftarrow{n/2}$
6. 回到 2

例如輸入 22，得到的數列：22 11 34 17 52 26 13 40 20 10 5 16 8 4 2 1

據推測此演算法對任何整數而言會終止 (當列印出 1 的時候)。雖然此演算法很簡單，但以上的推測是否真實卻無法知道。然而對所有的 $0 < n < 1,000,000$ 來說，以上的推測已經被驗證是正確的。

給一個輸入 $n$，透過以上的演算法我們可以得到一個數列 (1 作為結尾)。此數列的長度稱為 $n$ 的 *cycle length*。上面提到的例子，22 的 cycle length 為 16。

問題來了：對任 2 個整數 $i, j$ 我們想要知道介於 $i, j$ (包含 $i, j$) 之間的數所產生的數列中最大的 cycle length 是多少。

## Input ##

輸入可能包含了好幾列測試資料，每一列有一對整數資料 $i, j$。

$0 < i,j < 1,000,000$

## Output ##

對每一對輸入 $i, j$ 你應該要輸出 $i, j$ 和介於 $i, j$ 之間的數所產生的數列中最大的 cycle length。

## Sample Input ##

	1 10
	10 1
	100 200
	201 210
	900 1000

## Sample Output ##

	1 10 20
	10 1 20
	100 200 125
	201 210 89
	900 1000 174
