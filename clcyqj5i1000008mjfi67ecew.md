# day-to-day solution of 30 days of code

Hey tech enthusiasts, 🤟

We are thrilled to announce the launch of the 30 Days of Code challenge. With 20+ Community for Keeping your vision up.. starting from 16 jan till 14 Feb!

Communities coming together!! • 30 coding challenges, each with a unique theme i.e. Problem Of The Day!. • Sessions between the challenge for swag and extra points.

The challenge is open to all skill levels, so whether you are a beginner just starting out in coding or a more experienced programmer, you can join the challenge and work your way up.

So what are you waiting for? • Active participants will receive swags such as T-Shirts, Bottles and many more. 😍 • Certificate for everyone!! ✨

### Language used

![python](https://skillicons.dev/icons?i=python align="left")

## Mall and Coupons

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

Hope you like my effort, pls make sure you like this blog 😊 and subscribe to my newsletter to get updated regarding 30 days of code :))