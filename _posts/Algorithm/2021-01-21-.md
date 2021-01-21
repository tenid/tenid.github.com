---
title: 이진수의 활용
category: Algorithm
---

-문제  
자연수를 A를 B번 곱한 수를 출력한다.  

보통은 A** % C 하면 된다고 생각을 하지만 이것은 시간복잡도가 O(B)이기 때문에 시간초과가 일어날 수 있다.  

{% highlight python linenos %}

#이진수를 이용한 거듭제곱 계산
def pow_custom(a, b):
    # b가 0인 경우
    ret = 1
    # b가 0이 되면 종료
    while b:  
				#b를 2로 나눈 나머지가 1인 경우 곱한다.  
        if b % 2 == 1 : ret *= a  
				#a는 계속 자신을 곱하면서 a^2 a^3 거듭제곱 수가 된다.  
        a = a*a  
        b //= 2  
    return ret

a, b = map(int, input().split())
print(pow_custom(a,b))

{% endhighlight %}
