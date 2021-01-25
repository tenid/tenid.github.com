---
title: MAP과 Comprehension
last_modified_at: '2021-01-20'
---

# Python
## MAP과 Comprehension
1.입력의 대표적인 사례 3가지


* num = int( input())
* string  = input()
* char_lst = list(input())
* lst = list(map(int, input().split())

map(x,y)는 x함수를 y의 원소에 모두 적용한 map 객체를 반환 char_lst 내용을 문자열로 만들고 싶다면?  join 메서드


2.List 초기화는 comprehension으로!

{% highlight python linenos %}

lst_1d = [ 0 for _ in range(N)]
lst_2d = [[0 for _ in range(N)] for j in range(N)] 

{% endhighlight %}
lst_1d = 1차원 배열,  lst_2d = 2차월 배열
