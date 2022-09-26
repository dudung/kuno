---
layout: post
author: viridi
title: posisi
mathjax: true
ptext: false
x3dom: false
threejs: false
category: kinematics
tags: ["kinematicscs", "position"]
date: 2020-08-08 22:44:00 +07
permalink: position
---
Posisi, posisi relatif, perpindahan, jarak

## Sistem koordinat
Dalam pembahasan ini digunakan sistem koordinat kartesian dimensi-satu (1-D) dengan variabel $x$. Pusat koordinat ditandai dengan nilai $x = 0$. Umumnya sebelah kanan pusat koordinat adalah nilai positif atau $x > 0$ dan sebelah kirinya adalah nilai negatif atau $x < 0$. Konvensi ini akan digunakan kecuali diberikan keterangan lain. Dalam sistem satuan internasional (SI), variabel $x$ dinyatakan dalam meter atau dapat disingkat $\rm m$.

## Posisi
Bila digunakan satuan meter untuk posisi, suatu benda $\rm A$ yang berada tujuh satuan di sebelah kanan pusat koordinat akan memiliki posisi yang dinyatakan dengan $x_A = 7 \ \rm m$, dan benda $\rm B$ yang berada sembilan satuan di sebelah kiri pusat koordinat akan memiliki posisi yang dinyatakan dengan $x_B = -9 \ \rm m$. Posisi merupakan besaran vektor sehingga tandanya berperan menunjukkan arah yang dinyatakan dari pusat koordinat.

Terdapat berbagai cara menyatakan posisi suatu benda $\rm A$ pada saat tertentu $t$, seperti

\begin{equation}
\label{eqn:position}
x_A(t) \equiv x_A \equiv x_t,
\end{equation}

di mana notasi paling kiri adalah yang paling lengkap, notasi tengah bila dibahas hanya pada satu saat tertentu (tidak ada pembahasan pada dua saat berbeda), dan notasi paling kanan bila hanya terdapat satu benda akan tetapi membahas posisi pada berbagai waktu berbeda. Untuk notasi terakhir kadang digunakan pula bila saat yang dibahas adalah $t = t_n$ dengan $n = 0, 1, 2, ..$ maka digunakan

\begin{equation}
\label{eqn:position-tn}
x_A(t_n) \equiv x_{t_n} \equiv x_n.
\end{equation}

Konvensi lain yang semakin membingungkan adalah bila terdapat benda $\rm P$ yang pada saat $t = t_1$ berada pada titik $\rm A$ atau $x = x_A$ dan pada saat $t = t_2$ berada pada titik $\rm B$ atau $x = x_B$ maka berlaku bahwa

\begin{equation}
\label{eqn:position-tn-xm}
x_P(t_1) \equiv x_{t_1} \equiv x_1 \equiv x_A, \quad x_P(t_2) \equiv x_{t_2} \equiv x_2 \equiv x_B.
\end{equation}

Dengan demikian disarankan untuk selalu memperhatikan konvensi simbol yang digunakan saat membaca suatu teks. Usahakan untuk menggunakan simbol dengan indeks paling ringkas untuk memudahkan mengingatnya. Dan dalam satu tulisan sebaiknya digunakan notasi yang sama. Penggunaan notasi yang berbeda dalam tulisan ini hanya untuk menunjukkan terdapatnya berbagai konvensi penulisan simbol dan masih terdapat juga yang belum dibahas.

## Posisi relatif
Posisi relatif adalah posisi yang dinyakan relatif terhadap suatu titik acuan. Posisi relatif suatu benda $\rm P$ terhadap benda $\rm O$ adalah

\begin{equation}
\label{eqn:position-relative}
x_{PO} = x_P - x_O,
\end{equation}

dengan $x_P$ adalah benda $\rm P$ dan $x_O$ adalah posisi benda $\rm O$.

Benda $\rm A$ memiliki posisi $x_A = 20 \ \rm m$ dan benda $\rm B$ memiliki posisi $x_B = 15 \ \rm m$. Posisi relatif benda $\rm A$ terhadap benda $\rm B$ adalah

