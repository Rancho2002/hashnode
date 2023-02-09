# day-to-day solution of 30 days of code

Hey tech enthusiasts, 🤟

We are thrilled to announce the launch of the 30 Days of Code challenge. With 20+ Community for Keeping your vision up.. starting from 16 jan till 14 Feb!

Communities coming together!! • 30 coding challenges, each with a unique theme i.e. Problem Of The Day!. • Sessions between the challenge for swag and extra points.

The challenge is open to all skill levels, so whether you are a beginner just starting out in coding or a more experienced programmer, you can join the challenge and work your way up.

So what are you waiting for? • Active participants will receive swags such as T-Shirts, Bottles and many more. 😍 • Certificate for everyone!! ✨

### Language used

![python and c](https://skillicons.dev/icons?i=python,c align="left")

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

## Day 8: Contiguous Substring

> **Problem Statement**
> 
> You are given strings S and T consisting of lowercase English letters. Determine whether T is a (contiguous) substring of S.
> 
> A string Y is said to be a (contiguous) substring of X if and only if Y can be obtained by performing the operation below on X zero or more times.
> 
> Do one of the following.  
> i) Delete the first character in X.  
> ii) Delete the last character in X.  
> For instance, the tag is a (contiguous) substring of voltage, while ace is not a (contiguous) substring of atcoder.
> 
> More info : [https://my.newtonschool.co/playground/code/lwkqwpx5vrwh](https://my.newtonschool.co/playground/code/lwkqwpx5vrwh)

```python
def solve(S,T):
    if T in S:
        print("Yes")
    else:
        print("No")
S = input()
T = input()
solve(S,T)
```

## Day 9: Bob and Hammer

> **Problem Statement**
> 
> Bob is at the origin of a number line. He wants to reach a goal at coordinate X.  
> There is a wall at coordinate Y, which Bob cannot go beyond at first. However, after picking up a hammer at coordinate Z, he can destroy that wall and pass through.  
> Determine whether Bob can reach the goal. If he can, find the minimum total distance he needs to travel to do so.
> 
> More info: [https://my.newtonschool.co/playground/code/ty3qnc65hz8y](https://my.newtonschool.co/playground/code/ty3qnc65hz8y)

***Solution:***

```python
# Contributed by : https://github.com/adi271001
a, b, c = map(int, input().split())
if(a*b>=0 and a>=0):
    if b>a:
        print(a)
    elif c>b and a>b:
        print(-1)
    elif c>b:
        print(a)
elif(a*b>=0 and a<=0 and b<=0):
    if(a>b or (a<b and c<=0 and b<c)):
        print(abs(a))
    elif a<b and b<c:
        print(2*c-a)
    elif b>a:
        print(-1)
elif(a*b<=0 and a>=0):
    print(a)
elif(a*b<=0 and c>=0):
    print(abs(a))
else:
    print(-1)
```

## Day 10: Bacterias

> **Problem Statement**
> 
> There are A Bacterias.  
> Each time Jerry shouts, the bacterias multiply by K times.  
> In order to have B or more slimes, at least how many times does Jerry need to shout?
> 
> More info: [https://my.newtonschool.co/playground/code/ssqo8i2d0790](https://my.newtonschool.co/playground/code/ssqo8i2d0790)

***Solution:***

```python
# Your code here
a,b,c=map(int,input().split())
count=0
while(b>a):
    a=a*c
    count+=1
print(count)
```

## Day 11: Unlucky Seven

> **Problem Statement**
> 
> Mahi hates the number 7.
> 
> We are interested in integers without the digit 7 in both decimal and octal. How many such integers are there between 1 and N (inclusive)?
> 
> More info: [https://my.newtonschool.co/playground/code/q3uwdvvrguyb](https://my.newtonschool.co/playground/code/q3uwdvvrguyb)

***Solution:***

```python
# Your code here
def solve(n):
    x=[str(oct(i))[2:] for i in range(1,n+1)]
    y=[str(i) for i in range(1,n+1)]
    count=0
    for i in range (n):
        if '7' in x[i] or '7' in y[i]:
            continue 
        else:
            count+=1
    return count

n=int(input())
print(solve(n))
```

## Day 12: Play with 0's and 2's

> **Problem Statement**
> 
> Alexa Loves to play with 0's and 2's. Among the positive integers that consist of 0's and 2's when written in base 10, he wanted to find the Kth smallest integer. Help him find that.
> 
> More info: [https://my.newtonschool.co/playground/code/x0xsoz1t9245](https://my.newtonschool.co/playground/code/x0xsoz1t9245)

***Solution:***

```python
# Your code here
n=int(input())
s=str(bin(n))[2:]
print(s.replace("1","2"))
```

## Day 13: MEX

> **Problem Statement**
> 
> You are given a sequence of length N consisting of integers:  
> A=(A<sub>1</sub>, A<sub>2</sub>,...., A<sub>N</sub>)  
> Find the smallest non-negative integer not in (A<sub>1</sub>, A<sub>2</sub>,....,A<sub>N</sub>).
> 
> More info: [https://my.newtonschool.co/playground/code/d776qqeu2t6y](https://my.newtonschool.co/playground/code/d776qqeu2t6y)

***Solution:***

```python
def solve():
    input()
    sequence = set(map(int, input().split()))
    for i in range(2001):
        if i not in sequence:
            return i
print(solve())
```

## Day 14: Alexa and Strings

> **Problem Statement**
> 
> Alexa loves to play with strings. She is given a string S consisting of lowercase English letters.  
> If '**a**' appears in S, print the last index at which it appears; otherwise, print −1. (The index starts at 1. )
> 
> More info: [https://my.newtonschool.co/playground/code/w4iz1x4fbyd6](https://my.newtonschool.co/playground/code/w4iz1x4fbyd6)

***Solution:***

```python
# Your code here
s=list(input())
s.reverse()
s="".join(s)
if "a" in s: print(len(s)-s.index("a"))
else: print(-1)
```

## Day 15: Bob and Exams

> **Problem Statement**
> 
> There was an exam consisting of three problems worth 1, 2, and 4 points.  
> Alexa, Edward, and Bob took this exam. Alexa scored A points, and Edward scored B points.
> 
> Bob solved all of the problems solved by at least one of Alexa and Edward and failed to solve any of the problems solved by, neither of them.
> 
> Find Bob's score.  
> It can be proved that Bob's score is uniquely determined under the Constraints of this problem.
> 
> More info: [https://my.newtonschool.co/playground/code/h1gqdcep5bod](https://my.newtonschool.co/playground/code/h1gqdcep5bod)

***Solution:***

```python
# Your code here
a,b=map(int,input().split())
print((a & b) + (a ^ b))
```

## Day 16 : Prefix Strings

> **Problem Statement**
> 
> You are given two strings S and T consisting of lowercase English letters. Determine if S is a prefix of T.
> 
> More info: [https://my.newtonschool.co/playground/code/9ql82dpeu3qy](https://my.newtonschool.co/playground/code/9ql82dpeu3qy)

***Solution:***

```python
# Your code here
def prefix(s,t):
    if(len(s)<=len(t) and s==t[0:len(s)]): print("Yes")
    else: print("No")
s=input()
t=input()
prefix(s,t)
```

## Day 17: Reverse Strings

> **Problem Statement**
> 
> You are given integers L, R, and a string S consisting of lowercase English letters.  
> Print this string after reversing (the order of) the L-th through R-th characters.
> 
> **more info :** [https://my.newtonschool.co/playground/code/r798ze6sbgc1](https://my.newtonschool.co/playground/code/r798ze6sbgc1)

***Solution:***

```python
# Your code here
def rev(s):
    s=list(s)
    s.reverse()
    return "".join(s)

a,b=map(int,input().split())
s=input()

print(s[0:a-1]+rev(s[a-1:b])+s[b:])
```

## Day 18: Carry or Not?

> **Problem Statement**
> 
> You are given positive integers A and B.  
> Let us calculate A+B (in decimal). If it does not involve a carry, print **Easy**; if it does, print **Hard**.
> 
> More info: [https://my.newtonschool.co/playground/code/jbysom98s95s](https://my.newtonschool.co/playground/code/jbysom98s95s)

***Solution:***

```python
# Your code here
a,b=map(int,input().split())
flag=False

while(a):
    d=a%10
    e=b%10
    chk=(d+e)%10
    if(chk<a%10 and chk<b%10):
        flag=True
        break
    else:
        a=a//10
        b=b//10
print("Hard" if flag else "Easy")
```

## Day 19: Alexa and Balls

> **Problem Statement**
> 
> There is a container with A cyan balls. Alexa will do the following operation as many times as he likes (possibly zero times):  
> Add B cyan balls and C red balls into the container.  
> Alexa's objective is to reach a situation where the number of cyan balls in the container is at most D times the number of red balls in it.
> 
> Determine whether the objective is achievable. If it is achievable, find the minimum number of operations needed to achieve it.
> 
> More info: [https://my.newtonschool.co/playground/code/jzikdht1iho1](https://my.newtonschool.co/playground/code/jzikdht1iho1)

***Solution:***

```python
# Your code here
a, b, c, d = map(int, input().split())
result = 0
red = 0
target = d

if b >= c * d:
    result = -1
else:
    while a > red * d:
        a = a + b
        red = red + c
        result += 1

print(result)
```

## Day 20: Chipmunk and Nuts

> **Problem Statement**
> 
> There are N trees. The i<sup>th</sup> tree bears A<sub>i</sub> nuts. Chipmunk will harvest nuts from the trees in the following manner:  
> From a tree with 10 or fewer nuts, she does not take nuts.  
> From a tree with more than 10 nuts, she takes all but 10 nuts.  
> Find the total number of nuts Chipmunk will take from the trees.
> 
> More info: [https://my.newtonschool.co/playground/code/jlc53x5ur1r1](https://my.newtonschool.co/playground/code/jlc53x5ur1r1)

***Solution:***

```c
#include <stdio.h> // header file for Standard Input Output
#include <stdlib.h> // header file for Standard Library

int main() {
    //Your code here
    int n,a,count=0;
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        scanf("%d",&a);
        if(a>10) count+=a-10;
    }
    printf("%d",count);
    return 0;
}
```

## Day 21: Bob and Digits

> **Problem Statement**
> 
> Bob loves to play with numbers. He has an integer N. Find the number of digits that N has in base K.
> 
> More info: [https://my.newtonschool.co/playground/code/82oyjzel5dss](https://my.newtonschool.co/playground/code/82oyjzel5dss)

***Solution:***

```python
# Your code here
a,b=map(int,input().split())
c=""
while(a):
    c+=str(a%b)
    a=a//b
print(len(c))
```

## Day 22: Shifted String

> **Problem Statement**
> 
> We have a string S consisting of uppercase English letters. Additionally, an integer N will be given.  
> Shift each character of S by N in alphabetical order (see below), and print the resulting string.
> 
> We assume that A follows Z. For example, shifting A by 2 results in C (A → B → C), and shifting Y by 3 results in B (Y → Z → A → B).
> 
> More info: [https://my.newtonschool.co/playground/code/1ehegpitlyk7](https://my.newtonschool.co/playground/code/1ehegpitlyk7)

***Solution:***

```python
def shifted_string(n, s):
  res = ""
  for char in s:
    res += chr((ord(char) - ord("A") + n) % 26 + ord("A"))
  return res
n = int(input().strip())
s = input().strip()
print(shifted_string(n, s))
```

## Day 23: Cards Shuffle

> **Problem Statement**
> 
> We have 4 cards with an integer 1 written on it, 4 cards with 2, …, 4 cards with N, for a total of 4N cards.  
> Alexa shuffled these cards, removed one of them, and gave you a pile of the remaining 4N−1 cards. The i- th card (1≤i≤4N−1) of the pile has an integer A<sub>i</sub> written on it.
> 
> Find the integer written on the card removed by Alexa.
> 
> More info: [https://my.newtonschool.co/playground/code/82sz2hgpfl0l](https://my.newtonschool.co/playground/code/82sz2hgpfl0l)

***Solution:***

```python
# Your code here
from collections import Counter
n=int(input())
l=list(map(int,input().split()))
l=Counter(l)
chk=min(l.values())
for i in l:
    if l[i]==chk:
        print(i)
        break
```

## Day 24: String Sequence

> **Problem Statement**
> 
> You are given a sequence of 26 integers P=(P<sub>1</sub>, P<sub>2</sub>, …, P<sub>26</sub> ) consisting of integers from 1 through 26. It is guaranteed that all elements in P are distinct.  
>   
> Print a string S of length 26 that satisfies the following condition. For every i (1≤i≤26), the i- th character of S is the lowercase English letter that comes P<sub>i</sub>\- th in alphabetical order.
> 
> More info: [https://my.newtonschool.co/playground/code/8oovbbhm8v6r](https://my.newtonschool.co/playground/code/8oovbbhm8v6r)

***Solution:***

```python
# Your code here
s="abcdefghijklmnopqrstuvwxyz"
l=list(map(int,input().split()))
for i in l:
    print(s[i-1],end="")
```

## Day 25: Multiple of 3

> **Problem Statement**
> 
> Given is a positive integer N, where none of the digits is 0. Let k be the number of digits in N. We want to make a multiple of 3 by erasing at least 0 and at most k−1 digits from N and concatenating the remaining digits without changing the order. Determine whether it is possible to make a multiple of 3 in this way. If it is possible, find the minimum number of digits that must be erased to make such a number.
> 
> More info: [https://my.newtonschool.co/playground/code/lqhvuld49hbb](https://my.newtonschool.co/playground/code/lqhvuld49hbb)

***Solution:***

```python
# Your code here
def helper(N: int) -> int:
    if N % 3 == 0:
        return 0
    digit = [0 for i in range(10)]
    sum = 0
    temp = N
    while N > 0:
        sum += N % 10
        digit[N % 10] += 1
        N = N // 10
    for i in range(3):
        val = sum - (sum // 3) * 3 + 3 * i
        if val > 0 and val < 10 and digit[val] > 0:
            return 1
    return 2 if temp > 100 else -1
n=int(input())
print(helper(n))
```

## Announcement

Like or its no mean to update this blog. Like target : 50