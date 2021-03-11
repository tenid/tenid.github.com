---
title: 1018.체스판 다시 칠하기
---

문제  
지민이는 자신의 저택에서 MN개의 단위 정사각형으로 나누어져 있는 M*N 크기의 보드를 찾았다. 어떤 정사각형은 검은색으로 칠해져 있고, 나머지는 흰색으로 칠해져 있다. 지민이는 이 보드를 잘라서 8*8 크기의 체스판으로 만들려고 한다.  
  
체스판은 검은색과 흰색이 번갈아서 칠해져 있어야 한다. 구체적으로, 각 칸이 검은색과 흰색 중 하나로 색칠되어 있고, 변을 공유하는 두 개의 사각형은 다른 색으로 칠해져 있어야 한다. 따라서 이 정의를 따르면 체스판을 색칠하는 경우는 두 가지뿐이다. 하나는 맨 왼쪽 위 칸이 흰색인 경우, 하나는 검은색인 경우이다.   
   
보드가 체스판처럼 칠해져 있다는 보장이 없어서, 지민이는 8*8 크기의 체스판으로 잘라낸 후에 몇 개의 정사각형을 다시 칠해야겠다고 생각했다. 당연히 8*8 크기는 아무데서나 골라도 된다. 지민이가 다시 칠해야 하는 정사각형의 최소 개수를 구하는 프로그램을 작성하시오.   

입력  
첫째 줄에 N과 M이 주어진다. N과 M은 8보다 크거나 같고, 50보다 작거나 같은 자연수이다. 둘째 줄부터 N개의 줄에는 보드의 각 행의 상태가 주어진다. B는 검은색이며, W는 흰색이다.  

출력  
첫째 줄에 지민이가 다시 칠해야 하는 정사각형 개수의 최솟값을 출력한다.  


예제 입력 1   
8 8  
WBWBWBWB  
BWBWBWBW  
WBWBWBWB  
BWBBBWBW  
WBWBWBWB  
BWBWBWBW  
WBWBWBWB  
BWBWBWBW  
  
예제 출력 1   
1  

{% highlight python linenos %}

# 체스판 전체를 모두 바꿔야 하는 경우
result = 64


# 맨 왼쪽 위 칸이 흰색인 경우
def white_color(board, row, column):
    count = 0
    for i in range(row, 8 + row):
        for j in range(column, 8 + column):
            # 짝수 행
            if i % 2 == 0:
                # 짝수 열
                if j % 2 == 0:
                    if board[i][j] == 'W':
                        continue
                    else:
                        count += 1
                # 홀수 열
                if j % 2 == 1:
                    if board[i][j] == 'B':
                        continue
                    else:
                        count += 1
            # 홀수 행
            if i % 2 == 1:
                # 짝수 열
                if j % 2 == 0:
                    if board[i][j] == 'B':
                        continue
                    else:
                        count += 1
                # 홀수 열
                if j % 2 == 1:
                    if board[i][j] == 'W':
                        continue
                    else:
                        count += 1
    return count


# 맨 왼쪽 위 칸이 검정인 경우
def black_color(board, row, column):
    count = 0
    for i in range(row, 8 + row):
        for j in range(column, 8 + column):
            # 짝수 행
            if i % 2 == 0:
                # 짝수 열
                if j % 2 == 0:
                    if board[i][j] == 'B':
                        continue
                    else:
                        count += 1
                # 홀수 열
                if j % 2 == 1:
                    if board[i][j] == 'W':
                        continue
                    else:
                        count += 1
            # 홀수 행
            if i % 2 == 1:
                # 짝수 열
                if j % 2 == 0:
                    if board[i][j] == 'W':
                        continue
                    else:
                        count += 1
                # 홀수 열
                if j % 2 == 1:
                    if board[i][j] == 'B':
                        continue
                    else:
                        count += 1
    return count


n, m = map(int, input().split())

data = []
for _ in range(n):
    data.append(list(input()))

# board에서 나올 수 있는 체스판의 모든 경우의 수
for i in range(0, n - 7):
    for j in range(0, m - 7):
        # 맨 왼쪽 위칸이 검정색일 경우 혹은 흰색일 경우의 모든 경우의 수를
        # 체크하여 가장 색칠한 횟수가 적을 경우를 찾아냄
        result = min(result, black_color(data, i, j))
        result = min(result, white_color(data, i, j))

print(result)


{% endhighlight %}