\begin{equation}
\nonumber
x_{AB} = x_A - x_B = 20 \ \rm m - 15 \ \rm m = 5 \ \rm m
\end{equation}

dan posisi relatif benda $\rm B$ terhadap benda $\rm A$ adalah

\begin{equation}
\nonumber
x_{BA} = x_B - x_A = 15 \ \rm m - 20 \ \rm m = -5 \ \rm m.
\end{equation}

Posisi relatif, sebagaimana posisi, juga merupakan besaran vektor. Akan tetapi tanda pada posisi relatif menyatakan arah dari titik acuan, sedangkan pada posisi tanda menyatakan arah dari pusat koordinat. Atau dengan kata lain dapat dinyatakan bahwa posisi adalah posisi relatif dengan titik acuannya adalah pusat koordinat.

## Perpindahan
Perpindahan suatu benda $\rm A$ dari posisi awal saat $t_i$ ke posisi akhir saat $t_f$ diberikan oleh

\begin{equation}
\label{eqn:position-displacement}
\Delta x_{A, t_i \rightarrow t_f} = x_A(t_f) - x_A(t_i).
\end{equation}

Bila terdapat hanya satu benda indeks $\rm A$ dalam Persamaan \eqref{eqn:position-displacement} dapat tidak digunakan agar menjadi lebih sederhana.

Perpindahan merupakan besaran vektor, yang arahnya menentukan ke mana perpindahan terjadi, dari posisi awal (inisial) ke posisi akhir (final). Bila perpindahan bertanda positif maka benda berpindah ke kanan dari posisi awalnya, sedangkan bila perpindahan berharga negatif maka benda berpindah ke kiri dari posisi awalnya.

## Jarak
Dalam Persamaan \eqref{eqn:position-relative} untuk posisi relatif dan \eqref{eqn:position-displacement} untuk perpindahan, terlihat bahwa keduanya merupakan selisih dari posisi. Perbedaannya adalah bahwa posisi relatif mengaitkan dua benda berbeda pada waktu yang sama, sedangkan perpindahan mengaitkan benda yang sama pada dua waktu yang berbeda.

Untuk jarak terdapat sudut pandang keduanya yang harus diperhatikan saat konsep ini akan digunakan. Selain itu jarak merupakan merupakan besaran skalar sehingga nilainya selalu positif.

Untuk sudut pandang pertama, terkait dengan posisi relatif, jarak merupakan nilai mutlak dari posisi relatif

\begin{equation}
\label{eqn:position-relative-distance}
s_{PO} = |x_P - x_O|,
\end{equation}

yang menyatakan jarak titik $\rm P$ terhadap titik $\rm O$. Dan nilai yang diperoleh ini akan berlaku pula sebaliknya, yaitu jarak titik $\rm O$ terhadap titik $\rm P$ dikarenakan nilainya selalu positif.

Sedangkan untuk untuk sudut pandang kedua, terkait dengan perpindahan, jarak merupakan nilai mutlak dari perpindahan yang terjadi dengan perpindahan hanya ke satu arah

\begin{equation}
\label{eqn:position-displacement-distance}
s_{A, t_i \rightarrow t_f} = |x_A(t_f) - x_A(t_i)|,
\end{equation}

yang menyatakan jarak dari posisi akhir terhadap posisi awal. Bila benda A mengalami beberapa kali perubahan arah perpindahan (arah kecepatannya berubah) dengan posisi-posisinya pada saat $t_1$, $t_2$, $t_3$, dan $t_4$ berturut-turut adalah $x_1 = x(t_1)$, $x_2 = x(t_2)$, $x_3 = x(t_3)$, dan $x_4 = x(t_4)$, maka jarak yang ditempuh antara $t_1$ sampai $t_4$ adalah

\begin{equation}
\label{eqn:position-displacement-distance-velocities}
s_{41} = |x_2 - x_1| + |x_3 - x_2| + |x_4 - x_3|.
\end{equation}

