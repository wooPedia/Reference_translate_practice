<a href="https://en.cppreference.com/w/cpp/memory/weak_ptr" target = "_blank">출처: cppreference</a>

<b>오역이 있을 수 있으니 잘못된 부분이 있다면 꼭 알려주세요!</b>

<br>

## 원어
std::weak_ptr is a smart pointer that holds a non-owning ("weak") reference to an object that is managed by std::shared_ptr. It must be converted to std::shared_ptr in order to access the referenced object.

std::weak_ptr models temporary ownership: when an object needs to be accessed only if it exists, and it may be deleted at any time by someone else, std::weak_ptr is used to track the object, and it is converted to std::shared_ptr to assume temporary ownership. If the original std::shared_ptr is destroyed at this time, the object's lifetime is extended until the temporary std::shared_ptr is destroyed as well.

Another use for std::weak_ptr is to break reference cycles formed by objects managed by std::shared_ptr. If such cycle is orphaned (i,e. there are no outside shared pointers into the cycle), the shared_ptr reference counts cannot reach zero and the memory is leaked. To prevent this, one of the pointers in the cycle can be made weak.



<br>

## 해석
std::weak_ptr는 shared_ptr가 관리하는 객체에 대한 비소유적인 weak-reference(약한 참조)를 가지는 스마트 포인터이다. 참조되는 객체에 접근하기 위해선 반드시 shared_ptr로 변환해야 한다. 
<br>
<br>
weak_ptr는 임시 소유권을 만든다: 객체는 존재할 때만 접근되어야 하고, 객체가 누군가에 의해 언제라도 삭제될 수 있다면, 해당 객체를 추적하기 위해 weak_ptr을 사용하고, 임시 소유권을 취하기 위해 shared_ptr로 변환된다. 만약 기존 공유 포인터가 이 때 소멸된다면, 해당 객체의 lifetime은 또한 변환된 임시 공유 포인터가 소멸될 때까지 유지된다.
<br>
<br>
weak_ptr의 또 다른 용도는 공유 포인터에 의해 관리되는 객체의 순환 참조를 멈추기 위함이다. 만약 이와 같은 순환이 고립된다면(남아있다면)(예를 들어 해당 순환에 접근할 공유 포인터가 없을 경우), 공유 포인터의 참조 카운트는 0에 도달할 수 없으며 이는 메모리 누수이다. 이를 방지하기 위해 해당 순환에서 포인터들 중 하나가 weak_ptr가 될 수 있다.
