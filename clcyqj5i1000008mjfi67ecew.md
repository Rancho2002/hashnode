# day-to-day solution of 30 days of code

Hey tech enthusiasts, 🤟

We are thrilled to announce the launch of the 30 Days of Code challenge. With 20+ Community for Keeping your vision up.. starting from 16 jan till 14 Feb!

Communities coming together!! • 30 coding challenges, each with a unique theme i.e. Problem Of The Day!. • Sessions between the challenge for swag and extra points.

The challenge is open to all skill levels, so whether you are a beginner just starting out in coding or a more experienced programmer, you can join the challenge and work your way up.

So what are you waiting for? • Active participants will receive swags such as T-Shirts, Bottles and many more. 😍 • Certificate for everyone!! ✨

### Language used

![python](https://skillicons.dev/icons?i=python align="left")

## Day 1 : Mall and Coupons

> Newton went to a mall. There are N items in a shop. For each i=1, 2, …, N, the price of the i- th item is Ai Rs. Newton has K coupons. Each coupon can be used on one item. You can use any number of coupons, possibly zero, on the same item. Using `k` coupons on an item with a price of `a` Rs allows him to buy it for `max{a−kX, 0}` Rs.  
> Print the minimum amount of money Newton needs to buy all the items.
> 
> More info: [https://my.newtonschool.co/playground/code/56rnswcwem6q](https://my.newtonschool.co/playground/code/56rnswcwem6q)

***Solution:***

```python
from typing import List

def main():
    # Your code here
    N, K, X = map(int, input().split())
    arr = list(map(int,input().split()))
    
    arr.sort(reverse=True)
    for i in range(N):
        req = arr[i] // X
        if req <= K:
            arr[i] = arr[i] % X
            K -= req
        else:
            if K == 0:
                break
            else:
                arr[i] = arr[i] - (K * X)
                K = 0
    arr.sort(reverse=True)
    ans = 0
    for i in range(K, N):
        ans += arr[i]
    print(ans)

if __name__ == "__main__":
    main()
```

## Day 2: Friends Or Not?!

> **Problem Statement**
> 
> The students of Newton School threw a grand party to celebrate their hard work and achievements. They danced and sang the night away, enjoying delicious food and creating memories that would last a lifetime.  
> There are N guests in the party and N-1 relationships are given. The guests are numbered 1, 2,. , N. The i- th relationship depicts that guest ai and guest bi are friends.  
> Determine whether a guest exists or not who is a friend of all other guests.  
> Here, we only consider the direct friendship
> 
> More info : [https://my.newtonschool.co/playground/code/w6g62sucd655](https://my.newtonschool.co/playground/code/w6g62sucd655)

***Solution:***

```python
n = int(input())
x, y = 0, 0
mp = {}
for i in range(n-1):
    x, y = map(int, input().split())
    mp[x] = mp.get(x, 0) + 1
    mp[y] = mp.get(y, 0) + 1

for key, value in mp.items():
    if value == n-1:
        print("Yes")
        exit(0)
print("No")
# print(mp)
```

## Day 3: Edward and Maths Competition

> Edward participated in one maths competition. He was asked to find the number of ways to choose a pair of an even number and an odd number from the positive integers between 1 and N (inclusive). The order does not matter.
> 
> More info : [https://my.newtonschool.co/playground/code/vso6otmi5nv7](https://my.newtonschool.co/playground/code/vso6otmi5nv7)

***Solution:***

```python
# Your code here
n=int(input())

if(n%2!=0):
    a1=n//2
    a2=(n+1)//2
else:
    a1=(n+1)//2
    a2=n//2

print(a1*a2)
```

## Day 4: Even Numbers - 2

> Newton loves EVEN numbers.
> 
> You are given two integers N and M. Generate 5 unique even numbers for Newton between N and M (excluding both).
> 
> More info: [https://my.newtonschool.co/playground/code/idyoxe1fdjm9](https://my.newtonschool.co/playground/code/idyoxe1fdjm9)

```python
# Your code here
n,m=map(int,input().split())
chk=0
for i in range(n+1,m):
    if(i%2==0 and chk<5):
        print(i,end=" ")
        chk+=1
    if(chk==5): break

# end of program
```

## Day 5: Emily and Triplets

> **Problem Statement**
> 
> Emily was playing with triplets. She was excited to find out how many triples of non-negative integers (a, b, c) satisfy a+b+c≤S and a×b×c≤T, where S & T are non-negative integers.
> 
> More Info: [https://my.newtonschool.co/playground/code/qzm7lli9xevb](https://my.newtonschool.co/playground/code/qzm7lli9xevb)

***Solution:***

```python
# Your code here
def solve(s,t):
    a=b=c=[x for x in range(0,101)]
    count=0
    for i in a:
        for j in b:
            for k in c:
                if(i+j+k<=s and i*j*k<=t):
                    count+=1
    return count

s,t=map(int,input().split())
print(solve(s,t))
```

## Day 6: Abhas and Numbers

> **Problem Statement**
> 
> Abhas likes to play with numbers. He is given integers N and K. Find the number of triples (a, b, c) of positive integers not greater than N such that a+b, b+c, and c+a are all multiples of K. The order of a, b, and c does matter, and some of them can be the same.
> 
> More info: [https://my.newtonschool.co/playground/code/mhj0sjeq02c6](https://my.newtonschool.co/playground/code/mhj0sjeq02c6)

***Solution:***

```python
# Your code here
def solve(N, K):
    if (K % 2 == 0):
        x = N // K
        y = (N + (K // 2)) // K
 
        return x * x * x + y * y * y
    else:
        x = N // K
        return x * x * x

N,K=map(int,input().split())
print(solve(N,K))
```

## Day 7: Matching Strings

> **Problem Statement**
> 
> You are given two strings S and T. Determine whether it is possible to make S and T equal by doing the following operation at most once:  
>   
> Choose two adjacent characters in S and swap them.  
>   
> Note that it is allowed to choose not to do the operation.
> 
> More info: [https://my.newtonschool.co/playground/code/gw6aww5f6uhe](https://my.newtonschool.co/playground/code/gw6aww5f6uhe)

***Solution:***

```python
# Your code here
def swap(s,a,b):
    if s[a]==s[b]:
        return s
    else:
        s=list(s)
        s[a],s[b]=s[b],s[a]
        return ''.join(s)
 

s=input()
t=input()
swapped=False

for i in range(len(s)-1):
    if(s[i]==t[i]):
        continue
    elif(i+1<len(s) and not swapped):
        s=swap(s,i,i+1)
        swapped=True

if(s==t):
    print("Yes")
else:
    print("No")
```

Hope you like my effort, pls make sure you like this blog 😊 and subscribe to my newsletter to get updated regarding 30 days of code :))