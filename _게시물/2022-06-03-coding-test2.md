'''
그리디 알고리즘
'현재 상황에서 지금 당장 좋아보이는 아이디어를 고르는 방법'
최소한의 아이디어 -> 정당성(최적의 해) 검증

* 문제 유형을 파악하기 어렵다 -> 그리디 알고리즘을 의심
직관적인 해결 아이디어를 고려 -> 정당성 검증 
'''

'''
예제 문제 1 -> 거스름돈
N을 0으로 만드는 최소한의 count 값을 구하라

화폐 종류(k)만큼 반복 수행
코드의 시간 복잡도 -> O(K)
'''

n = 1260
count = 0

# 큰 단위의 화폐부터 차례로 확인
coin_types = [500, 100, 50, 10]

for coin in coin_types:
  count = count + n // coin # 해당 화폐로 거슬러 줄 수 있는 동전 개수 셈
  n = n % coin # 남은 금액 최신화

print(count)


'''
실전 문제 2 -> 큰 수의 법칙
배열의 크기 n / 숫자가 더해지는 횟수 m / 연속으로 더하는 한계 k
배열의 특정한 인덱스에 해당하는 수가 연속해서 k번을 초과해서 더해질 수 없음.

해결 아이디어
가장 큰 수 k번 더하기 -> 두 번째 큰 수를 1번 더하기 -> 가장 큰 수 k번 더하기

입력 값 : 5 8 3 / 2 4 6 4 6 -> 정답 : 46
'''

# N, M, K를 공백으로 구분하여 입력 (첫 번째 줄)
n, m, k = map(int, input().split())
# N개의 수를 공백으로 구분하여 입력 받기 (두 번째 줄)
data = list(map(int, input().split()))

data.sort(reverse=True) # 입력 값 '내림차순' 정렬
first = data[0] # 가장 큰 값
second = data[1] # 두 번째 큰 값

result = 0

while True:
  for i in range(k): # 가장 큰 수 3번 더하기
      if m == 0:
        break
      result += first
      m = m - 1 # 더했으니 1 감소
  if m == 0: # m이 0이라면 반복문 탈출
    break
  result += second # 두 번째 큰 수 한 번 더하기
  m -= -1 # 더했으니 1 감소

print(result)
print(first, second, data)


n, m, k = map(int, input().split())
data = list(map(int, input().split()))

data.sort(reverse=True)
first = data[0]
second = data[1]

# 가장 큰 수가 더해지는 횟수 계산
# k+1이란 가장 큰 수(k개) + 두 번째 큰 수(1개)의 묶음
count = int(m / k+1) * k     # 몫
count = count + m % (k+1) # 나머지

result = 0
result += count * first # 가장 큰 수 더하기
result += (m-count)     # 두 번째 큰 수 더하기

print(result)



'''
실전 문제 3 -> 숫자 카드 게임
여러 개의 숫자 카드 중, 가장 높은 숫자가 쓰인 카드 한 장을 뽑는 것

1. 숫자 카드 n x m 형태
2. 먼저 뽑고자 하는 카드가 포함된 행을 선택
3. 그 다음 선택된 행에 포함된 카드들 중 가장 숫자가 낮은 카드 뽑아야 함
4. 처음에 카드를 골라낼 행을 선택할 때, 이후에 해당 행에서 가장 숫자가 낮은 카드를
뽑을 것을 고려하여 최종적으로 가장 높은 숫자의 카드를 뽑는 전략을  세워야 함

2 4
7 3 1 8
3 3 3 4
정답 -> 3
'''

# 예시 답안 1
n, m = map(int, input().split())

result = 0

for i in range(n):
  data = list(map(int, input().split()))
  min_value = min(data) # 현재 줄에서 가장 작은 숫자 찾기
  result = max(result, min_value) # 가장 작은 수들 중 가장 큰 값 찾기

print(result)


# 예시 답안 2
n, m = map(int, input().split())

result = 0

for i in range(n):
  data = list(map(int, input().split()))
  min_value = 10001
  for a in data:  # 현재 줄에서 가장 작은 값 찾기
    min_value = min(min_value, a)
  result = max(result, min_value) # 가장 작은 수들 중 가장 큰 값 찾기

print(result)


'''
실전 문제 4 -> 1이 될 때까지

어떠한 N이 1이 될 때까지 두 과정 중 하나를 반복 수행.
N을 1로 만드는 최소 횟수! 단, 두 번째 연산은 N이 k로 나눠질 때만 가능

1. N에서 1을 뺀다
2. N을 K로 나눈다

해결 아이디어
N이 k의 배수가 될 때까지 -1 -> n을 k로 나누기 (위 과정 반복)

입력 : 25 5 -> 2
'''

# 예시 답안 1
n, k = map(int, input().split())
result = 0 # 연산 횟수

# N이 K 이상이라면 k로 계속 나누기
while n >= k:
  while n % k != 0: # k로 나눠질 때까지 -1
    n -= 1
    result += 1
  # k로 나누기
  n = n // k
  result += 1

print(result)


# 예시 답안 2

n, k = map(int, input().split())
result = 0

while True:
  target = (n//k) * k # n이 k로 나눠 떨어지는 지점
  result += (n - target) # target 값까지 -1 뺀 횟수
  n = target
  if n < k:
    break
  n //= k
  result += 1

# 마지막으로 남은 수에 대하여 1씩 빼기
result += (n-1)
print(result)

