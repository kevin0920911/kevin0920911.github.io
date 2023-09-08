---
title: "Elgenvalues"
subtitle: "Elgenvalues"
layout: post
author: "Hsu"
published: true
header-style: text
tags:
  - linearalgebra
  - Python
---

# Elgenvalues

Status: Not started

# Eigenvalue and Eigenvector

<aside>
💡 **Def Eigenvalue and Eigenvector**

Let A be an n*n matrix. The scalar $\lambda$ is an eigenvalue of A when there is a nonzero vector x such that $Ax=\lambda x$. The vector is an eigenvector of A corresponding to $\lambda$ . 

![Untitled](Elgenvalues%203fe146aa21944dc39b1ad346e4bfebd3/Untitled.png)

<aside>
📢 **Thm Finding Eigenvalue and Eigenvector of a Matrix**

Let A be an n*n matrix

1. An eigenvalue of A is a scalar $\lambda$  such that $det(\lambda I - A)=0$
2. The eigenvector of A corresponding to $\lambda$ are the nonzero solution of $(\lambda I-A)x=0$

If A is an n*n triangular matrix, then its eigenvalue are the entires on its main diagonal(對角線)

</aside>

<aside>
📢 **Thm Triangular Matrix**

```python
import math
def det(m):
    if len(m)==1:
        return m[0][0]
    else:
        total=f([0])
        for i in range(len(m)):
            n=[ [row[j] for j in range(len(m)) if i!=j]for row in m[1:] ]
            if i%2==0:
                total=total+det(n)*m[0][i]
            else:
                total=total-det(n)*m[0][i]
        return total
class f:
    def __init__(self,A):
        self.A=A
    def __sub__(self,a):
        P=[0]*(max( len(a.A) , len(self.A) ))
        for i in range( len(P) ):
            try:
                P[i]=self.A[i]-a.A[i]
            except:
                try:
                    P[i]=self.A[i]
                except:
                    P[i]=-a.A[i]
        self.popZero(P)
        return f(P)
    def __add__(self,a):
        P=[0]*(max( len(a.A) , len(self.A) ))
        for i in range( len(P) ):
            try:
                P[i]=a.A[i]+self.A[i]
            except:
                try:
                    P[i]=a.A[i]
                except:
                    P[i]=self.A[i]
        self.popZero(P)
        return f(P)
    def __mul__(self,a):
        if type(a.A)==type([]):
            P=[0]*( len(a.A)+len(self.A) )
            for i in range(len(a.A)):
                for j in range(len(self.A)):
                    P[i+j]+=a.A[i]*self.A[j]
            self.popZero(P)
            return f(P)
        else:
            P=[0]*len(self.A)
            for i in range(len(self.A)):
                P[i]=self.A[i]*a
            return f(P)
    def popZero(self,m):
        if m==[]:
            m=[0]
            return 
        while not m[-1]:
            m.pop()
            if m==[]:
                m=[0]
                break 
    def slove(self):
        n=len(self.A)
        if n==3:
            A,B,C=self.A[2],self.A[1],self.A[0]
            x1=(-B+math.sqrt(B**2-4*A*C))/ (2*A)
            x2=(-B-math.sqrt(B**2-4*A*C))/ (2*A)
            return [x1,x2]
        elif n==4: 
            A,B,C,D=self.A[3],self.A[2],self.A[1],self.A[0]
            p =  ( -(B**2) / (3*A**2) ) + (C/A)
            q = ( (2*B**3) / (27*A**3) ) - ((B*C) / (3*A**2)) + (D/A)
            w = complex(-1,3**(1/2)) / 2

            U = (-q / 2) + ( ( ( q / 2 )**2 + ( p / 3 )**3 )**(1/2) )
            V = (-q / 2) - ( ( ( q / 2 )**2 + ( p / 3 )**3 )**(1/2) )

            U =  (U/abs(U))*math.pow(abs(U),1/3)
        
            V =  (V/abs(V))*math.pow(abs(V),1/3)
            

            x1 = U + V - (B/(3*A))
            x2 = U*w + V*w*w - (B/(3*A))
            x3 = U*w*w + V*w - (B/(3*A))

            return [x1,x2,x3]
        elif n==5:
            A,B,C,D,E=self.A[4],self.A[3],self.A[2],self.A[1],self.A[0]

            p1 = 2*C*C*C - 9*B*C*D + 27*A*D*D + 27*B*B*E - 72*A*C*E
            p2 = p1 + ( -4*((C*C - 3*B*D + 12*A*E)**3) + (p1)**2 )**(1/2)
            
            p3 = (C*C - 3*B*D + 12*A*E) / (3*A)*(math.pow(p2,1/3) / 2) + math.pow(p2,1/3) / 2 / (3*A)
            p4 = ( (B*B)/(4*A*A) - (2*C)/(3*A) + p3 )**(1/2)
            p5 = (B*B)/(2*A*A) - (4*C)/(3*A) - p3
            p6 = ( -(B*B*B)/(A*A*A) + (4*B*C)/(A*A) - (8*D)/A ) / (4*p4)

            x1 = - B/(4*A) - p4/2 - ( (p5-p6)**(1/2) ) / 2
            x2 = - B/(4*A) - p4/2 + ( (p5-p6)**(1/2) ) / 2
            x3 = - B/(4*A) + p4/2 - ( (p5+p6)**(1/2) ) / 2
            x4 = - B/(4*A) + p4/2 + ( (p5+p6)**(1/2) ) / 2
            return [x1,x2,x3,x4]
m=[int(i) for i in input().split()]
n=0
while n**2<len(m):n+=1
M=[[f([0])]*n for i in range(n)]
for i in range(len(m)):
    M[int(i/n)][i%n]=M[int(i/n)][i%n]+f([m[i]])
for i in range(n):
    M[i][i]=M[i][i]+f([0,-1])
print(det(M).A)
for i in det(M).slove():
    print(f"{round(i.real,2):.2f}")
```

