# Complete Solution of Newton School 51 days of Coding Challenge

If you are new to this challenge, first of all, join [Newton School Official Discord Server](https://bit.ly/3hc9GsX) and get started with it. Awesome prizes are awaiting you. Use this blog as a reference for those who face problems while solving the questions. Don't forget to share it with your peers. 😊

## Question 1: Tell Date

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670916242079/N-TcD-oGp.png align="center")

## Solution:

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

## Solution:

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

## Solution:

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

## Solution:

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

### New Questions are to be updated with a daily streak. Make sure you subscribe to the newsletter to be notified when I am adding more solutions. Thanks for reading 😊. A small sponsor is always appreciated 💝