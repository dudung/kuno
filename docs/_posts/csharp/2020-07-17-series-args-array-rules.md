---
layout: post
author: viridi
title: Show finite integer power series with C#
date: 2020-07-17 07:56:00 +07
mathjax: true
ptext: false
x3dom: false
threejs: false
category: learn
tags: ["C#", "CLI", "series"]
---
Produce integer power series with rules using program arguments through CLI


## Power series
A power series can be written in a simple form of [[1](#ref1)]

\begin{equation}
\label{eqn-series-power-infinite}
\sum_{n = 0}^\infty c_n x^n = c_0 + c_1 x + c_2 x^2 + c_3 x^3 + \dots,
\end{equation}

where in general $x \in \mathbb{R}$, but now we only consider that $x \in \mathbb{Z}$ for simplicity. And we also limit Eqn. \eqref{eqn-series-power-infinite} to

\begin{equation}
\label{eqn-series-power-finite}
\sum_{n = 0}^N c_n x^n = c_0 + c_1 x + c_2 x^2 + \dots + c_N x^N,
\end{equation}

a fininte power series, that only consists of $N + 1$ terms, where

\begin{equation}
\label{eqn-series-power-finite-coefficients}
\mathbf{C} = \left[ c_0 \quad c_1 \quad c_2 \quad c_3 \ \dots \ c_N \right]
\end{equation}

are the coefficients. Then, \eqref{eqn-series-power-finite} can be writen in the form of

\begin{equation}
\label{eqn-series-power-finite-matrix}
\sum_{n = 0}^N c_n x^n = \mathbf{C} \cdot \mathbf{X}^T
\end{equation}

with

\begin{equation}
\label{eqn-matrix-row-x}
\mathbf{X} = \mathbf{X}(x) = \left[ 1 \quad x \quad x^2 \quad x^3 \ \dots \ x^N \right].
\end{equation}

Eqn. \eqref{eqn-matrix-row-x} has similar form with Eqn. \eqref{eqn-series-power-finite-coefficients}, but the former is function of $x$.

## Polynomial series term
Term of a series in the form of

\begin{equation}
\label{eqn-series-polynomial}
U_x = \sum_{n = 0}^N c_n x^n
\end{equation}

can be defined, so that the term is function of $x$. Since $x$ is normaly used for real number, it will be changed to $i$ in representing integer. Then, \eqref{eqn-series-polynomial} will change to

\begin{equation}
\label{eqn-series-polynomial-integer}
U_i = \sum_{n = 0}^N c_n i^n
\end{equation}

with $i \in \mathbb{Z}$. Let's have an example where $\mathbf{C} = \left[ 1 \quad 1 \right]$ and $i \in \left[0, \ 4 \right]$. Then

1st term: $i = 0$, $U_0 = 1 \cdot 0^0 + 1 \cdot 0^1 = 1$,

2nd term: $i = 1$, $U_0 = 1 \cdot 1^0 + 1 \cdot 1^1 = 2$,

3rd term: $i = 2$, $U_2 = 1 \cdot 2^0 + 1 \cdot 2^1 = 3$,

4th term: $i = 3$, $U_3 = 1 \cdot 3^0 + 1 \cdot 3^1 = 4$,

5th term: $i = 4$, $U_4 = 1 \cdot 4^0 + 1 \cdot 4^1 = 5$,

and the series will be 1, 2, 3, 4, 5.

## Implementation
Using a program via CLI following results

```batch
L:\>iter-series-args-rules 9 -4 1 0 1
# Series of integer polynomial
NTERMS 9
IINDEX -4
COEFFS 1,0,1
SERIES 17,10,5,2,1,2,5,10,17
```

can be obtained, that shows a series of 9 terms start with index -4 (or $i \in \left[-4, \ 4 \right]$) with $\mathbf{C} = [1 \quad 0 \quad 1]$.


## C#
A program with content
```c#
/*
	iter-series-args-rules.cs
	Learn about iteration to produce simple series with args
	consisting rules
	
	Sparisoma Viridi | https://github.com/dudung/butiran
	
	Compile: csc iter-series-args-rules
	Execute: iter-series-args-rules [args]
	
	20200717
	0711 Start this one from iter-series-args code, and use [1].
	0726 Learn array [2].
	0741 Can find error in output, logical one.
	0747 Can produce hopefully right results.
	0750 Add output comment at the end for documentation.
	
	References
	1. url https://docs.microsoft.com/en-us/dotnet/csharp
	   /programming-guide/main-and-command-args/command-line
		 -arguments [20200716].
	2. url https://docs.microsoft.com/en-us/dotnet/csharp
	   /programming-guide/arrays/single-dimensional-arrays
		 [20200717].
*/

using System;

public class IterSeries
{
	public static void Main(string[] args)
	{
		if (args.Length < 3) {
			Console.WriteLine("Usage: iter-series-args [N ii poly]");
			Console.WriteLine("N     number of terms");
			Console.WriteLine("ii    initial index");
			Console.Write("poly  coefficients of a polynomial,");
			Console.WriteLine("e.g. c0 c1 c2 c3 c4 .. for");
			Console.Write("      Un = c0 + c1 n + c2 n^2 + ");
			Console.WriteLine("c3 n^3 + c4 n^4 + c5 n^5 + ..");
		} else {
			Console.WriteLine("# Series of integer polynomial");
			
			int N = int.Parse(args[0]);
			Console.WriteLine("NTERMS " + N);
			
			int ii = int.Parse(args[1]);
			Console.WriteLine("IINDEX " + ii);
			
			int M = args.Length - 2;
			int[] c = new int[M];
			for (int i = 0; i < M; i++) {
				c[i] = int.Parse(args[2 + i]);
			}
			Console.Write("COEFFS ");
			for (int j = 0; j < M; j++) {
				Console.Write(c[j]);
				if (j < M - 1) {
					Console.Write(",");
				}
			}
			Console.WriteLine();
			
			Console.Write("SERIES ");
			for (int i = ii; i < ii + N; i++) {
				int U = 0;
				
				for (int j = 0; j < M; j++) {
					
					int jj = 1;
					for (int k = 0; k < j; k++) {
						jj *= i;
					}
					
					U += c[j] * jj;
				}
				
				Console.Write(U);
				if (i < ii + N - 1) {
					Console.Write(",");
				}
			}
			Console.WriteLine();
		}
	}
}
```

## Note
Spacing in the MathJax equation requires `\quad` as suggested [[2](#ref2)]. Start on 17 Jun, add example on 18 Jun. 


## References
1. <a name="ref1"></a>[Wikipedia (en) 950336490, 11 Apr 2020](https://en.wikipedia.org/w/index.php?oldid=950336490).
2. <a name="ref2"></a>[TEX Stack Exchange 370504, 19 May 2017](https://tex.stackexchange.com/a/370504)


