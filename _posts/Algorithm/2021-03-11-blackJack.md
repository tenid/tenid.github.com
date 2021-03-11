---
title: 2798.블랙잭
---

입력  
첫째 줄에 카드의 개수 N(3 ≤ N ≤ 100)과 M(10 ≤ M ≤ 300,000)이 주어진다. 둘째 줄에는 카드에 쓰여 있는 수가 주어지며, 이 값은 100,000을 넘지 않는 양의 정수이다.  
  
합이 M을 넘지 않는 카드 3장을 찾을 수 있는 경우만 입력으로 주어진다.  
  
출력  
첫째 줄에 M을 넘지 않으면서 M에 최대한 가까운 카드 3장의 합을 출력한다.  
  
예제 입력 1  
5 21  
5 6 7 8 9  
  
예제 출력 1  
21  
  
예제 입력 2  
10 500  
93 181 245 214 315 36 185 138 216 295  
  
예제 출력 2  
497  

{% highlight python linenos %}
n,m = map(int, input().split())

data = list(map(int, input().split()))

total = 0
result = 0
# 첫번째 수
for i in range(0, n-2):
    # 두번째 수
    for j in range(i+1 ,n-1):
        # 세번째 수
        for k in range(j+1, n):
            total = data[i] + data[j] + data[k]
            # 세개의 수가 m보다 작고 이미 저장된 값보다 클 경우
            if total <= m and result < total:
                result = total
print(result)

{% endhighlight %}
