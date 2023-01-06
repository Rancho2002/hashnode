# Complete Solution of Newton School 51 days of Coding Challenge

If you are new to this challenge, first of all, join [Newton School Official Discord Server](https://bit.ly/3hc9GsX) and get started with it. Awesome prizes are awaiting you. Use this blog as a reference for those who face problems while solving the questions. Don't forget to share it with your peers. 😊

### ::Language in this blog::

![python](https://skillicons.dev/icons?i=python align="left")

## Question 1: Tell Date

> **Tell Date**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> You are given a string S in *yyyy/mm/dd* format, which represents a date in 2022. You have to tell whether the date if before or after 20 June 2022.
> 
> If the date is before 20 June, print "Before". If the date is 20 June or later, Print "After".
> 
> **Input**
> 
> The first and only line of the input contains a string S.
> 
> **Constraints:**  
> S is always a valid date
> 
> **Output**
> 
> Print the answer
> 
> **Example**
> 
> **Sample Input 1:**  
> 2022/01/30
> 
> **Sample Output 1:**  
> Before
> 
> Explanation:  
> 30 Jan 2022 is before 20 June 2022

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

> **Money Money**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> Newton visited his friends in Japan on the occasion of Diwali.
> 
> He received N gifts there. Some gifts were in Japanese yen (JPY) and Some gifts were in the form of Bitcoin (BTC).
> 
> You are given N values T<sub>1</sub>, T<sub>2</sub>,. ., T<sub>N</sub> and N strings S<sub>1</sub>, S<sub>2</sub>,. ., S<sub>N</sub>. Each string S<sub>i</sub> is either "JPY" or "BTC" representing the type of the i- th gift and value X<sub>i</sub> represents the amount of the i- th gift.
> 
> You need to convert and calculate how many Japanese Yen Newton got from Japan's visit.
> 
> (Note: 1BTC = 380000.0 JPY)
> 
> **Input**
> 
> The first line of the input contains a single integer N.  
> The next N lines contains a real number T<sub>i</sub> and a string S<sub>i</sub>.
> 
> **Constraints:**  
> 2 ≤ N ≤ 100  
> 0.00000001 ≤ T<sub>i</sub> ≤ 100.00000000  
> S<sub>i</sub> is either "BTC" or "JPY"  
> T<sub>i</sub> is either a integer or a decimal with 8 decimal digits.
> 
> **Output**
> 
> Output the total value in Japanese Yen.  
> Print the answer with 8 decimal digits.
> 
> **Example**
> 
> **Sample Input 1:**  
> 2  
> 10000 JPY  
> 0.10000000 BTC
> 
> **Sample Output 1:**  
> 48000.00000000

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

> **Newton Hates Balloons**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> There are N balloons placed on a number line. Newton doesn't like balloons so he wants to burst exactly K balloons.
> 
> The i- th balloon is placed on coordinate X<sub>i</sub>. Here, X<sub>1</sub> &lt; X<sub>2</sub> &lt; ... &lt; X<sub>n</sub>.
> 
> Initially Newton is at coordinate 0. In a single second, he can move from coordinate C to either C - 1 or C + 1.
> 
> Newton doesn't like to waste much of his time so find the minimum time needed to burst K balloons.
> 
> **Input**
> 
> The first line of the input contains 2 integers N and K  
> The next line contains N integers, X<sub>1</sub>, X<sub>2</sub>, ... , X<sub>n</sub>.
> 
> **Constraints:**  
> 1 ≤ N ≤ 2 x 10<sup>5</sup>  
> 1 ≤ K ≤ N  
> \-10<sup>8</sup> ≤ X<sub>i</sub> ≤ 10<sup>8</sup>
> 
> **Output**
> 
> Output the minimum time
> 
> **Example**
> 
> **Sample Input 1:**  
> 5 3  
> \-40 -10 5 20 80
> 
> **Sample Output 1:**  
> 40
> 
> **Explanation**  
> Newton would first burst the balloon at -10, then at 5, then at 20. Total time take = 10 + 10 + 5 + 15 = 40
> 
> **Sample Input 2:**  
> 9 5  
> \-20 -17 -9 -4 -3 1 2 3 4
> 
> **Sample Output 2:**  
> 10

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

> **Newton's Family**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> Newton’s family has *N* members.
> 
> Every member, except the member *1*, has exactly one immediate parent with a smaller number.
> 
> When a person X is the immediate parent of a person Y, the person Y is said to be an immediate child of the person X.
> 
> You are given the immediate parent of the member numbered *i* is the member numbered A<sub>i</sub>. For each member, find how many immediate child it has.
> 
> **Input**
> 
> The first line contains one integer N.  
> The second line contains N - 1 integers A<sub>1</sub>, A<sub>2</sub> ... A<sub>N-1</sub>.
> 
> **Constraints**  
> 2 ≤ N ≤ 2×10<sup>5</sup>  
> 1 ≤ A<sub>i</sub> &lt; i
> 
> **Output**
> 
> For each of the members numbered 1, 2, ..., N, print the number of immediate children it has, in its own line.
> 
> **Example**
> 
> **Sample Input 1:**  
> 5  
> 1 1 2 2
> 
> **Sample Output 1:**  
> 2  
> 2  
> 0  
> 0  
> 0
> 
> **Explaination**  
> The member numbered 1 has two immediate children: the members numbered 2 and 3.  
> The member numbered 2 has two immediate children: the members numbered 4 and 5.  
> The members numbered 3, 4, and 5 do not have immediate child.

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

> **Camp**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> Yash has *N* days of Camp.
> 
> He has to visit *M* places. It will take A<sub>i</sub> days for him to visit the ith place. He cannot visit multiple places on the same day, or hang out on a day he does an assignment.
> 
> What is the maximum number of days Yash can hang out during the Camp if he visits all the places during this Camp?
> 
> If Yash cannot visit all the places during the Camp, print *\-1* instead.
> 
> **Input**
> 
> The first line contains two integers N and M.  
> The second line contains N integers A<sub>1</sub>, A<sub>2</sub> ... A<sub>M</sub>.
> 
> **Constraints**  
> 1 ≤ N ≤ 10<sup>6</sup>  
> 1 ≤ M ≤ 10<sup>4</sup>  
> 1 ≤ Ai ≤ 10<sup>4</sup>
> 
> **Output**
> 
> Print the maximum number of days Yash can hang out during the Camp, or -1.
> 
> **Example**
> 
> **Sample Input 1**  
> 41 2  
> 5 6
> 
> **Sample Output 1**  
> 30
> 
> **Explaination**  
> He can do the first visit on the first 5 days, hang out on the next 30 days, and do the second visit on the last 6 days of the vacation. In this way, he can safely spend 30 days hanging out.

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

> **End Card**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> You are given N cards and an integer *i*.
> 
> Find an integer *j* such that the i- th card from the top of the deck is the j- th card from the bottom of the deck.
> 
> **Input**
> 
> The first and only line of the input contains 2 integers, N and *i*
> 
> **Constraints:**  
> 1 ≤ i ≤ N ≤ 10<sup>5</sup>
> 
> **Output**
> 
> Print the answer
> 
> **Example**
> 
> **Sample Input 1:**  
> 5 3
> 
> **Sample Output 1:**  
> 3
> 
> **Explanation:**  
> The third card from the top is also the third card from the end
> 
> **Sample Input 2:**  
> 3 1
> 
> **Sample Output 2:**  
> 3

***Solution:***

```python
# Your code here
n,i=map(int,input().split())
print(n-i+1)
```

## Question 7: Newtogon

> **Newtogon**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> Newton wants to draw a polygon with N sides on a two- dimensional plane. Length of each side is given as L<sub>1</sub>, L<sub>2</sub>, ... , L<sub>3</sub>
> 
> You need to tell Newton whether or not its possible to make the polygon.
> 
> **Input**
> 
> The first line of the input contains a single integer N  
> The next line contains N space separated integers L<sub>1</sub>, L<sub>2</sub>, ... , L<sub>3</sub>
> 
> **Constraints:**  
> 3 &lt;= N &lt;= 10  
> 1 &lt;= L<sub>i</sub> &lt;= 100
> 
> **Output**
> 
> Output "Yes" if its possible to draw the polygon, else "No"
> 
> **Example**
> 
> **Sample Input 1:**  
> 4  
> 1 2 3 10
> 
> **Sample Output 1:**  
> No
> 
> **Explanation**  
> The side with length 10 is greater than the sum of all other sides. So a polygon is not possible
> 
> **Sample Input 2:**  
> 4  
> 1 2 3 4
> 
> **Sample Output 2:**  
> Yes

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

> **Point Dance**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> Newton wants to dance and that too on a number line.
> 
> In his dance moves, he wants to cover M specific coordinates P<sub>1</sub>, P<sub>2</sub>, ... P<sub>M</sub>.
> 
> To do that, he has N checkpoints that he needs to place at some integer coordinates.  
> In a single move, Newton can move any of his checkpoint at coordinate X to X - 1 or X + 1
> 
> Find the minimum moves required by Newton to travel all of M specified coordinates using the checkpoints.
> 
> **Input**
> 
> The first line of the input contains two integers, N and M  
> The second line of the input contains M integers P<sub>1</sub>, P<sub>2</sub>, ... P<sub>M</sub>.
> 
> **Constraints:**  
> 1 ≤ N ≤ 10<sup>5</sup>  
> 1 ≤ M ≤ 10<sup>5</sup>  
> \-10<sup>5</sup> ≤ P<sub>i</sub> ≤ 10<sup>5</sup>
> 
> **Output**
> 
> Output the minimum number of moves required to achieve the objective.
> 
> **Example**
> 
> **Sample Input 1:**  
> 2 5  
> 9 1 11 2 13
> 
> **Sample Output 1:**  
> 5
> 
> **Explanation:**  
> The objective can be achieved in five moves as follows, and this is the minimum number of moves required.  
> \* Initially, put the two pieces at coordinates 1 and 9.  
> \* Move the piece at coordinate 1 to 2.  
> \* Move the piece at coordinate 9 to 10.  
> \* Move the piece at coordinate 10 to 11.  
> \* Move the piece at coordinate 11 to 12.  
> \* Move the piece at coordinate 12 to 13.

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

## Question 9: Divide It

> **Divide it**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> Newton has an array containing *12* integers from 1 to 12. But later he divides it into *3* arrays in the following manner.  
> First array - 1 3 5 7 8 10 12  
> Second array - 4 6 9 11  
> Third array - 2
> 
> Given two integers a and b (1 ≤ a &lt; b ≤ 12). Find whether these two integers belong to the same array or not.
> 
> **Input**
> 
> The input contains two integers x and y.
> 
> **Constraints**  
> 1 ≤ x &lt; y ≤ 12
> 
> **Output**
> 
> If x and y belong to the same group, print Yes; otherwise, print No.
> 
> **Example**
> 
> **Sample Input 1**  
> 1 3
> 
> **Sample Output 1**  
> Yes
> 
> **Sample Input 2**  
> 2 4
> 
> **Sample Output 2**  
> No

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

> **Find Prosum**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> You are given an array of N integers A1, A2,. . An. You have to calculate prosum of the array.
> 
> Prosum is defined as the sum of all the Ai x Aj over all pairs (i, j) such that 1 &lt;= i &lt; j &lt;= N, modulo (10^9 + 7)
> 
> **Input**
> 
> The first line of the input contains a single integer N  
> The next line of the input contains N different integers A1, A2,. . An
> 
> Constraints:
> 
> 1. 2 &lt;= N &lt;= 2 x 10^5
>     
> 2. 0 &lt;= Ai &lt;= 10^9
>     
> 
> **Output**
> 
> Print the answer
> 
> **Example**
> 
> Sample Input 1:  
> 4  
> 1 2 3 4
> 
> Sample Output 1:  
> 35
> 
> Explanation:  
> 1 x 2 + 1 x 3 + 1 x 4 + 2 x 3 + 2 x 4 + 3 x 4 = 35

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

> **Letter game**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> There is a room filled with letters.  
> Newton can choose exactly three letters C<sub>1</sub>, C<sub>2</sub> and C<sub>3</sub>. If all of them are the same letter, then it is considered as a win.
> 
> Determine whether Newton wins.
> 
> **Input**
> 
> The first line contains three letters C<sub>1</sub>, C<sub>2</sub> and C<sub>3</sub>.
> 
> **Constraints**  
> C<sub>i</sub> is an uppercase English letter.
> 
> **Output**
> 
> If the result is a win, print Won; otherwise, print Lost.
> 
> **Example**
> 
> **Sample Input 1:**  
> SSS
> 
> **Sample Output 1:**  
> Won
> 
> **Sample Explanation 1:**  
> All of them are the same letter, so it is a win.
> 
> **Sample Input 2:**  
> WVW
> 
> **Sample Output 2:**  
> Lost
> 
> **Sample Explanation 2:**  
> It is not a win.

***Solution:***

```python
# Your code here
letter=input().strip()
if(len(set(letter))==1): print("Won")
else: print("Lost")
```

## Question 12: Vegetable

> **Vegetable**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> There are some dishes. Each of them is a Chinese dish with two vegetables or an Italian dish with four vegetables.
> 
> There are X dishes in total, and Y vegetables in total.  
> Determine whether there is a combination of numbers of Chinese dishes and Italian dishes in which this statement is correct.
> 
> **Input**
> 
> The first line contains two integers X and Y.
> 
> **Constraints**  
> 1≤X≤100  
> 1≤Y≤100  
> All values in input are integers.
> 
> **Output**
> 
> If there is a combination of numbers of Chinese dishes and Italian dishes in which the statement is correct, print Yes; otherwise, print No.
> 
> **Example**
> 
> **Sample Input 1:**  
> 3 8
> 
> **Sample Output 1:**  
> Yes
> 
> **Sample Explanation 1:**  
> The statement "there are 3 dishes in total and 8 vegetables in total" is correct if there are two Chinese dishes and one Italian dish. Thus, there is a combination of numbers of Chinese dishes and Italian dishes in which the statement is correct.

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

> **Assign zero**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> You are given a sequence of 5 integers A.  
> Initially, A<sub>i</sub> (1 ≤ i ≤ 5) assigns i.
> 
> But due to some glitch, one of the integers in the array becomes 0.  
> Find out which integer of A assigned 0.
> 
> **Input**
> 
> The first line contains 5 integers A<sub>1</sub>, A<sub>2</sub> ... A<sub>5</sub>.
> 
> **Constraints**  
> The values of A<sub>1</sub>, A<sub>2</sub>, A<sub>3</sub>, A<sub>4</sub>, A<sub>5</sub> given as input are a possible outcome of the assignment.
> 
> **Output**
> 
> If the integer assigned 0 was A<sub>i</sub>, print the integer i.
> 
> **Example**
> 
> **Sample Input 1:**  
> 0 2 3 4 5
> 
> **Sample Output 1:**  
> 1
> 
> **Sample Input 2:**  
> 1 2 0 4 5
> 
> **Sample Output 2:**  
> 3

***Solution:***

```python
# Your code here
def find(arr):
    return arr.index(0)+1

arr=list(map(int,input().split()))
print(find(arr))
```

## Question 14: **Kick Palindrome**

> **Kick Palindrome**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> Newton got a string as a gift on Christmas.
> 
> Newton likes palindromes so he decides to make this string into a palindrome.
> 
> He can kick the string and after every kick he can change any one of its character to any other character of his choice.
> 
> Find the minimum number of times that Newton has to kick the string.
> 
> **Input**
> 
> The first and the only line of the input contains a single string S
> 
> **Constraints:**
> 
> * 1 ≤ |S| ≤ 1000
>     
> * All characters in S are in lowercase and are English letters
>     
> 
> **Output**
> 
> Output the answer
> 
> **Example**
> 
> **Sample Input 1:**  
> newton
> 
> **Sample Output 1:**  
> 2
> 
> **Sample Explanation 1:**  
> In the first kick, Newton changes the 2nd character to 'o'  
> In the second kick, Newton changes the 4th character to 'w'.  
> Thus, the final word is "nowwon" which is a palindrome.

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

> **Newton Gold Magic**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> Newton knows magic and he can mysteriously combine several items to create new items.
> 
> One day, Newton got his hand on N bars of gold. He cannot carry all of the N bars, so he used his magic to combine bars.
> 
> Each gold bar has a weight represented by W<sub>i</sub> (1 ≤ i ≤ N).
> 
> In one operation, Newton can take 2 bars of gold and combine them to create a single bar of gold. The weight of the new bar is (X+Y)/2 where X and Y represent the weights of the two initial bars.
> 
> Newton will perform this operation N-1 times and in the end, he will be left with only one bar of gold.
> 
> Find out the maximum possible weight of the final bar left with Newton.
> 
> **Input**
> 
> The first line of the input contains a single integer N  
> The next line contains N space-separated integers, W<sub>1</sub>, W<sub>2</sub>,. ., W<sub>N</sub>
> 
> **Constraints:**  
> 2 ≤ N ≤ 50  
> 1 ≤ W<sub>i</sub> ≤ 1000
> 
> **Output**
> 
> Print the answer in a single line with decimal values upto 8 digits.
> 
> **Example**
> 
> **Sample Input 1:**  
> 2  
> 2 4
> 
> **Sample Output 1:**  
> 3.00000000
> 
> **Sample Explanation 1:**  
> (2+4)/2 = 3
> 
> **Sample Input 2:**  
> 3  
> 500 300 200
> 
> **Sample Output 2:**  
> 375.00000000
> 
> **Sample Explanation 2:**  
> The maximum weight can only be achieved by first combining 300 and 200 to get 250, then combining 250 with 500 to get 375.

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

> **Stringram**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> We define a *Stringram* of a string as the string that can be formed by rearranging the given string.
> 
> For example, "tewnon" is the *Stringram* of "newton".
> 
> Einstein has given Newton N distinct strings S<sub>1</sub>, S<sub>2</sub>,. ., S<sub>N</sub> each containing 10 lowercase characters. Now, he wants Newton to count the number of pairs i, j (1 ≤ i &lt; j ≤ N) such that the string S<sub>i</sub> is the *Stringram* of S<sub>j</sub>.
> 
> **Input**
> 
> The first line of the input contains a single integer N  
> The i- th of the N lines contains a string S<sub>i</sub> of length 10
> 
> **Constraints:**
> 
> 1. 2 ≤ N ≤ 2 x 10<sup>5</sup>
>     
> 
> **Output**
> 
> Output the answer in a single line
> 
> **Example**
> 
> **Sample Input 1:**  
> 3  
> nocrtsatni  
> atomcastic  
> constraint
> 
> **Sample Output 1:**  
> 1
> 
> **Sample Explanation 1:**  
> The only valid pair is S<sub>1</sub> and S<sub>3</sub>.
> 
> **Sample Input 2:**  
> 5  
> abaaaaaaaa  
> oneplustwo  
> aaaaaaaaba  
> twoplusone  
> aaaabaaaaa
> 
> **Sample Output 2:**  
> 4

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

## Question 17: Socket Problem

> **Socket Problem**
> 
> Time Limit: 2 sec  
> Memory Limit: 128000 kB
> 
> **Problem Statement**
> 
> Newton has shifted to a new house and it came to his notice that there is only one socket in his house !!!  
>   
> Newton does a lot of experiments using electricity and wants at least B sockets in his house.  
>   
> Furthermore, he has ample amount of extension cords and each extension has A sockets and takes one socket. In others words, an extension cord extends one socket into A sockets.  
>   
> You need to tell Newton how many extension cords will be required so that he can have at least B sockets.
> 
> **Input**
> 
> The first and the only line of the input contains 2 single integers A and B  
>   
> **Constraints:**  
> 1) 2 ≤ A ≤ 200  
> 2) 1 ≤ B ≤ 200
> 
> **Output**
> 
> Print the answer
> 
> **Example**
> 
> **Sample Input 1:**  
> 4 10  
>   
> **Sample Output 1:**  
> 3  
>   
> **Sample Explanation 1:**  
> 3 power strips, each with 4 sockets, extend the socket into 10 empty sockets.  
>   
> **Sample Input 2:**  
> 8 9  
>   
> **Sample Output 2:**  
> 2

***Solution:***

```python
# Your code here
def solve(A,B):
    if(A>2):
        ans=B//(A-1)
        if(B%(A-1)>1):
            ans+=1  
    else:
        ans=B-1
    print(ans)
a,b=map(int,input().split())
solve(a,b)
```

### New Questions are to be updated with a daily streak. Make sure you subscribe to the newsletter to be notified when I am adding more solutions. Thanks for reading 😊. A small sponsor is always appreciated 💝