Perhatikan bagaimana penggunaan indeks pada Persamaan \eqref{eqn:position-displacement-distance-velocities} lebih disederhanakan dari Persamaan \eqref{eqn:position-displacement-distance} dikarenakan membahas hanya satu benda $\rm A$. Indeks waktu $t_i \rightarrow t_f$ juga disederhakan menjadi $t_f t_i$ lalu $f i$ seperti dalam Persamaan \eqref{eqn:position-tn}.

## Latihan
1. Berikan contoh kapan sebaiknya digunakan Persamaan \eqref{eqn:position}, \eqref{eqn:position-tn}, dan \eqref{eqn:position-tn-xm}.
2. Dengan menggunakan satuan m untuk posisi, benda $\rm A$ berada emmpat satuan di sebelah kanan pusat koordinat sedangkan benda $\rm B$ berada delapan satuan di sebelah kiri pusat koordinat. Nyatakanlah posisi kedua benda dengan variabel $x_A$ dan $x_B$.
3. Tedapat benda $\rm P$ dan $\rm Q$ yang masing-masing memiliki posisi $x_P = 2 \ \rm m$ dan $x_Q = -4 \ \rm m$. Tentukanlah posisi relatif benda $\rm Q$ terhadap benda $\rm P$. Gunakan Persamaan \eqref{eqn:position-relative}.
4. Bila posisi relatif benda $\rm A$ terhadap benda $\rm B$ adalah $-10 \ \rm m$ dan posisi benda $\rm A$ adalah $x_A = 2 \ \rm m$, tentukanlah posisi benda $\rm B$.
5. Suatu benda $\rm Q$ saat $t = 2 \ \rm s$ berada pada posisi $x(2) = 10 \ \rm m$ dan saat $t = 4 \ \rm s$ berada pada posisi $x(4) = 25 \ \rm m$. Tentukanlah perpindahan benda itu antara waktu $2 \ \rm s$ dan $4 \ \rm s$.
6. Jelaskan dengan menggunakan contoh perbedaan konsep antara posisi relatif dan perpindahan pada Persamaan \eqref{eqn:position-relative-distance} dan \eqref{eqn:position-displacement-distance} Gunakan notasi yang memudahkan.
7. Tentukan jarak yang ditempuh benda $\rm P$ bila saat $t = 2 \ {\rm s}$ berada pada posisi $x(2) = 4 \ \rm m$, saat $t = 4 \ \rm s$ berada pada posisi $x(4) = 10 \ \rm m$, dan saat $t = 6 \ \rm s$ berada pada posisi $x(6) = 1 \ \rm m$. Gunakan Persamaan \eqref{eqn:position-displacement-distance-velocities}.
8. Saat $t_1 = 0 \ \rm s$ benda $\rm A$ berada pada posisi $3 \ \rm m$ dan benda $\rm B$ berada pada posisi $4 \ \rm m$. Kemudian saat $t_2 = 2 \ \rm s$ kedua benda berada pada posisi berturut-turut $ 10 \ \rm m$ dan $5 \ \rm m$. Hitunglah posisi relatif benda $\rm A$ terhadap benda $\rm B$ pada kedua waktu tersebut. Gunakan notasi yang paling memudahkan.
9. Dengan menggunakan data pada soal sebelumnya tentukanlah perpindahan dan jarak yang ditempuh masing-masing pada pada selang waktu tersebut.
10. Terdapat dua buah benda, $\rm A$ dan $\rm B$, yang bergerak dari dari posisi awal masing-masing ke posisi akhir masing-masing dengan waktu pada kedua keadaan tersebut adalah $t_1$ dan $t_2$. Bila perpindahan benda pertama adalah negatif perpindahan benda kedua, hitunglah posisi relatif benda pertama terhadap benda kedua dan juga posisi relatif benda kedua terhadap benda pertama saat $t_1$ dan $t_2$. Ungkapkan bila terdapat suatu hal yang menarik.

## Catatan
10. 09 2nd, 2020-08-08 1st version.