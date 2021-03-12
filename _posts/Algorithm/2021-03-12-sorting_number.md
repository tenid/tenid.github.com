---
title: 2750.수 정렬하기
---

문제  
N개의 수가 주어졌을 때, 이를 오름차순으로 정렬하는 프로그램을 작성하시오.  

입력  
첫째 줄에 수의 개수 N(1 ≤ N ≤ 1,000)이 주어진다. 둘째 줄부터 N개의 줄에는 숫자가 주어진다. 이 수는 절댓값이 1,000보다 작거나 같은 정수이다. 수는 중복되지 않는다.  
  
예제 입력 1   
5  
5  
2  
3  
4  
1  

예제 출력 1   
1  
2  
3  
4  
5  
  
{% highlight python linenos %}

def solution(index):
    data = []
    # 입력 받은 n 만큼 배열에 넣기
    for _ in range(0,index):
        data.append(int(input()))

    # 정렬
    data = sorted(data)

    # 출력하기
    for i in range(0, len(data)):
        print(data[i], end="\n")


n = int(input())
solution(n)

{% endhighlight %}
