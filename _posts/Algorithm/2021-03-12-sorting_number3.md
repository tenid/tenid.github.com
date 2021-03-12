---
title: 10989.수 정렬하기 3
---

시간 제한: 3초  
메모리 제한: 8MB  

문제  
N개의 수가 주어졌을 때, 이를 오름차순으로 정렬하는 프로그램을 작성하시오.  
  
  
입력  
첫째 줄에 수의 개수 N(1 ≤ N ≤ 10,000,000)이 주어진다. 둘째 줄부터 N개의 줄에는 숫자가 주어진다. 이 수는 10,000보다 작거나 같은 자연수이다.  

출력   
첫째 줄부터 N개의 줄에 오름차순으로 정렬한 결과를 한 줄에 하나씩 출력한다.  
   

예제 입력 1    
10  
5  
2  
3  
1  
4  
2  
3  
5  
1  
  
	
예제 출력 1  
1  
1  
2   
2   
3  
3  
4  
5  
5  
7  
  
이 문제는 PyPy3로 제출할 때 메모리 제한에 걸리므로 Python3로 제출  
메모리와 시간제한에 주의 하여 풀것  
1. 메모리 제한: 배열 보다 딕셔너리를 통해 메모리 공간 절약  
2.  시간제한: input() 보다 sys.stdin.readline()을 활용  
	 

{% highlight python linenos %}

import sys


def solution(index):
    data = {}
    # 입력 받은 n 만큼 배열에 넣기
    # input() 보다 속도가 더 빠름
    for _ in range(0, index):
        num = int(sys.stdin.readline())
        # 처음 입력받은 수라면 횟수를 1로 설정
        if num not in data.keys():
            data[num] = 1
        # 이미 입력받았던 수라면 횟수를 1 증가
        else:
            data[num] += 1
    # 정렬
    data = sorted(data.items())

    # 출력하기
    for i in range(len(data)):
        # 키 값에 해당되는 횟수
        for j in range(data[i][1]):
            # 키 값 출력
            print(data[i][0])


n = int(sys.stdin.readline())
solution(n)


{% endhighlight %}
