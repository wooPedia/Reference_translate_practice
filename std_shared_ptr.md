<a href="https://en.cppreference.com/w/cpp/memory/shared_ptr" target = "_blank">출처: cppreference</a>

<b>오역이 있을 수 있으니 잘못된 부분이 있다면 꼭 알려주세요!</b>

<br>

## 원어

std::shared_ptr is a smart pointer that retains shared ownership of an object through a pointer. Several shared_ptr objects may own the same object. The object is destroyed and its memory deallocated when either of the following happens:

- the last remaining shared_ptr owning the object is destroyed;
- the last remaining shared_ptr owning the object is assigned another pointer via operator= or reset().

<br>
The object is destroyed using delete-expression or a custom deleter that is supplied to shared_ptr during construction.

A shared_ptr can share ownership of an object while storing a pointer to another object. This feature can be used to point to member objects while owning the object they belong to. The stored pointer is the one accessed by get(), the dereference and the comparison operators. The managed pointer is the one passed to the deleter when use count reaches zero.

A shared_ptr may also own no objects, in which case it is called empty ~~(an empty shared_ptr may have a non-null stored pointer if the aliasing constructor was used to create it).~~

~~All specializations of shared_ptr meet the requirements of CopyConstructible, CopyAssignable, and LessThanComparable and are contextually convertible to bool.~~

All member functions (including copy constructor and copy assignment) can be called by multiple threads on different instances of shared_ptr without additional synchronization even if these instances are copies and share ownership of the same object. If multiple threads of execution access the same shared_ptr without synchronization and any of those accesses uses a non-const member function of shared_ptr then a data race will occur; the shared_ptr overloads of atomic functions can be used to prevent the data race.


<br>

## 해석
std::shared_ptr는 하나의 포인터 객체(원시 포인터)에 대해 공유 가능한 소유권을 가지는 스마트 포인터이다. 여러개의 공유 포인터 객체가 동일한 객체(원시 포인터)를 소유할 수 있다. 객체와 그 메모리는 다음과 같은 상황에서 소멸되고 해제된다. <br>

- 객체를 소유한 마지막 공유 포인터가 소멸될 경우
- 객체를 소유한 마지막 공유 포인터에 대입 연산자 또는 reset() 함수를 통해 다른 객체가 할당되었을 경우

<br>
객체는 delete 또는 shared_ptr 생성 과정에서 전달된 커스텀된 deleter를 통해 소멸된다.
<br>

공유 포인터는 또 다른 객체에 대한 원시 포인터를 저장하면서 하나의 객체에 대한 소유권을 공유할 수 있다. 이 특징은 그들이 속한 객체를 소유하면서 멤버 객체들을 가리키는데 사용될 수 있다. 저장된 원시 포인터는 get 함수, 역참조, 관계 연산자에 의해 접근될 수 있다. 관리되는 포인터는 count가 0에 도달할 때 deleter에게 전달된다.
<br>
공유 포인터는 어떠한 객체도 소유하지 않을 수 있으며 empty라고 불린다.

모든 멤버 함수(복사 생성자, 복사 할당 연산자를 포함한)는 해당 인스턴스들이 복사되거나 똑같은 객체 소유권을 공유한다해도 다른 공유 포인터의 인스턴스에서 추가적인 동기화 없이 멀티 스레드에 의해 호출될 수 있다. 만약 멀티 실행 스레드가 동기화없이 동일한 공유 포인터에 접근하는 경우 또는 해당 접근 중 어떤 것이라도 non-const 멤버 함수를 사용한다면 data race(race condition, 경쟁 상태)가 발생할 수 있다. 아토믹 함수가 오버로드된 공유 포인터는 data race를 방지하기위해 사용될 수 있다.   