<a href="https://en.cppreference.com/w/cpp/container/map" target="_blank">출처: cppreference</a>

<b>오역이 있을 수 있으니 잘못된 부분이 있다면 꼭 알려주세요!</b>

<br>

## 원어

std::map is a sorted associative container that contains key-value pairs with unique keys. Keys are sorted by using the comparison function Compare. Search, removal, and insertion operations have logarithmic complexity. Maps are usually implemented as red-black trees.

Everywhere the standard library uses the Compare requirements, uniqueness is determined by using the equivalence relation. In imprecise terms, two objects a and b are considered equivalent (not unique) if neither compares less than the other: !comp(a, b) && !comp(b, a).

~~std::map meets the requirements of Container, AllocatorAwareContainer, AssociativeContainer and ReversibleContainer.~~


<br>

## 해석
std::map은 <유일한 key와, value>를 pairs(쌍)으로 가지는 정렬된 연관 컨테이너이다. key는 비교 함수인 (default) Compare 또는 커스터마이즈된 Compare 함수를 사용함으로써 정렬된다. 탐색, 삭제, 삽입 연산들은 로그의 시간 복잡도를 가진다. map은 보통 red-black-tree로 구현된다.   

표준 라이브러리가 Compare 함수를 사용하는 모든 곳에선 동치 관계를 적용함으로써 유일성을 판단한다. 만약 객체 a와 b를 비교할 경우, 두 compare 모두 서로보다 적지 않다면 객체 a와 b는 동일하다고 판단한다.(= 유일하지 않다)
: !comp(a, b) && !comp(b, a).
