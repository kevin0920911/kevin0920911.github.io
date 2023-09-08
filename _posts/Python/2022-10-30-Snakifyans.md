---
title: "Snakify"
subtitle: "All answers of Snakify"
layout: post
author: "Hsu"
published: true
header-style: text
tags:
  - Python
  - pythonLearing
---
# Snakify
[SNAKIFY](https://snakify.org/en/)
## CHAPTER 1
### Sum of three numbers
```python
a = int(input())
b = int(input())
c = int(input())
print(a + b + c)
```
>**後記:** input()出來是字串，要轉形

### Hi John
```python
a=input()
print("Hi ",a)
```
> **後記:** Python的print預設是間隔一空白(如果要改預設可用sep 或+ 處理)，並換行

### Square
```python
a= int(input())
print(a*a)
```
### Area of right-angled triangle
```python
b = int(input())
h = int(input())
print ( b*h/2 )
```
> **後記:** Python這樣出來可以是float，不須管形別轉換，但C++要注意會不會強制轉換

### Hello, Harry!
```python
name = input()
print("Hello",name,"!",sep='')
```
>**後記:** 2行可改成 `print('Hello, ' + input() + '!')`

### Apple sharing
```python
n = int(input())
K = int(input())
print(K//n)
print(K%n)
```
>**後記:** `//`是整除

### Previous and next
```python
a= int(input())
print("The next number for the number",a,"is",a+1)
print("The previous number for the number",a,"is",a-1)
```
### Two timestamps
```python
a=int(input())
b=int(input())
c=int(input())
d=int(input())
e=int(input())
f=int(input())
print((d-a)*60*60+(e-b)*60+(f-c))
```
### School desks
```python
import math
sum=0
for i in range(3):
    a=int(input())
    a=math.ceil(a/2) 
    sum=a+sum
print(sum)
```
## CHAPTER 2
### Last digit of integer
```python
a=int(input())
print(a%10)
```
### Tens digit
```python
print(int(int(input())/10)%10)
```
### Sum of digits
#### 正常解法
```python
a= int(input())
frist=int(a/100)
second=int((a-frist*100)/10)
third=a%10
print(frist+second+third)
```
#### 字串解
```python
a=input()
sum=0
for i in a:
    sum+=ord(i)-48
print(sum)
```
#### 一行流
```python
print(sum([ord(i)-48 for i in input()]))
```
> **後記:** 可再延伸UVA題目: 10019 - Funny Encryption Method

### Fractional part
#### 理想的解法
```python
a=float(input())
b=int (a)
print(a-b)
```
#### 實際解法
```python
a=input().split(".")
if (len(a)==2):
    print('0.'+a[1])
else:
    print(0)
```
>**後記:** Float不精確，要用字串處理才能得到標準答案

### First digit after decimal point
#### 正常解法
```python
a=float(input())
b=float(int(a))
c=float((a-b)*10)
d=int(c)
print(d)
```
#### 字串處理
```python
a=input()
if( a.find(".")==-1 ):
    print(0)
else:
    print(a[a.find(".")+1])
```
#### 精簡化
```python
a=input()
print( (a[a.find(".")+1],0) [a.find(".")==-1] )
```
### Car route
```python
N=int(input())
M=int(input())
Day=M//N
if (M%N>0):
    Day=Day+1
print(Day)
```
#### Snakify 解答
```python
import math
N=int(input())
M=int(input())
print(math.ceil(M/N))
```
### Digital clock
```python
a=int(input())
print(a//60,a%60)
```
### Total cost
```python
A=int(input())
B=int(input())
N=int(input())
dollar=(A*100+B)*N
print(dollar//100,dollar%100)
```
>**後記:** Float不精確，改用int方式解

### Clock face - 1
```python
H=int(input())
M=int(input())
S=int(input())
angle=float(H*30+M/2+S/120)
print(angle)
```
### Clock face - 2
```python
degree=float(input())
print(degree*12%360)
```
> **後記:** hour hand: min hand = 1 : 12

## CHAPTER 3
### Minimum of two numbers
```python
a=int(input())
b=int(input())
if (a>b):
    print(b)
else:
    print(a)
```
#### 簡化
```python
a=int(input())
b=int(input())
print((a,b)[a>b])
```
### Sign function
```python
a=int(input())
if(a>0):
    print(1)
elif (a<0):
    print(-1)
else:
    print(0)
```
### Minimum of three numbers
```python
A=[0,0,0]
A[0]=int(input())
A[1]=int(input())
A[2]=int(input())
for i in range(2):
    if (A[i+1]>A[i]):
        tmp=A[i]
        A[i]=A[i+1]
        A[i+1]=tmp
print(A[2])
```
> **後記:** Python 數值交換可以改成a,b=b,a，以元組形式

### Equal numbers
```python
a=int(input())
b=int(input())
c=int(input())
if (a==b):
    if (b==c):
        print(3)
    else:
        print(2)
elif (b==c):
    if (a==b):
        print(3)
    else:
        print(2)
elif (c==a):
    if (a==b):
        print(3)
    else:
        print(2)
else:
    print(0)
```
### Rook move
```python
A=[0,0,0,0]
for i in range(4):
    A[i]=int(input())
if (A[0]==A[2]):
    print("YES")
elif (A[1]==A[3]):
    print("YES")
else:
    print("NO")
```
### Chess board - same color
```python
A=[0,0,0,0]
for i in range(4):
    A[i]=int(input())
if ((A[0]+A[1])%2 == (A[2]+A[3])%2):
    print("YES")
else:
    print("NO")
```
>**思路:** 同顏色 $x+y$  奇數(偶數)

### King move
```python
A=[0,0,0,0]
for i in range(4):
    A[i]=int(input())
if (abs(A[0]-A[2])<=1 and abs(A[1]-A[3])<=1):
    print("YES")
else:
    print("NO")
```
> **後記:** Python可以使用類似數學區間的表達式(-1<=A[0]-A[2]<=1)但C++不行，請注意

### Bishop moves
```python
A=[0,0,0,0]
for i in range(4):
    A[i]=int(input())
if (abs(A[0]-A[2]) == abs(A[1]-A[3])):
    print("YES")
else:
    print("NO")
```
>**後記:** `abs()`是取絕對值

### Queen move
```python
A=[0,0,0,0]
for i in range(4):
    A[i]=int(input())
if (abs(A[0]-A[2]) == abs(A[1]-A[3])): #斜向移動
    print("YES")
elif (A[0]==A[2]):  #水平移動
    print("YES")
elif (A[1]==A[3]):  #鉛直移動
    print("YES")
else:
    print("NO")
```
### Knight move
```python
A=[0,0,0,0]
for i in range(4):
    A[i]=int(input())
a=abs(A[0]-A[2])
b=abs(A[1]-A[3])
if (a==2 and b==1):
    print("YES")
elif (a==1 and b==2):
    print("YES")
else :
    print("NO")
```
### Chocolate bar
```python
n=int(input())
m=int(input())
k=int(input())
if ((k%n==0 or k%m==0) and m*n>=k):
    print("YES")
else:
    print("NO")
```
> **後記:** 這題多考慮兩種情況
>      1.長或寬可以整除所求
>      2.面積大於所求

### Leap year
```python
year=int(input())
if (year%4==0 and year%100!=0):
    print("LEAP")
elif (year%400==0):
    print("LEAP")
else:
    print("COMMON")
```
## CHAPTER 4

### Series - 1
```python
a=int(input())
b=int(input())
for i in range (a,b+1):
    print(i)
```
### Series - 2
```python
a=int(input())
b=int(input())
if (b>=a):
    for i in range(a,b+1):
        print (i)
elif (a>b):
    for i in range(a,b-1,-1):
        print(i)
```
### Sum of ten numbers
```python
sum=0
for i in range(10):
    a=int(input())
    sum=sum+a
print(sum)
```
### Sum of N numbers
```python
N=int(input())
sum=0
for i in range(N):
    a=int(input())
    sum=sum+a
print(sum)
```

### Sum of cubes
#### 正常作法
```python
N=int(input())
sum=0
for i in range(N+1):
    sum=sum+(i**3)
print(sum)
```
#### 一行流
```python
print(sum(map(lambda x:x**3,range(1,int(input())+1))))
```
> **思路**: 用range()產生list並用map執行迭代，並回傳陣列給sum()並印出總和

### Factorial
#### 正常做法
```python
a=int(input())
b=a
mul=1
for i in range (b):
   mul=mul*a
   a=a-1
print(mul)
```
#### 遞迴演算法
```python
f=lambda x: 1 if x==1 else x*f(x-1)
print( f(int(input())) )
```
### The number of zeros
```python
sum=0
N=int(input())
for i in range(N):
   a=int(input())
   if (a==0):
       sum=sum+1
print(sum)
```
### Adding factorials
#### 正常作法
```python
N=int(input())
sum=0
for i in range(1,N+1,1):
    mul=1 
    for g in range (1,i+1,1):
        mul=mul*g
    sum=sum+mul
print(sum)
```
#### 一層迴圈做法
```python
N=int(input())
sum=0
mul=1 
for i in range(1,N+1,1):
    mul=mul*i
    sum=sum+mul
print(sum)
```
#### 遞迴演算法與Sum of Club應用
```python
f=lambda x: 1 if x==1 else x*f(x-1)
print(sum([f(int(i)) for i in range(1,int(input())+1)]))
```
### Ladder
#### 正常作法
```python
N=int(input())
for i in range(1,N+1,1):
    for g in range(1,i+1,1):
        print(g,end="")
    print()
```
#### 一行流
```python
for i in range(1,int(input())+1):print("".join([str(j) for j in range(1,i+1)]))
```
> **思路:** 正常解法簡化即可
> **後記:** `join` 只能用`char`,`int`不行
### Lost card
#### 標記解法
```python
N=int(input())
A=[i for i in range(1,N+1)]
for i in range(N-1):
    A.remove(int(input()))
print( A[0] )
```
#### 特殊解
```python
N=int(input())
sum=0
for i in range (1,N):
    sum+=int(input())
print(int(N*(1+N)/2-sum))
```
## CHAPTER 5
### The number of words
```python
s=input()
print(s[2])
print(s[len(s)-2])
print(s[0:5])
print(s[0:len(s)-2])
print(s[0:len(s):2])
print(s[1:len(s):2])
print(s[-1:-(len(s)+1):-1])
print(s[-1:-(len(s)+1):-2])
print(len(s))
```
### The number of words
```python
a=input().split(" ")
print(len(a))
```
### The two halves
#### Slice
```python
a=input()
print(a[(len(a)+1)//2:]+a[:(len(a)+1)//2])
```
#### 我的解法
```python
a=input()
a=list(a)
if (len(a)%2==0):
    for i in range(int(len(a)/2),len(a),1):
        print(a[i],end="")
    for i in range(0,int(len(a)/2),1):
        print(a[i],end="")
else:
    for i in range(int(len(a)/2)+1,len(a),1):
        print(a[i],end="")
    for i in range(0,int(len(a)/2)+1,1):
        print(a[i],end="") 
```

### To swap the two words
```python
s=input().split(" ")
for i in range(len(s)-1,-1,-1):
    print(s[i],end=" ")
```
### The first and last occurrence

```python
s=input()
address=[]
for i in range(0,len(s),1):
    if (s[i]=='f'):
        address.append(i)
if (len(address)==1):
    print(address[0])
elif(len(address)==0):
    pass
else:
    print(address[0],address[len(address)-1])
```
### The second occurrence
```python
s=input()
address=[]
for i in range(0,len(s),1):
    if (s[i]=='f'):
        address.append(i)
if (len(address)==1):
    print(-1)
elif(len(address)==0):
    print(-2)
else:
    print(address[1])
```
### Remove the fragment
#### find()
```python
s=input()
print(s[ :s.find('h') ]+s[ s.rfind('h')+1: ] )
```
#### 儲存成陣列
```python
s=input()
b=[]
for i in range(0,len(s),1):
    if (s[i]=='h'):
        b.append(i)

print(s[0:b[0]]+s[b[len(b)-1]+1: ])
```
### Reverse the fragment
```python
s=input()
b=[]
for i in range(0,len(s),1):
    if (s[i]=='h'):
        b.append(i)

print(s[0:b[0]]+s[b[len(b)-1]-len(s):b[0]-len(s):-1]+s[b[len(b)-1]: ])
```
### Replace the substring
```python
s=input()
for i in s:
    if (i=='1'):
        print("one",end="")
    else:
        print(i,end="")
```
### Delete a character
#### Snakify 作法
```python
print(input().replace('@',''))
```
#### 我的解法
```python
s=input()
for i in s:
    if (i=='@'):
        pass
    else:
        print(i,end="")
```
### Replace within the fragment
#### 用find()
```python
s=input()
l,r=(s.find('h'),s.rfind('h'))
for i in range(len(s)):
    if (s[i]=='h'):
        if(i!=l and i!=r):
            print('H',sep='',end='')
        else:
            print('h',sep='',end='')
    else:
        print(s[i],sep='',end='')
```
#### 用count()
```python
s=input()
count=0
h=s.count('h')
for i in s:
    if (i=='h'):
        if (count==0):
            count+=1
            print(i,end="")
            continue
        elif (count==h-1):
            count+=1
            print(i,end="")
            continue
        print("H",end="")
        count+=1
    else:
        print(i,end="")
```
> **思路:** 第一個h和最後一個h不能改，可以用判斷第幾個h的方式執行，再者碰到第一個與最後一個h以continue的方式跳過

### Delete every third character
```python
s=input()
for i in range(0,len(s),1):
    if (i%3==0):
        pass
    else:
        print(s[i],end="")
```
## CHAPTER 6
:::success
**while迴圈**
1. 用在不確定次數的時候
2. 裡面條件是TURE(1)會執行
:::
### List of squares

```python
a=int(input())
i=1
while (a>=i**2):
    print(i**2)
    i=i+1
```
### Least divisor
```python
n=int(input())
i=2
while(n%i!=0):
    i=i+1
print(i)
```
### The power of two
```python
n=int(input())
i=0
x=1
while (n>x):
    x=x*2
    i=i+1
    if(x*2>n):
        break
print(i,x)
```
### Morning jog

```python
x=int(input())
y=int(input())
Day=1
while(x < y):
    x=x*1.1
    Day=Day+1
print(Day)
```
### The length of the sequence
```python
i=0
a=int(input())
while(a!=0):
    a=int(input())
    i+=1
print(i)
```
### The sum of the sequence
```python
a=int(input())
sum=0
while(a!=0):
    sum=a+sum
    a=int(input())
print(sum)
```
### The average of the sequence
```python
count=0
a=int(input())
sum=0
while(a!=0):
    sum=sum+a
    a=int(input())
    count=count+1
print(sum/count)
```
### The maximum of the sequence
```python
a=int(input())
max=a
while(a!=0):
    if(a>max):
        max=a
    a=int(input())
print(max)
```
### The index of the maximum of a sequence
```python
address=1
max_address=1
a=int(input())
max=a
while(a!=0):
    if(a>max):
        max=a
        max_address=address
    a=int(input())
    address+=1
print(max_address)
```
> **後記:** 類似於氣泡排序

### The number of even elements of the sequence
```python
a=int(input())
count=0
while(a!=0):
    if (a%2==0):
        count+=1
    a=int(input())
print(count)
```
### The number of elements that are greater than the previous one
```python
a=int(input())
tmp=a
count=0
while(a!=0):
    a=int(input())
    if (a>tmp):
        count+=1
    tmp=a
print(count)
```
### The second maximum
#### Snakify解法(以兩變數實現)
```python
first_max = int(input())
second_max = int(input())
if first_max < second_max:
    first_max, second_max = second_max, first_max
element = int(input())
while element != 0:
    if element > first_max:
        second_max, first_max = first_max, element
    elif element > second_max:
        second_max = element
    element = int(input())
print(second_max)
```
#### 本人解法(list實現)
```python
n=int(input())
b=[]
while(n!=0):
    b.append(n)
    n=int(input())
b.sort()
print(b[len(b)-2])
```
### The number of elements equal to the maximum
```python
n=int(input())
b=[]
while(n!=0):
    b.append(n)
    n=int(input())
max_=max(b)
count=0
for i in b:
    if (max_==i):
        count+=1
print(count)
```
### Fibonacci numbers
```python
n=int(input())
b=[0,1]
for i in range(1,n+1,1):
    b.append(b[i]+b[i-1])

print(b[len(b)-2])
```
### The index of a Fibonacci number
#### Snakify作法(無unfind問題)
```python
a = int(input())
if a == 0:
    print(0)
else:
    fib_prev, fib_next = 0, 1
    n = 1
    while fib_next <= a:
        if fib_next == a:
            print(n)
            break
        fib_prev, fib_next = fib_next, fib_prev + fib_next
        n += 1
    else:
        print(-1)
```
#### 本人作法(有unfind問題)
```python
b=[0,1]
for i in range(1,100,1):
    b.append(b[i]+b[i-1])
f=int(input())
flag=0
for i in range(0,100,1):
    if (b[i]==f):
        print(i)
        flag=1
        break
if (flag==0):
    print(-1)
```
> **後記:** 看完解答才想到可以用兩變數(fib1,fib2)的方式實現，既不會浪費太多記憶體也不會浪費太多時間

### The maximum number of consecutive equal elements
```python
n=int(input())
pre=0
count=1
max_count=1
while n!=0:
    if n==pre:
        count+=1
        max_count=max(max_count,count)
    else:
        count=1
    pre=n
    n=int(input())
print(max_count)
```
>**思路:** 用count的方式跟最大數到的數字比，若比較大則取代之

##  CHPTER 7
:::success
**List**
1.單行輸入用列表生成式實現`[ int(i) for i in input().split()]`
2.多行輸入用append實現
3.切片技巧很方便
:::
### Even indices
#### 正常解
```python
a=input().split(" ")
for i in range(0,len(a),2):
    print(a[i],end=" ")
```
#### 一行流
```python
print(" ".join([i for i in input().split(' ')][0::2]))
```
### Even elements
```python
a=[ int(i) for i in input().split()]
for i in a:
    if (i%2==0):
        print( i , end=' ')
```
> **後記:** 列表生成式很好用 `[ int(i) for i in input().split()]` 可以直接生成一個列表

### Greater than previous
```python
a=[int(e) for e in input().split()]
i=0
for _ in a:
    if (i >= 1):
            if (a[i]>a[i-1]):
                print(a[i] ,end=" ")
    i=i+1
```
### Neighbors of the same sign
```python
a = [int(i) for i in input().split()]
for i in range(1,len(a),1):
    if (a[i]*a[i-1]>0):
        print(a[i-1],a[i],sep=" ",end=" ")
        break
```
### Greater than neighbours
```python
a = [int(i) for i in input().split()]
flag=0
for i in range(1,len(a)-1,1):
    if (a[i]>a[i-1] and a[i]>a[i+1]):
        flag+=1
print(flag)
```
### The largest element

```python
a = [int(g) for g in input().split()]
max_ = a[0]
address = 0
for i in range(1,len(a),1):
    if (a[i]>max_):
        address = i
        max_ = a[i]

print(max_ , address)
```
### The number of distinct elements
```python
a=[i for i in input().split()]
count=0
for i in range (1,len(a),1):
    if (a[i]!=a[i-1]):
        count+=1
print(count+1)
```
### Swap neighbours
```python
a=[i for i in input().split()]
for i in range(0,len(a),2):
    if (len(a)%2!=0):
        if (i==len(a)-1):
            break
        tmp=a[i+1]
        a[i+1]=a[i]
        a[i]=tmp
    
    else:
        tmp=a[i+1]
        a[i+1]=a[i]
        a[i]=tmp
for i in range(0,len(a),1):
    print(a[i],end=' ')
```
### Swap min and max
```python
a=[int(e) for e in input().split()]
b=a.index(max(a))
c=a.index(min(a))
a[b],a[c]=a[c],a[b]


for i in a:
    print(i,end=" ")
```
### The number of pairs of equal

```python
a=[int(i) for i in input().split()]
count=0
for i in range (0,len(a),1):
    for j in range(i+1,len(a),1):
        if (a[i]==a[j]):
            count+=1
print(count)
```
### Unique elements
```python
a=[int(i) for i in input().split()]
flag=0
for i in range(0,len(a),1):
    for j in range(0,len(a),1):
        if (i != j):
            if (a[i]==a[j]):
                flag=1
    if (flag==0):
        print(a[i],end=" ")
    flag=0
```
### Queens
```python
a=[]
for i in range(8):
    row_list=[int(g) for g in input().split()]
    a.append(row_list)
flag=0
for i in range(8):
    for g in range(8):
        if(i==g):
            break
        elif ((abs(a[i][0]-a[g][0]))==(abs(a[i][1]-a[g][1]))):
            flag=1
        elif (a[i][0]==a[g][0]):
            flag=1
        elif (a[i][1]==a[g][1]):
            flag=1
if (flag==1):
    print("YES")
else:
    print("NO")
```
> **後記:** 個人認為本章最困難的一題，有偷偷用二維陣列實現，但也是可以用一維處理 

### The bowling alley
```python
N,K=map(int,input().split())
a=[]
for i in range(K):
    row_array=[int(g) for g in input().split()]
    a.append(row_array)
    
pin=[1]*N
for i in range(K):
    for j in range(a[i][0]-1,a[i][1],1):
        pin[j]=0
for i in range(N):
    if (pin[i]==0):
        print(".",sep="",end="")
    elif (pin[i]==1):
        print("I",sep="",end="")
```
> 後記: 用bool的想法似乎又再多浪費時間，直接用.和I還比較快

## CHAPTER 8
### The length of the segment
```python
import math

def distance(a,b):
    dis=math.sqrt(a**2+b**2)
    return dis

x1=float(input())
y1=float(input())
x2=float(input())
y2=float(input())
print(distance(abs(x2-x1),abs(y2-y1)))
 
```
### Negative exponent
```python
def power(a,b):
    return a**b
print(power(float(input()),float(input())))
```
### Uppercase
```python
def capitalize(a):
    return chr(ord(a)-32)
a=input()
for i in range(0,len(a),1):
    if(a[i-1]==' '):
        print(capitalize(a[i]),end="")
    elif (i==0):
        print(capitalize(a[i]),end="")
    else:
        print(a[i],end="")
```
>後記: ASCII表大寫小寫差32(小寫比較大)

:::warning
**以下開始是遞迴**
:::
### Exponentiation
```python
def f(x,y):
    if(y==1):
        return x
    elif (y==0):
        return 1
    else:
        return f(x,y-1)*x
x=float(input())
y=float(input())
print(f(x,y))
```
### Reverse the sequence
```python
def f():
    a=int(input())
    if (a!=0):
        f()
    # Isn't 0 it will keep input
    print(a)
    # when a=0 it will print
f()
```
### Fibonacci numbers
```python
def fib(n):
    if (n==1):
        return 1
    elif (n==0):
        return 0
    return fib(n-1)+fib(n-2)
n=int(input())
print(fib(n))
```
## CHAPTER 9
### Maximum
```python
#Initialized & Input
a=[]
row,col=map(int,input().split())
for i in range(row):
    c=[int(i) for i in input().split()]
    a.append(c)
    
#Processing
max_=a[0][0]
address_x,address_y=0,0
for i in range(row):
    for j in range(col):
        if (a[i][j]>max_):
            max_=a[i][j]
            address_x,address_y=i,j
            
#Print
print(address_x,address_y)
```
### Snowflake
```python
#Initialized & Input
N=int(input())
a=[['.']*N for i in range(N)]

#Processing the list
for i in range(N):
    for j in range(N):
        if ( i==(N-1)/2 or j==(N-1)/2 ):
            a[i][j] = "*"
        elif (i == j):
            a[i][j] = "*"
        elif (i+j==(N-1)):
            a[i][j] = "*"
            
#Print
for i in range(N):
    for j in range(N):
            print(a[i][j],end=" ",sep=" ")
    print()
```
### Chess board
```python
#Initialized & Input
row,col=[int(i) for i in input().split()]
a=[["."]*col for i in range(row)]

#Processing the list
for i in range(row):
    for j in range(col):
        if (i%2==1):
            if (j%2==0):
                a[i][j] = "*"
        elif (i%2==0):
            if (j%2==1):
                a[i][j] = "*"
                
#Print
for i in range(row):
    for j in range(col):
        print(a[i][j],end=" ",sep=" ")
    print()
```
> 注意: line 3 `[["."]*col for i in range(row)]` 不能寫成`[["."]*col]*row`此種寫法的指標會和row=0時相同(原因是Python =和C++ = 概念不同)

### The diagonal parallel to the main
```python
n = int(input())
for i in range(n):
    for j in range(-i,n-i,1):
        print (abs(j),end=" ",sep=" ")
    print()
```
### Side diagonal
```python
n=int(input())
a=[[0]*n for i in range(n)]
for i in range(n):
    for j in range(n):
        if (i+j==n-1):
            a[i][j]=1
        elif (i+j>n-1):
            a[i][j]=2
for i in range(n):
    for j in range(n):
        print(a[i][j],sep=" ",end=" ")
    print()
    
```
### Swap the columns
```python
row,col=map(int,input().split())
a=[]
for i in range(row):
    a.append([int(j) for j in input().split()])
change1,change2=map(int,input().split())
for i in range(row):
    tmp=a[i][change2]
    a[i][change2]=a[i][change1]
    a[i][change1]=tmp
for i in range(row):
    for j in range(col):
        print(a[i][j],sep=" ",end=" ")
    print()
```
### Scale a matrix
```python
row,col=map(int,input().split())
a=[]
for i in range(row):
    a.append([int(i) for i in input().split()])
product=int(input())
for i in range(row):
    for j in range(col):
        a[i][j]=a[i][j]*product
        print(a[i][j],end=" ",sep=" ")
    print()
```
### Multiply two matrices
```python
m,n,r=map(int,input().split())
A=[]
B=[]
for i in range(m):
    A.append([int(j) for j in input().split()])
for i in range(n):
    B.append([int(j) for j in input().split()])
C=[[0]*r for i in range(m)]
for j in range(m):
    for g in range(r):
        for i in range(n):
            C[j][g]=C[j][g]+A[j][i]*B[i][g]
for i in range(m):
    for g in range(r):
        print(C[i][g],end=" ")
    print()
```
## CHAPTER 10
### The number of distinct numbers
```python
A={int(i) for i in input().split()}
max_=max(A)
count=0
for i in range(max_+1):
    if (i in A):
        count+=1
print(count)
```
### The number of equal numbers
```python
print(len(set(input().split()).intersection(set(input().split()))))
```
### The intersection of sets
```python
print(" ".join(sorted(set(input().split()).intersection(set(input().split())))))
```
### Has the number been encountered before
```python
A=[int(i) for i in input().split()]
for i in range(len(A)):
    if A[i] in A[0:i]:
        print("YES")
    else:
        print("NO")
```
### Cubes
```python
M,N=map(int,input().split())
Alice=set()
Bod=set()
for i in range(M):
    Alice.add(input())
for i in range(N):
    Bod.add(input())
print(len(Alice&Bod))
print("\n".join(sorted(Alice&Bod)))
print(len(Alice-Bod))
print("\n".join(sorted(Alice-Bod,key=lambda x:int(x))))
print(len(Bod-Alice))
print("\n".join(sorted(Bod-Alice)))
```
### The number of distinct words in some text
```python
n=int(input())
sets=set()
for i in range(n):
    line=input().split()
    for j in line:
        if j not in sets:
            sets.add(j)
print(len(sets))
```
### Guess the number
```python
all_={int(i) for i in range(1,int(input()))}
possible=all_
while True:
    guess=input()
    if guess=="HELP":
        break
    guess={int(i) for i in guess.split()}
    ans=input()
    if ans=="YES":
        possible &= guess
    elif ans=="NO":
        possible &= (all_-guess)
print(" ".join([str(i) for i in possible]))
```
### Polyglots
```python
n=int(input())
language=[]
for i in range(int(input())):
    language.append(input())
general=set(language)
all_=set(language)
for i in range(n-1):
    language=[]
    for j in range(int(input())):
        language.append(input())
    general&=set(language)
    all_|=set(language)

general=sorted(list(general),key= lambda x:ord(x[0]))
all_=sorted(list(all_),key = lambda x:ord(x[0]))
print(len(general))
for i in general:
    print(i)
print(len(all_))
for i in all_:
    print(i)
```
## CHAPTER 11
### Number of occurrences
```python
a=input().split()
dic=dict()
for i in a:
    if i not in dic:
        print(0,end=" ")
        dic[i]=1
    
    else:
        print(dic[i],end=" ")
        dic[i]+=1

```
### Dictionary of synonyms
```python
n=int(input())
dic=dict()
for i in range(n):
    a=[j for j in input().split()]
    dic[a[0]]=a[1]

word=input()
if word in dic:
    print(dic[word])
else:
    new_dic={v:k for k,v in dic.items()}
    print(new_dic[word])
```
### Elections in the USA
```python
n=int(input())
dic={}
for i in range(n):
    a=[i for i in input().split()]
    a[1]=int(a[1])
    if a[0] not in dic:
        dic[a[0]]=a[1]
    elif a[0] in dic:
        dic[a[0]]+=a[1]
new_dic=sorted(dic.items(),key= lambda x:(ord(x[0][0])))
for k,v in new_dic:
    print(k,v)
```
### The most frequent word
```python
n=int(input())
dic=dict()
for i in range(n):
    a=input().split()
    for j in a:
        if j not in dic:
            dic[j]=1
        else:
            dic[j]+=1
new=sorted(dic.items(),key= lambda x:(x[1],-ord(x[0][0])),reverse=True)
print(new[0][0])
```
### Access rights
```python
n=int(input())
access={}
for i in range(n):
    program=input().split()
    access[program[0]]=program[1:len(program)]

m=int(input())
for i in range(m):
    program=input().split()
    if "W" in access[program[1]] and program[0]=="write":
        print("OK")
    elif "R" in access[program[1]] and program[0]=="read":
        print("OK")
    elif "X" in access[program[1]] and program[0]=="execute":
        print("OK")
    else:
        print("Access denied")
```
### Countries and cities
```python
n=int(input())
dic={}
for i in range(n):
    cities=input().split()
    for city in cities[1:]:
        dic[city]=cities[0]

m=int(input())
for i in range(m):
    location=input()
    print(dic[location])

```
### Frequency analysis
```python
n=int(input())
dic={}
for i in range(n):
    line=input().split()
    for j in line:
        if j not in dic:
            dic[j]=1
        else:
            dic[j]+=1
new=[(-j,i) for (i,j) in dic.items()]
new=sorted(new)
for i,j in new:
    print(j)
```
### English-Latin dictionary
```python
dic={}
for i in range(int(input())):
    line=input().split(" - ")
    latin=line[1].split(", ")
    for i in latin:
        if i in dic:
            dic[i].append(line[0])
        else:
            dic[i]=[line[0]]
print(len(dic))
for i in sorted(dic):
    print(i,"-",", ".join(dic[i]))
```