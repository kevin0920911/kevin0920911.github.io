---
title: "Linear Transformations"
subtitle: "Linear Transformations"
layout: post
author: "Hsu"
published: flase
header-style: text
tags:
  - linearalgebra
  - Python
---
<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>



# Image and Preimage


**Domain, Range, Image, Preimage**


**Image:** 經過f映射後的值

**Preimage:** 反函數



# Linear Transformations


**Def Linear Transformations**

Let V and W be vector spaces. The Function

$$
T:V\rightarrow W
$$

is a Linear Transformations of V to W. Then, 

1. $T(u+v)=T(u)+T(v)$
2. $T(cu)=cT(u)$


**Thm Properties of Linear Transformations**

1. $T(0)=0$
2. $T(-v)=-T(v)$
3. $T(u-v)=T(u)-T(v)$
4. $T(c_1v_1+c_2v_2\dots+c_nv_n)=T(c_1v_1)+T(c_2v_2)\dots+T(c_nv_n)$

**Thm Linear Transfirmation Given by a Matrix**

Translate $R^n \rightarrow R^m$  

$$
T(v)=Av
$$

where A is m*n martix, v is n*1 martix , T(v) is m*1 martrix


# Kernel and Range


**Def Kernel of Kinear Transformation**

Let $T: V \rightarrow W$. Then the set of all vectors $v \in V$ satisfy that $**T(v)=0$ is $ker(T)$** 


**Thm Kernel is the Subspace of V**

$ker(T)$ is a subspace of  $V$


**Thm Corollary**

Let $T: R^n \rightarrow R^m$ , and T is $T=Av$

Then The Kernel of T is the solution space of $Ax=0$


**Def Range of Linear Tramsformation**

$T: V\rightarrow W$

$$
range(T)=\{ T(v): v\in V \}
$$


**Thm The Range of T Is a subspace of W**

The range of a linear transformation $T: V \rightarrow W$ is a subspace of W


**Thm Corollary**

Let $T: R^n\rightarrow R^m$    be the linear transformation $T(x)=Ax$. Then the **col space of A is equal to the range(T)**


**Def Rank(T) Nullity(T)**

1. $nullity(T) = dim(ker(T))$
2. $rank(T) = dim(range(T))$

$$
rank(T)+nullity(T)= domain(T)
$$



# One to One & Onto


**Def One to One**

1. **One to One (一對一，傳入傳出唯一):** $ker(T) =\{0\}$ if and only if one to one
2. **Onto (值域用完):**  $rank(T) = dim(W)$  if and only if onto 


**Thm one to one and onto Linear Transformation**

Let $T:V\rightarrow W$  be linear transformation with vector spaces V and W.

1. $dim(V)=dim(W)=n$
2. Then if T is one to one if and only if onto



**Def Isomorphism**

If T is one to one and onto is called **Isomorphism** 


**Thm** **Isomorphism spaces and dimension**

V and W are **Isomorphism** if and only if they are the same of dim



# Martrix for Linear Transformations


**Thm The stanfard Martix of Linear Transformation**

Let $T: R^n \rightarrow R^m$ be a linear transformation such that, for the standrad basis basis vector $e_i$ of  $R^n$

 $T(e_1)=\begin{bmatrix} x_{11} \\
    x_{21} \\ \vdots
  \\
    x_{n1} 
\end{bmatrix}$ $T(e_2)=\begin{bmatrix} x_{12} \\
    x_{22} \\ \vdots
  \\
    x_{m2} 
\end{bmatrix}$$\dots$   $T(e_m)=\begin{bmatrix} x_{1n} \\
    x_{2n} \\ \vdots
  \\
    x_{mn} 
\end{bmatrix}$

 Then, the standard marteix of T is: 

$$
A=\begin{bmatrix} x_{11}&&x_{12} &&\dots && x_{1m}  \\ x_{21}&&x_{22} &&\dots && x_{2m} \\ \vdots &&\vdots &&\ddots && \vdots
  \\ x_{n1}&&x_{n2} &&\dots && x_{nm} 
\end{bmatrix}
$$



# Composition of Linear Transformation


**Def Composition**

$$
T(v)=T_1(T_2(v))
$$


📢 **Thm Composition of Linear Transformation**

1. $T_1(v)=A_1v$
2. $T_2(v)=A_2v$

$$
T(v)=T_1(T_2(v))=A_1A_2v
$$


**Def Inverse of Linear Transformation**

1. $T_2(T_1(v))=v$
2. $T_1(T_2(v))=v$

then $T_1$  is be said inverse of $T_2$ , and $T_1$  is invertible 

**Thm Existence of an Inverse Transformation**

1. T is inveritiblem
2. T is an isomorphism**(one to one + onto)** 
3. A is inverible

Then the standrad matrix of $T^{-1}$ is $A^{-1}$


# Nonstandard Bases and General Vector Spaces

 


**Transformation Matrix for Nonstandard Bases**

Let V and W be fiinite-dim vector spaces with bases $B$$\space to \space$$B'$ where $B=\{ v_1 , v_2 \dots , v_n\}$ 

Then  $T:V \rightarrow W$ is a linear transformation such that

 $[T(v_1)]_{B'}=\begin{bmatrix} x_{11} \\
    x_{21} \\ \vdots
  \\
    x_{n1} 
\end{bmatrix}$ $[T(v_2)]_{B'}=\begin{bmatrix} x_{12} \\
    x_{22} \\ \vdots
  \\
    x_{m2} 
\end{bmatrix}$$\dots$   $[T(v_n)]_{B'}=\begin{bmatrix} x_{1n} \\
    x_{2n} \\ \vdots
  \\
    x_{mn} 
\end{bmatrix}$

then the m*n matrix whose col coorespond to $[T(v_i)]_{B'}$

$$
A=\begin{bmatrix} x_{11}&&x_{12} &&\dots && x_{1m}  \\ x_{21}&&x_{22} &&\dots && x_{2m} \\ \vdots &&\vdots &&\ddots && \vdots
  \\ x_{n1}&&x_{n2} &&\dots && x_{nm} 
\end{bmatrix}
$$

is such that $[T(v)]_{B'}=A[v]_{B}$



# Transition Matrix


💡 **Transition Matrix**





# Similar Matrix


**Def Similar Matrix**

1. Square Matrix $A$  and $A'$
2. Exist an inverible martix P st $A'=P^{-1}AP$

$A$ is be say that similar to $A'$




**Thm Properties of Similar Marix**

1. A is similar to A
2. A is simialr to B, B is similar to A
3. A is simialr to B, B is similar to C, A is similar to C
