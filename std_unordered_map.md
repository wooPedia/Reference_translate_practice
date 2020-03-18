<a href="https://en.cppreference.com/w/cpp/container/unordered_map" target = "_blank">출처: cppreference</a>

<b>오역이 있을 수 있으니 잘못된 부분이 있다면 꼭 알려주세요!</b>

<br>

## 원어

Unordered map is an associative container that contains key-value pairs with unique keys. Search, insertion, and removal of elements have average constant-time complexity.

Internally, the elements are not sorted in any particular order, but organized into buckets. Which bucket an element is placed into depends entirely on the hash of its key. This allows fast access to individual elements, since once the hash is computed, it refers to the exact bucket the element is placed into.

~~std::unordered_map meets the requirements of Container, AllocatorAwareContainer, UnorderedAssociativeContainer.~~


<br>

## 해석
Unordered map은 unique(유일)한 key를 가진 key-value 쌍을 포함하는 연관 배열이다. 요소의 검색, 삽입, 삭제 연산은 평균적으로 상수 시간의 복잡도를 가진다. 
<br>
<br>
내부적으로, 요소들은 따로 정렬되지 않고 bucket에 저장된다. 요소가 저장되는 bucket은 전적으로 key의 해시 값에 의해 결정된다. 해시가 계산되면, 그 결과는 요소가 저장된 버킷을 참조하기 때문에 각각의 요소로의 빠른 접근이 가능하다.     