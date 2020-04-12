<a href="https://en.cppreference.com/w/cpp/container/unordered_set" target = "_blank">출처: cppreference</a>

<b>오역이 있을 수 있으니 잘못된 부분이 있다면 꼭 알려주세요!</b>

<br>

## 원어
		
Unordered set is an associative container that contains a set of unique objects of type Key. Search, insertion, and removal have average constant-time complexity.

Internally, the elements are not sorted in any particular order, but organized into buckets. Which bucket an element is placed into depends entirely on the hash of its value. This allows fast access to individual elements, since once a hash is computed, it refers to the exact bucket the element is placed into.

Container elements may not be modified (even by non const iterators) since modification could change an element's hash and corrupt the container.

~~std::unordered_set meets the requirements of Container, AllocatorAwareContainer, UnorderedAssociativeContainer.~~


<br>

## 해석
unordered_set은 unique(유일한) key 개체 집합을 포함하는 연관 컨테이너이다. 검색, 삽입, 삭제 연산은 평균 상수 시간의 복잡도를 가진다.
<br>

내부적으로 요소들은 특정한 순서로 정렬되지 않고 버킷에 저장된다. 요소가 저장되는 버킷의 위치는 전적으로 해시값에 의존한다. 해시가 계산되면 요소가 저장된 정확한 버킷을 참조하기 때문에 임의의 원소에 빠르게 접근할 수 있다. 
<br>

컨테이너의 요소(key)들은 요소의 해시값이 변경되거나 컨테이너가 손상될 수 있기 때문에 수정되지 않을 것이다. (non-const 타입의 반복자라 하더라도)

