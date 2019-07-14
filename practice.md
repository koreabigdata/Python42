*할당문 
기본 : 식별자 = 표현식 ( 하나의 값으로 축약 가능한 것)
```
1.	a = 1+2
2.	a,b = 1,2
a, b = b, a   swap
3.	a = b = 1  #mutable일 때 같이 바뀌므로 조심
4.	* 2가지
```
①	나머지 할당
a , *b = 1,2,3,4
a  1, b = [2,3,4] 
②	*a, = 1,2,3,4,5  a가 list 타입으로 나온다. (tuple을 list로 변신시킬 때 사용)

-	tuple 
①	a = (1,2,3,)  끝에 , 있는게 좋음! 
    a=(1)은 숫자이기 때문
②	a = 1,  괄호가 없어도 튜플

-	list 
①	list(‘정영서’)	#list를 쪼개줄 때 사용
[‘정’, ‘영’, ‘서]
②	append, extend
a.append(2)
a.extend([3])
 결과값(out)이 바로 나오지 않음. 
③	Mutable일 때 조심해야 하는 것들.  ######이게 왜 네가지 ? 
 자기 자신은 변하지만 리턴 값은 주지 않는다.
 안좋은 예시. 리스트에 원소 값 하나만 넣고 싶지만, 실행할때마다 추가됨
def s(t,L=[]):
    L.append(t)
    return L
④	Pop : 마지막 원소 빼줌.
다시 프린트해보면 stack처럼 마지막 원소 사라져 있음
⑤	+연산자 
a = [1,2,3]
b = [4,5,6]
a+b
[1,2,3,4,5,6]
⑥	* 연산자 : 반복
a = [1,2,3]
a*3
[1,2,3,1,2,3,1,2,3]

-	Set 
①	a = {1,2,3}
②	연산을 지원해 줌
차집합 : a – {2} (자기 자신이 변하는건 아님. 연산 결과만 리턴해줌)
공집합 : a & {2}
대칭차집합 : a^{2}
합집합 : a|b

-	Dictionary 
①	{‘key’ : value}
②	Dictionary는 mutable이다
③	{} : 공집합X dictionary
④	숫자는 key로 올 수 있다
⑤	Key : immutable만 올 수 있다
⑥	Value : mutable이든 immutable이든 상관X
⑦	Dictionary view (설정 안하면 key값만 나옴)
key만 보여주고 싶다  {~}.keys()
value만 보여주고 싶다  {~}.values()
key, value 둘다   items.values()
⑧	Key 에러 방지 (key가 없을 때 나는 에러)
x.get(‘x’ , ‘error’) : x란 dictionary에 x란 key가 없으면 ‘error’를 출력
ex) x = {'a':1,'b':2}
   x.get('x',3)
   3
⑨	from collections import OrderedDict
 정렬을 유지하도록 하는 딕셔너리