</aside>

</aside>

# Eigenspaces

<aside>
💡 **Thm Eigenvectors of $\lambda$  Form a subspace**

If A is an n*n matrix with an eigenvalue $\lambda$, then the set of all eigenvectors of  $\lambda$  with zero vector

$$
\{ x:x\space is\space an\space eigenvector\space of\space \lambda  \}
$$

is a subspace of $R^n$. This subspace is eigenspace of $\lambda$. 

</aside>

# Diagonalization

<aside>
💡 **Def Diagonalizable Matrix**

An n*n matrix A is diagonalizable when A is similar to a diagonal matrix.

$$
\exists P,P^{-1} \space A'=P^{-1}AP
$$

<aside>
📢 **Thm Similar Matrice**

Similar Martrix have the same eigenvalue

</aside>

<aside>
📢 **Thm Codition for Diagonalization**

An n*n matrix A is diagonalizable if and only if it has n linearly indeoendent eigenvectors

</aside>

<aside>
📢 **Thm Sufficient Condition for Diagonalization**

If n*n matrix A has n distinct eigenvalues, then the correspnding eigenvectors are linear independent and A is diagonalizable

</aside>

</aside>

<aside>
⚠️ **Step for Diagonalizing**

1. Find n linearly independent eigenvectors $p_1 \space p_2\space p_3 \dots p_n$
2. Let P be n*n matrix: $P=[p_1 \space p_2 \space\dots p_n]$
3. Then get $D=P^{-1}AP$
</aside>

# Stmmetric Matrices and Orthogonal Diagonalization

<aside>
💡 **Def Symmetric Matrix**

A square matrix A is symmetric when $A=A^T$

<aside>
📢 **Thm Properties of Symmetric Matric**

If A is n*n symmetric matrix, then the properties listed below are true

1. A is diagonalizable
2. All eigenvalue of A are real .
3. If $\lambda$  is an eigenvalue of A with **Multiplicity** k, then $\lambda$ has k linearly indepentent eigenvalue. That is, the eigenvalue of $\lambda$ has dimension k
</aside>

</aside>

<aside>
💡 **Def Orthgonal Matrix**

A square P is orthogonal when it is invertible and $P^T=P^{-1}$

**ps 共乘P可得$I=PP^T$**

<aside>
📢 **Thm Properties of Orthgonal Matrix**

An n*n matrix P is Orthogonal **if and only if** its col vector form an **orthornormal** set

</aside>

<aside>
📢 **Thm Property of Symmetric Matrix**

Let A be an n*n symmetric matrix. If $\lambda_1 \& \lambda_2$ are distinct eigenvalue of A, then their corresponding eigenvector $x_1$  and $x_2$ are orthogonal

</aside>

</aside>

<aside>
💡 **How to get Diagonalization of Symmetric Matrix**

1. Find eigenvalue
2. 無重跟: 算出eigenvalue 對應的特徵向量，並單位化
3. 有重跟: 用Gram-Shimmit normalization
4. 將全部的eigenvector 組合成P 可得到 $P^{-1}AP=P^TAP=D$
</aside>