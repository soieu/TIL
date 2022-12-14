# [algorithm] 0x15 해시


## 1. 해시?

- 해시 : key에 대응되는 value를 저장하는 자료구조
- 해시함수 : 임이 길의의 데이터를 고정된 길이의 데이터로 대응시키는 함수.
- 

## 2. 해시의 시간 복잡도

- insert : O(1)
- erase : O(1)
- find : O(1)
- update : O(1)

## 3. 해시충돌

- 해시 충돌 : 서로 다른 key가 같은 해시 값을가지게 될 경우 생기는 문제를 해시 충돌이라한다. 해시 충돌을 어떻게  처리하느냐에 따라 해시의 성능이 결정된다.

## 4. 해시충돌 - 충돌회피 1  : Chaining

- Chaining : 각 인덱스마다 연결 리스트를 둬 충돌을 회피하는 방법. insert가 발생할 경우 해당 index의 연결 리스트에 값을 추가한다.
- STL 해시 자료구조 사용.
- 단점 : 최악의 경우 (ex 모든 키의 해시 값이 모두 동일한 경우) 시간복잡도가 O(N)이 된다.
- → 해시의 성능을 좋아지게 하기 : 해시 값이 균등하게 펴져야함. 따라서 주어진 데이터에 대한 좋은 해시함수를 지정해야함.

## 5. 해시충돌 - 충돌회피 2 : Open Addressing

- Open Addressing : 해시 값이 채워져있는 경우 다음 칸으로 넘어가 해시값을 쓴다.
- erase에서 주의 !! -dummy값 사용.
- 종류
    1. **Linear Probing** : 충돌 발생 시 오른쪽으로 1칸씩 이동
        - 장점 : cache hit rate가 높다
        - 단점 : clustering이 생겨 성능에 영향을 줄 수 있다.
    2. **Quadratic Probing** : 충돌 발생 시 기준에서 오른쪽으로 1, 4($=2^2$), 9($=3^2$), … 칸 씩 이동하는 방식
        - 장점 : cache hit rate 보통. clustering 어느정도 회피 가능
        - 단점 : 해시 값이 같을 경우 여전히 clustering 발생.
    3. **Double Hashing** : 충돌 발생 시 이동할 칸의 수를 새로운 `해시 함수`로 계산하는 방식
        - 장점 : clustering을 효과적으로 회피 가능
        - 단점 : cache hit rate 낮음

## 6. 한번 생각해 보자

- 해시는 뭔가? 해시 함수는 또 뭔가?
- 해시 충돌이 일어나면 왜 안좋은가?
- 해시 충돌 회피하는 방법들에 대해 얘기해보자
