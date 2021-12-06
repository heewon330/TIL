```python
n= ord(input()) # ord(c)는 문자 c를 10진수로 변환
print(n)
```

```python
c=int(input())
print(chr(c))  #chr(c)는 정수를 유니코드로 변환
```

```python
n=input().split()
a=int(n[0])
b=int(n[1])
print(a-b) # 띄어쓰기로 구분한 정수 두개 값 계산
```

```
'{:x}'.format(10)
```

```python
a,b=input().split()
print(f'{float(a)/float(b):.3f}') #소수점 3자리까지
```



- 2개의 정수값이 입력될 때, 그 불 값(True/False) 이 서로 다를 때에만 True 를 출력하는 프로그램

- 참 거짓이 서로 다를 때에만 True 로 계산하는 논리연산을 **XOR(exclusive or, 배타적 논리합) 연산**이라고도 부른다.

```python
a,b = map(int,input().split())
a=bool(a)
b=bool(b)

print((a and not b) or (not a and b))
```

결과값 :   1  0

​                 True



```python
n=int(input())

while n!=0:
    print(n-1)
    
    n-=1
    
    if n==0:
        break
```



```python
while True:
 n=int(input())
 if n != 0:
        print(n)
 else:
    break
```

결과값 : 5

 			4

​			3

​			2

​			1



```python
n = 'a'     #처음 조건 검사를 통과하기 위해 q 아닌 값을 임의로 저장
while n!='q' :
  n = input()
  if n!='q' :
    print(n)

  else:
      print(n)
      break
```



6079번)

1, 2, 3 ... 을 계속 더해 나갈 때,
그 합이 입력한 정수(0 ~ 1000)보다 같거나 작을 때까지만
계속 더하는 프로그램을 작성해보자.

즉, 1부터 n까지 정수를 계속 더해 나간다고 할 때,
어디까지 더해야 입력한 수보다 같거나 커지는 지를 알아보고자하는 문제이다.

```python
n=int(input())
sum=0

for i in range(1,n+1):
 sum+=i
 
 if sum>=n:
    
      print(i)
      break
```



6082번) 3,6,9게임

```
n=int(input())

for i in range(1, n+1) :
 if i%10==3 or i%10==6 or i%10==9 :
  print("X",end=' ')  #출력 후 공백문자(빈칸, ' ')로 끝냄

 else :
     print(i,end=' ')
```



6083번) 픽셀 rgb

```python
a,c,d = map(int,input().split())
n=0
for r in range(0,a):
    for g in range(0,c):
        for b in range(0,d):
            print(r,g,b)
            n+=1
print(n)
```

