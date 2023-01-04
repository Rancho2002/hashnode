# Complete Solution of Newton School 51 days of Coding Challenge

If you are new to this challenge, first of all, join [Newton School Official Discord Server](https://bit.ly/3hc9GsX) and get started with it. Awesome prizes are awaiting you. Use this blog as a reference for those who face problems while solving the questions. Don't forget to share it with your peers. 😊

### ::Language in this blog::

![python](https://skillicons.dev/icons?i=python align="left")

## Question 1: Tell Date

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670916242079/N-TcD-oGp.png align="center")

***Solution:***

```python
# Your code here
dt=input().split("/")
yr,mon,day=int(dt[0]),int(dt[1]),int(dt[2])

if(yr>=2022):
    if(yr==2022):
        if(mon>=6):
            if(mon==6):
                if(day>=20):
                    print("After")
                else:
                    print("Before")
            else:
                print("After")
        else:
            print("Before")
    else:
        print("After")
else:
    print("Before")
```

## Question 2: Money Money

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670916394025/fnc3_K_QN.png align="center")

***Solution:***

```python
init=0
for i in range(int(input())):
    a=input()
    if(a[-3:]=="JPY"):
        init+=float(a[0:-4])
    
    elif(a[-3:]=="BTC"):
        init+=float(a[0:-4])*380000

print(format(init,".8f"))
```

## Question 3: **Newton Hates Balloons**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670916512215/0IsdN10f-.png align="center")

***Solution:***

```python
import sys
a,b=map(int,input().split())
arr=list(map(int,input().split()))
# print(arr)
if(a==1):
    print(abs(arr[0]))
else:
    h,l,ms=b-1,0,sys.maxsize
    while(h<a): # (number of ballon to burst-1) is less than have ballons
        s=arr[h]-arr[l]
        if(arr[h]<0 and arr[l]<0): s+=abs(arr[h])
        elif(abs(arr[l])>abs(arr[h])): s+=abs(arr[h])
        else: s+=abs(arr[l])
        ms=min(ms,s)
        l+=1
        h+=1
    print(ms)
```

## Question 4: Newton's family

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670934432469/WKdff1eHq.png align="center")

***Solution:***

```python
n=int(input())
l=list(map(int,input().split()))
d ={}
for i in l:
    if i in d :
        d[i] = d[i]+1
     
    else:
        d[i]=1
      

for i in range(1,n+1):
    if i in d:
        pass
    else :
        d[i]=0
        
for i in range(1,n+1):
    print(d[i])
```

## Question 5: Camp

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671001219042/cYnB6xfVp.png align="center")

***Solution:***

```python
# Your code here
a,b=map(int,input().split())
l=list(map(int,input().split()))

rem= a- sum(l)
if(rem<0):
    print(-1)
else:
    print(rem)
```

## Question 6: End Card

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671201723914/XjEIQY0TT.png align="center")

***Solution:***

```python
# Your code here
n,i=map(int,input().split())
print(n-i+1)
```

## Question 7: Newtogon

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671346916754/u20YbuMEl.png align="center")

***Solution:***

```python
# Your code here
a=int(input())
sides=list(map(int,input().split()))
temp=sides.copy()

flag=False
for i in sides:
    temp.remove(i)
    if(i>sum(temp)):
        flag=True
    temp=sides.copy()

if(flag): print("No")
else: print("Yes")
```

## Question 8: Point Dance

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671478429823/EZYEvqxVb.png align="center")

***Solution:***

```python
# Your code here
checkpt, total=map(int,input().split())
cords=list(map(int,input().split()))
cords.sort()
place=0
l=[0]
for i in range(1,total):
    l.append(abs(cords[i-1]-cords[i]))

l.sort()
# print(l)
# print(total-checkpt)
for i in range(total-checkpt+1):
    place+=l[i]
print(place)
```

## Question 9 : Divide It

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671706044136/MtCm4WYrm.png align="center")

***Solution:***

```python
# Your code here
def belongToSame(x,y):
    a=[1 ,3 ,5 ,7 ,8 ,10,12]
    b=[4,6,9,11]
    c=[2]
    if((x in a and y in a)or(x in b and y in b)or(x in c and y in c)):
        print("Yes")
    else:
        print("No")

x,y=map(int,input().split())

belongToSame(x,y)
```

## Question 10: Find Prosum

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671804311776/7417c134-52bf-4742-ba41-dec22cae073d.png align="center")

***Solution:***

```python
# Your code here
n=int(input())
l=list(map(int,input().split()))
tosum=l[n-1]
ans=0
mod=10**9+7

for i in range(n-2,-1,-1):
    ans=(ans+(tosum*l[i]))
    tosum=(tosum+l[i])


print(ans%mod)
```

## Question 11: Letter Game

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672059150168/d2f8301c-ab9f-47de-891c-db91600b8720.png align="center")

***Solution:***

```python
# Your code here
letter=input().strip()
if(len(set(letter))==1): print("Won")
else: print("Lost")
```

## Question 12: Vegetable

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672059278248/9f81730a-d0f8-403b-a606-631b308708da.png align="center")

***Solution:***

```python
# Your code here
def vegetable(dish,vege):
    #checking posibilities
    allChn=dish*2
    allIt=dish*4
    flag=False
    if(vege==allChn or vege==allIt):
        flag=True
    elif(vege>allChn and vege<allIt):
        for i in range(1,dish+1):
            if((4*i+(2*(dish-i)))==vege):
                flag=True
                break
    return flag

dish,vege=map(int,input().split())

flag=vegetable(dish,vege)
print("Yes" if flag else "No")
```

## Question 13: Assign Zero

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672147589202/633f6217-df5d-41de-8acf-f7e105a2c4d7.png align="center")

***Solution:***

```python
# Your code here
def find(arr):
    return arr.index(0)+1

arr=list(map(int,input().split()))
print(find(arr))
```

## Question 14: **Kick Palindrome**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672331943797/5d3ad71b-accc-4f4b-b912-fe662db60ebd.png align="center")

***Solution:***

```python
# Your code here
def minKick(gift):
    count=0
    for i in range(len(gift)//2):
        if(gift[i]!=gift[(len(gift)-1)-i]):
            count+=1
    return count

gift=input()
print(minKick(gift))
```

## Question 15: Newton Gold Magic

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672482581214/5b5b880f-4ae4-4980-b033-d7c2c624e169.png align="center")

***Solution:***

```python
# Your code here
def magic(gold,n):
    gold.sort()
    s=(gold[0]+gold[1])/2
    for i in range(2,n):
        s=s+gold[i]
        s=s/2
    return s
n=int(input())
gold=list(map(int,input().split()))

print(f"{magic(gold,n):.8f}")
```

## Question 16: Stringram

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672831113382/8952146e-2276-4d97-abea-5e76a981eead.png align="center")

***Solution:***

```python
# Your code here
n=int(input())
l={}

for i in range(n):
    s=input()
    m="".join(sorted(s))
    if(m in l):
        l[m]=l[m]+1
    else:
        l[m]=1
count=0
for i in l:
    if(l[i]>1):
        count+=(l[i]*(l[i]-1))/2
print(int(count))
```

### New Questions are to be updated with a daily streak. Make sure you subscribe to the newsletter to be notified when I am adding more solutions. Thanks for reading 😊. A small sponsor is always appreciated 💝