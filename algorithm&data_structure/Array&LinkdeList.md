# 배열과 연결리스트의 차이점을 서술하시오

## 답안
> 배열은 저장된 데이터들이 연속적으로 저장되어있는구조로 이로인해 인덱스를 통한 접근이 가능한  RandomAcess를 지원한다. 이러한 특성에 의해 테이터 탐섹에 대해 O(1)이라는 시간복잡도를 보여준다. 다만 배열을 중간이나 처음의 요소를 삽입 혹은 삭제할 시 O(n)이라는 시간복잡도를 보인다. 또한 크기에 대해 제약사항이 있어 메모리 공간을 낭비할 수도 있다.
> 연결리스트는 여러개의 노드들이 순차적으로 연결된 형태의 자료구조이며, 배열과는 다르게 연속적인 메모리공간을 사용하지 않기에, 각노드가 자신의 다음노드의 위치를 저장하는 포인터를 이용하여 각 요소를 순차적(Sequntial)으로 접근 가능하다. 따라서 특정 요소 접근시 O(n)이라는 시간복잡도를 가진다. 또한 배열과 다르게 각 요소가 다음 노드를 가리키는 포인터 공간을 가진다는 단점도 있다. 하지만 요소의 삽입과 삭제의 측면에서 배열보다 높은 O(1)의 성능을 보여주기에 삽입&삭제가 빈번히 일어나는 데이터의 경우 연결리스트가 더욱 적합한 자료형이라 볼수 있으며, 가변적인 크기를 가지고있어 메모리낭비를 방지할 수 있다.


## 자료

### 배열
- 데이터들이 연속된 메모리 공간에 저장되는 자료구조
- 메모리상에서 연속적으로 저장된 특성에 의해 index를 통한 접근이 용이함
- 배열의 크기는 처음생성될 때 정해지며, 이후에 변경할 수 없다.
	- 배열의 크기를 변경할 시 새로운 크기의 배열의 생성하여 해당배열에 기존의 배열의 내용을 복사하여 배열의 Ref를 새로운 배열을 가르키도록 하는 식으로 작동하기에 사실 배열의 크기를 변경할 수 없다.
- 기본적으로 컴파일 타임에 할당이 되므로 Stack영역에 생성된다.
- 시간복잡도
	-	탐색 : O(1)
	- 요소의 삽입 및 삭제 : 
		- 배열의 처음 또는 중간에 삽입 및 삭제 시 : O(n)
		- 배열의 끝에 삽입 및 삭제 시 : O(1)(단 배열의 크기를 재할당 하지 않아도 될 시)


### 연결리스트
- 연결리스트는 여러개의 노드들이 순차적으로 연결된 형태를 가진다.
	- 첫 번째 노드를 Head Node, 마지막 노드를 Tail Node라고 한다.
- 각 노드는 데이터와 다은 노드를 가르키는 포인터로 이루어져 있다.
- 배열과 달리 연속적인 메모리 공간을 사용하지 않는다.
- 배열과 달리 순차석(Sequntial)으로 요소에 접근해야하는 단점이 있지만 삽입과 삭제에선 배열보다 뛰어난 성능을 보여준다.
- 크기가 실행시간에 결정된다. (가변적인 크기를 가짐)
- 기본적으로 실행 시간에 할당이 되며, Heap영역에서 생성된다.
- 시간 복잡도
	- 탐색 : O(n)
	- 삽입 및 삭제 : O(1)(단 삽입 및 삭제 할 시 위치에 대한 data를 가진 경우)
		- 위치에 대한 데이터 없고, 리스트의 중간이나 끝에 삽입 및 삭제 할 시 : O(n)(탐색시간이 요구되므로, Tail Node의 위치에 대한 data가 있는 경우 끝에 삽입 시 O(1))


## 꼬리 질문

- 다양한 리스트의 형태
	- 원형 리스트
		- 하나의 노드에서 다른 모든 노드로의 접근이 쉬워짐
		- 노드의 삽입과 삭제가 단순 연결리스트보다 용이함
		- 반복적인 순회가 필요할 시 유용
		- 단 무한 Loop가 발생하지 않도록 주의하여 사용하여야 함

	- 이중 연결 리스트
		- 단반향 흐름을 가진 단순, 원형 리스트와 달리 양방향으로 노드접근이 가능함
		- 삽입 / 삭제 시 선행노드에 대한 data를 바로 구할 수 있음
		- 연속적인 데이터 탐색 시 비교적 높은 성능을 보여준다.
		- 단 구현 알고리즘이 복잡해지며, 이전노드를 지정하는 데이터를 추가적으로 저장하여야 한다.

- 배열과 연결 리스트에 유용한 자료 구조
	- 배열 : 주식 차트
	- 연결리스트 : 

- \[Java\] : Array와 ArrayList의 차이점
	Java의 ArrayList는 배열과 연결 리스트의 장점을 합친 자료형으로, 배열과 같이 Random Access가 가능하며, 연결리스트처럼 크기가 가변적이다. 배열과의 차이점중 중요한 내용은 앞서 말했듯 가변적인 크기를 가진다는 것이다. 세세한 차이점은 다음과 같다.
	구분 |Array|ArrayList
	--|--|--|
	크기 | 초기화 시 고정 | 초기화 시 따로 크기를 지정하지 않으며, 가변적임(요소 추가 시 공간이 부족하면 배열의 크기를 늘리거나 공간적 제약이 있는 경우 새로운 크기의 배열을 할당받아 복사하는 식으로 크기를 변결할 수 있음)
	탐색 | O(1) | O(1)
	요소 추가 | 여유공간이 있을때 가능, O(1) | O(1), 단 여유공간이 없을 시 O(n)
	요소 삭제 |O(n) | O(n)
	Type | Primitive, Object(Ref) | Object(Primitive Type의 데이터를 넣는 경우 자동으로 객체로 형변환 진행), Generic
	다차원 배열 | O | X


## 참고자료


학과 수업(자료구조, 박창현)

개발 블로그([humblechoi](https://velog.io/@humblechoi/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%EB%A9%B4%EC%A0%91%EC%A7%88%EB%AC%B8-%EB%AA%A8%EC%9D%8C),
[Hongcoding](https://velog.io/@humblechoi/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%EB%A9%B4%EC%A0%91%EC%A7%88%EB%AC%B8-%EB%AA%A8%EC%9D%8C))