# ArrayList와 LinkedList의 차이점

ArrayList 및 LinkedList는 Java List 인터페이스의 가장 일반적으로 사용 되는 구현 중 두 가지입니다. ArrayList와 LinkedList의 주요 차이점은 기본 데이터 구조와 성능 특성에 있습니다.

### ArrayList

ArrayList는 기본 데이터 구조로 동적 배열을 사용합니다. 목록 끝에 임의 액세스 및 삽입에 적합하지만 목록의 시작 부분이나 중간에 요소를 삽입하는 데는 느립니다.&#x20;

ArrayList는 배열에 의해 지원되므로 ArrayList가 커질 때 새 배열을 만들고 이전 배열의 모든 요소를 ​​새 배열로 복사해야 합니다. 이 작업은 목록의 요소 수에 비례하여 시간이 걸립니다.

### LinkedList

반면에 LinkedList는 기본 데이터 구조로 이중 연결 목록을 사용합니다. 연결된 목록은 일련의 노드로 구성되며 각 노드에는 개체에 대한 참조와 목록의 다음 노드에 대한 참조가 포함됩니다.&#x20;

주변 노드의 참조만 업데이트하면 되므로 LinkedList 중간에 요소를 매우 빠르게 삽입하고 삭제할 수 있습니다. 그러나 인덱스로 요소에 액세스하는 것은 특정 노드에 도달하기 위해 처음부터 목록을 탐색해야 하기 때문에 느립니다.

### 결론

* ArrayList는 인덱스로 요소에 빠르게 액세스해야 하고, 요소를 자주 삽입하거나 삭제할 필요가 없는 경우 좋은 선택인 반면&#x20;
* LinkedList는 요소를 자주 삽입하거나 삭제해야 하지만 인덱스로 요소에 빠르게 액세스할 필요가 없는 경우 좋은 선택입니다.
