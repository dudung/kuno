---
layout: post
author: viridi
title: besaran dan satuan
mathjax: true
chartjs: false
ptext: false
x3dom: false
threejs: false
3dmol: false
category: quantities
tags: ["quantities", "units"]
date: 2020-07-23 19:44:00 +07
permalink: quantities
---
Besaran-besaran fisis, satuan, konversi satuan


## Besaran pokok
Terdapat tujuh besaran pokok yang merupakan dasar dari sistem satuan internasional (international system of units, SI), yang meliputi panjang, massa waktu arus listrik, temperatur termodinamika, jumlah bahan, dan intensitas cahaya [[1](#ref1)].

Tab 1 Besaran pokok dan nama serta simbolnya dalam SI.

---------|------|--------|
**Besaran** | **Nama** | **Simbol**
panjang | meter| m
massa | kilogram | kg
waktu | detik | s
arus listrik | ampere | A
temperatur termodinamika | kelvin | K
jumlah zal | mole | mol
intensitas cahaya | candela | cd


## Besaran turunan
Besaran turunan yang bersumber dari besaran pokok terdapat dalam bebagai bidang fisika, berupa besaran mekanika, akustik, termal, molekular, listrik, optik, fisika atom, dan radiologi [[2](#ref2)], serta lainnya. Untuk besaran-besaran turunan berikut akan selalu digunakan satuan dalam SI.

### Kecepatan
Kecepatan $v$ yang menggambarkan perubahan posisi $\Delta{x}$ dalam suatu selang waktu $\Delta{t}$

\begin{equation}
\label{eqn:velocity}
v = \frac{\Delta{x}}{\Delta{t}},
\end{equation}

memiliki satuan m/s. Besaran dengan satuan yang sama dengan Eqn. \eqref{eqn:velocity} adalah kecepatan rata-rata, kecepatan sesaat, rata-rata kecepatan, laju, laju sesaat, dan rata-rata laju.

### Luas penampang
Suatu luas penampang $A$ dari suatu persegi panjang adalah

\begin{equation}
\label{eqn:area}
A = pl,
\end{equation}

dengan panjang $p$ dan lebar $l$. Untuk bentuk geometri yang lain akan memiliki rumusan yang berbeda dengan Eqn. \eqref{eqn:area}.

### Laju alir volumetrik
Debit atau laju alir volumetrik dapat diperoleh melalui [[3](#ref3)]

\begin{equation}
\label{eqn:volumetric-flow-rate}
Q = vA,
\end{equation}

dengan laju alir $v$ dan luas penampang $A$ telah memiliki arah sejajar, atau $v$ berarah tegak lurus menembus $A$. Satuan dari debit dalam Eqn. \eqref{eqn:volumetric-flow-rate} adalah m$^3$/s.

### Silsilah besaran
Dengan menggunakan lambang $x, y, z$ untuk posisi dan $t$ untuk waktu dapat dituliskan semacam silsilah dari Eqns. \eqref{eqn:velocity}-\eqref{eqn:volumetric-flow-rate} seperti dalam Fig 1, yang menggambarkan penggunaan besaran-besaran pokok (dan juga besaran-besaran turunan) dalam besaran-besaran turunan (berikutnya).

```batch
t1 ──┐
     ├── Δt ──┐
t2 ──┘        │
              ├── v ──┐
x1 ──┐        │       │
     ├── Δx ──┘       │
x2 ──┘                │
                      ├── Q
y1 ──┐                │
     ├── Δy ──┐       │
y2 ──┘        │       │
              ├── A ──┘
z1 ──┐        │
     ├── Δz ──┘
z2 ──┘
```
Fig 1 Silsilah besaran pokok dan turunan untuk debit $Q$.

Dengan demikian dapat dilacak dengan mudah satuan dari $Q$, dengan mengetahui satuan dari $v$ dan $A$.


## Persepsi baru
Terdapat persepsi lain mengenai besaran pokok, yang tidak didefinisikan, sementara besaran turunan didefinisikan berdasarkan besaran pokok tersebut [[4](#ref4)]. Untuk itu telah terdapat tujuh konstanta yang menjadi besaran pokok baru SI, yaitu frekuensi, kecepatan, aksi, muatan listrik, kapasitas panas, jumlah zat, dan intensitas cahaya [[5](#ref5)].


## Latihan
1. Bila saat $t_1$ benda berada pada posisi $x_1$ dan saat $t_2$ berada posisi $x_2$, tuliskanlah persamaan-persamaan untuk menghitung kecepatan rata-rata dan laju rata-rata dalam selang waktu $t_1 \le t \le t_2$.
2. Bila saat $t_1$ diketahui kecepatan sesaat $v_1$ dan demikian pula untuk saat $t_2$ dan $t_3$. Tuliskanlah rata-rata kecepatan untuk ketiga waktu tersebut.
3. Terdapat suatu pipa dengan penampang berbentuk elips dengan jari-jari $r_1$ dan $r_2$. Tuliskan persamaan untuk memperoleh luas penampang pipa tersebut.
4. Bagaimana cara untuk memperoleh besaran turunan massa jenis atau rapat massa $\rho$? Tuliskan perumusannya dan silsilah besarannya.
5. Tuliskan silsilah besaran daya $P$ melalui energi kinetik, massa, kecepatan, posisi, waktu dan gaya, kecepatan.
6. Tuliskan silsilah besaran daya $P$ melalui arus dan tegangan listrik, energi listrik dan muatan, serta arus listrik dan waktu.
7. Bandingkan kedua silsilah untuk memperoleh daya $P$ tersebut.
8. Bacalah mengenai tujuh besaran pokok baru SI [[5](#ref5)] dan buatlah tabel yang membandingkan ketujuh besaran pokok sebelumnya dan besaran pokok baru ini.


## Referensi
1. <a name="ref1"></a>-, "SI base units" in the NIST Reference ofn Constants, Units, and Uncertainty, National Institute of Standards and Technology, U.S. Department of Commernce, 
Gaithersburg, url <https://physics.nist.gov/cuu/Units/units.html> [20200726].
2. <a name="ref2"></a>-, "9.1 Physical Quantities & Units", WikiLecture, 16 Sep 2015, url <https://www.wikilectures.eu/w/9.1_Physical_Quantities_&_Units> [2020726].
3. <a name="ref3"></a>Wikipedia contributors, "Volumetric flow rate", Wikipedia, The Free Encyclopedia, 26 Jun 2020, 11:24 UTC, url <https://en.wikipedia.org/w/index.php?oldid=964588105> [20200726].
4. <a name="ref4"></a>Dmytro Taranovsky, "Physical Quantities", Massachusetts Institute of Technology, 25 Mar 2000, url <http://web.mit.edu/dmytro/www/other/PhysicalQuantities.htm> [20200726].
5. <a name="ref5"></a>David Newell, "A more fundamental International System of Units", Physics Today, vol. 67, no. 5, pp. 35-41, Jul 2014, url <https://doi.org/10.1063/PT.3.2448>
