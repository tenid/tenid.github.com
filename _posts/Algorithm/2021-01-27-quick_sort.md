---
title: 퀵 정렬
last_modified_at: '2021-01-27'
category: Algorithm
---

![]({{ 'assets/images/quick_sort.jpg' | relative_url }})

{% highlight python linenos %}

array = [5, 7, 9, 0, 3, 1, 6, 2, 4, 8]

def quick_sort(array, start, end):
        # 1개만 남으면 start == end , start가 pivot인 경우 start>end
        if start >= end: #원소가 1개인 경우 종료
                return
        pivot = start # 피벗은 첫 번째 원소
        right = start + 1
        left = end
        while(right <= left):
                # 피벗보다 큰 데이터를 찾을 때까지 반복
                while(right <= end and array[right] <= array[pivot]):
                        right += 1
                # 피벗보다 작은 데이터를 찾은 때까지 반복
                while(left > start and array[left] >= array[pivot]):
                        left -= 1
                if(left < right): #엇갈렸다면 작은 데이터와 피벗을 교체
                        array[left], array[pivot] = array[pivot], array[left]
                else: #엇갈리지 않앗다면 작은 데이터와 큰 데이터를 교체
                        array[left], array[right] = array[right], array[left]
        # 분할 이후 왼쪽 부분과 오른쪽 부분에서 각각 정렬 수행
        quick_sort(array, start, left -1)
        quick_sort(array, left +1, end)

quick_sort(array, 0, len(array) -1)
print(array)


{% endhighlight %}
