
# 자바 핵심 개념 정리 1
<details>
<summary>Java에서 제공하는 원시 타입들에 무엇이 있고, 각각 몇 바이트를 차지하나요?</summary>
<div markdown="1">   
<br>

자바의 원시 타입 (Primitive Type): 실제 데이터의 값을 저장하는 타입으로 CPU나 운영체제에 따라 크기가 변하지 않는다.<br>
* <U>논리형</U>
    * boolean (1byte)
* <U>문자형</U>
    * char (2byte)
* <U>정수형</U>
    * byte (1byte)
    * short (2byte)
    * int (4byte)
    * long (8byte)
* <U>실수형</U>
    * float (4byte)
    * double (8byte)
</div>
</details>
<br>

<details>
<summary>오버라이딩(OverRiding)과 오버로딩(OverLoading)에 대해 설명해주세요.</summary>
<div markdown="1">
<br>

* <U>오버라이딩(Overriding)</U>: 부모 클래스의 메서드를 자식 클래스에서 재정의하는 것
* <U>오버로딩(Overloading)</U>: 하나의 클래스 내에서 같은 이름의 메서드를 매개변수의 타입과 개수를 다르게 하여 여러 개 구현하는 것
</div>
</details>
<br>

<details>
<summary>객체지향 프로그래밍(OOP)에 대해 설명해주세요</summary>
<div markdown="1">
<br>

* <U>객체 지향 프로그래밍</U>: 실제 세계의 물체 혹은 데이터를 상태와 행위를 가진 객체로 표현하고, 그 객체들 간의 관계와 상호작용을 프로그램으로 나타내는 프로그래밍 방법<br>
* 객체 지향 프로그래밍의 4가지 특징

    * <U>캡슐화</U> (Encapsulation) : 서로 연관된 필드와 메서드들을 "클래스" 라고 하는 하나의 캡슐 안에 묶어 외부로부터 정보를 보호하고 은닉하는 것
    * <U>상속</U> (Inheritance) : 상위 클래스의 속성과 행위를 하위 클래스가 물려받는 것
    * <U>추상화</U> (Abstraction) : 객체의 공통된 속성과 행위만을 추출해내는 것
    * <U>다형성</U> (Polymorphism) : 같은 이름의 메서드가 클래스 혹은 객체에 따라서 다르게 구현되는 것. 사례로 오버라이딩과 오버로이딩이 존재한다.

</div>
</details>
<br>

<details>
<summary>추상 클래스와 인터페이스에 대해 설명해주시고, 차이에 대해 설명해주세요.</summary>
<div markdown="1">
<br>

* 추상 메서드: 구현부가 작성되지 않은 메서드<br>
  ```public abstract void example();```
  <br><br>
* 추상 클래스: 추상 메서드를 선언해 상속을 통해 자식 클래스에서 완성하도록 유도하는 클래스
    * ```abstract``` 라는 예약어를 통해 추상 클래스임을 나타낸다.
    * 추상 메서드 외에 일반 클래스와 같이 일반적인 필드, 메서드, 생성자를 가질 수 있다.
    * 상속 키워드로 ```extends``` 를 사용한다.
    * 다중 상속은 불가능하고 단일 상속만 허용한다.

* 인터페이스: 오직 추상 메서드와 상수(static final) 만을 가지고 있는 것을 인터페이스라고 한다.
    * ```interface``` 키워드를 사용한다.
    * 일반 메서드 또는 멤버 변수를 가질 수 없다.
    * 인터페이스의 모든 멤버 변수는 public static final 이어야 하며, 생략 가능하다.
    * 인터페이스의 모든 메서드는 public abstract 이어야 하며, 생략 가능하다.
    * Java8 부터는 static, default 메서드를 사용 가능하다.
    * 상속 키워드로 ```implements``` 를 사용한다.
    * 클래스에 다중 구현을 지원하며, 인터페이스 끼리는 다중 상속을 지원한다.

* 추상 클래스와 인터페이스의 공통점
    1. 객체를 생성할 수 없다. (인스턴스화 불가능)
    2. 추상 메서드를 포함한다.
    3. 가지고 있는 추상 메서드를 구현하도록 강제한다.

* 추상 클래스 vs 인터페이스
    1. 사용 키워드: ```abstract``` vs ```interface```
    2. 사용 가능 변수: ```제한 없음``` vs ```static final (상수)```
    3. 사용 가능 접근 제어자: ```제한 없음``` vs ```public```
    4. 상속 키워드: ```extends``` vs ```implements```
    5. 다중 상속: ```불가능``` vs ```가능```
    6. 사용 목적: ```상속을 통한 기능 확장``` vs ```구현 객체의 동일한 기능 실행 보장```

</div>
</details>
<br>

<details>
<summary>가비지 컬렉션(gc)란 무엇일까요?</summary>
<div markdown="1">
<br>

- 가비지 컬렉션: 자바의 메모리 관리 방법 중 하나로, JVM의 heap 영역에서 동적으로 할당했던 메모리 영역 중 필요없게 된 메모리 영역을 주기적으로 삭제하는 프로세스

- 장점: 자동으로 메모리를 관리해주므로 개발자가 이를 관리할 필요가 없어지며, 메모리 누수를 방지해준다.
- 단점: 메모리가 해제되는 시점을 정확히 알지 못한다. 가비지 컬렉션이 동작하는 동안 다른 동작들이 자꾸 멈추는 등의 오버헤드가 발생하고, 성능 하락으로 이어진다.
</div>
</details>
<br>

<details>
<summary>JVM의 동작 방식에 대해 설명해 주세요.</summary>
<div markdown="1">
<br>

1. 작성된 자바 소스코드(.java) 파일이 자바 컴파일러를 통해 자바 바이트 코드(.class) 로 컴파일된다.
2. 컴파일된 바이트 코드를 클래스 로더에게 전달
3. 클래스 로더는 동적 로딩을 통해 필요한 클래스와 객체들을 로딩 및 링크하여 runtime data area 에 업로드
4. Execution Engine 에서 JVM 메모리에 올라온 바이트 코드를 해석하여 bynary code 생성
5. 바이너리 코드가 runtime data area에 배치되어 수행됨
</div>
</details>
<br>

<details>
<summary>불변 객체란 무엇이고, final은 무엇일까요? 사용하는 이유와 함께 설명해주세요.</summary>
<div markdown="1">
<br>

- 불변 객체: 객체 생성 이후로 내부의 상태를 바꿀 수 없는 객체.   
  read-only 메소드만을 제공해야한다. 객체 내부의 상태를 제공하는 메소드(getter 등) 을 제공하지 않거나 제공하는 경우 방어적 복사(defensive-copy)를 통해 제공한다.   
  자바의 대표적인 불변 객체로는 String이 존재한다.

- final: 자바에서 불변성을 확보할 수 있도록 제공하는 키워드.   
  클래스나 변수에 final 을 붙이면 처음 정의된 상태가 변하지 않는다는 것을 보장한다는 의미이다.

- 사용하는 이유
    1. Thread-Safe 하여 병렬 프로그래밍에 유용하며 동기화를 고려하지 않아도 된다.: 일반적으로 멀티 스레드 환경에서 동기화 문제는 공유자원에 동시적으로 쓰기(write) 때문인데, 공유 자원이 불변이라면 동기화를 고려하지 않아도 된다.   
       *thread-safe는 멀티 스레드 프로그래밍에서 일반적으로 어떤 함수나 변수, 혹은 객체가 여러 스레드로부터 동시에 접근이 이루어져도 프로그램의 실행에 문제가 없음을 의미한다.
    2. 실패 원자적인(Failure Atomic) 메소드를 만들 수 있다.: 불변 객체는 항상 같은 값을 유지하기 때문에 예외가 발생하여도 메소드 호출 전의 상태를 유지 가능하며, 오류가 발생하지 않은 것처럼 다음 로직을 처리하는 것이 가능하다
    3. Cache나 Map, Set 등의 요소로 활용하기에 더욱 적합하다.: cache나 map, set 등으로 사용되는 객체가 변경되었다면 이를 갱신하는 작업을 추가로 해주어야하지만, 불변 객체의 경우 이와 같은 부가 작업을 고려하지 않아도 된다.
    4. 부수 효과(Side Effect)를 피해 오류가능성을 최소화 할 수 있다.: 만약 객체의 Setter가 구현되어 있어 여러 메소드에서 객체의 값이 변경된다면 객체를 예측하기 어려워진다. 객체의 바뀐 상태를 파악하려면 여러 메소드를 살펴보아야하고, 이러한 부분은 유지보수성을 떨어뜨린다. 불변 객체의 경우 값의 수정이 불가하므로 변경 가능성이 적다. 따라서 메소드들이 호출되어도 객체의 상태가 유지되기 때문에 안전하게 객체를 다시 사용할 수 있어 최종적으로 오류를 줄여 유지보수성이 높은 코드를 만들어준다.    
       *부수 효과: 함수 내에서의 어떤 구현이 함수 외부에 영향을 끼치는 경우 해당 함수는 부수 효과가 있다고 이야기한다.
    5. 다른 사람이 작성한 함수를 예측가능하며 안전하게 사용할 수 있다.: 불변성이 보장된 메서드라면 다른 사람이 개발한 메서드를 위험 없이 사용 가능하다.
    6. 가비지 컬렉션의 성능을 높일 수 있다.: 가변 객체를 사용하면 내부 인스턴스 필드를 변경할 수 있으므로 참조가 끊어진 객체들이 컨테이너와 별개로 GC의 대상이 된다. 불변 객체를 사용할 시 내부 인스턴스 필드를 변경할 수 없으므로 컨테이너를 더이상 사용하지 않게 되면 내부 인스턴스 필드까지 한번에 GC를 수행할 수 있다. 따라서 불변 객체를 사용하면 가비지 컬렉터가 스캔해야하는 메모리 영역과 GC의 빈도 수가 줄어든다.
</div>
</details>
<br>

<details>
<summary>자바의 메모리 영역에 대해 설명해주세요.</summary>
<div markdown="1">
<br>

Run-time data area: JVM의 메모리 영역으로 자바 어플리케이션을 실행할 때 JVM 이 OS 로부터 할당받은 메모리 공간이다. 해당 공간은 크게 다음과 같이 나눠진다.

1. Method Area
   JVM 이 실행되면서 생기는 공간이다. Class 정보, 전역 변수 정보, Static 변수 정보가 저장되는 공간이다.
   모든 스레드에서 정보가 공유된다.
   Runtime constant pool 라고 하는 상수 정보가 저장되는 공간이 있다.
   JVM이 종료될 때까지 유지된다.
2. Heap Area
   new 연산자로 생성된 객체, Array와 같은 동적으로 생성된 데이터가 저장되는 공간
   Heap에 저장된 데이터는 GC가 처리하지 않는 한 소멸되지 않는다.
   Reference type의 데이터가 저장되는 공간
   힙의 참조 주소는 스택이 가지고 있고, 해당 객체를 통해서만 힙 영역에 있는 인스턴스를 핸들링할 수가 있다.
   모든 스레드에서 정보가 공유된다.
3. Stack Area
   기본 자료형을 생성할 때 저장되는 공간으로 임시적으로 사용되는 변수나 정보들이 저장된다.
   메서드가 호출될 때마다 생성하고, 메서드 실행이 끝나면 제거된다.
   스레드마다 하나씩 존재한다.
   힙 메모리 영역보다 비교적 빠르다.
4. PC Register
   명령어의 주소값이 저장되는 공간이다.
   스레드들은 자신만의 PC Register 를 가지고 있다.
5. Native Method Stack
   자바 외 언어로 작성된 네이티브 코드를 위한 메모리 영역이다.
</div>
</details>
<br>

<details>
<summary>new String()과 리터럴(" ")의 차이에 대해 설명해주세요.</summary>
<div markdown="1">
<br>

- new 연산자를 통해 문자열 객체를 생성하는 경우 메모리의 heap 영역에 할당된다.
- 리터럴을 이용한 경우 String constant pool 이라는 상수풀 영역에 할당된다.
- 메모리를 할당한 영역이 달라지므로 주소값 비교를 하면 false 가 나오게 된다.
</div>
</details>
<br>

<details>
<summary>⭐️ 추가 과제: 람다(lambda)에 대해 알아볼까요?</summary>
<div markdown="1">
<br>

- 람다 표현식: 함수형 프로그래밍을 구성하기 위한 함수식. 자바의 메서드를 간결한 함수식으로 표현한 것
- 원래 자바에서는 메서드를 표현하려면 클래스를 정의해야하지만, 람다식으로 표현하면 메서드의 이름과 반환값을 생략 가능하고 이를 변수에 넣어 자바 코드가 간결해지는 장점이 존재
- 람다식을 이름이 없는 함수, '익명 함수(anonymous function)' 이라고도 한다.
```java
//원래 메서드
int add(int x, int y){
    return x+y;
}

//람다 표현식 1
(int x, int y)->{
    return x+y;
}

//람다 표현식 2 매개변수 타입 생략
(x,y) ->{
    return x+y;
}

//람다 표현식 3 중괄호, return 생략 (함수에 리턴문 한줄만 있을 경우)
(x,y) -> x+y;
```

</div>
</details>
<br>

<details>
<summary>⭐️ 추가 과제: 스트림(stream)에 대해 알아볼까요?</summary>
<div markdown="1">
<br>

- 스트림: Java 8부터 추가된 기술로 람다를 활용해 배열과 컬렉션을 함수형으로 간단하게 처리할 수 있는 기능이다.
- 스트림은 데이터 소스를 추상화하고, 데이터를 다루는 데 자주 사용되는 메서드를 정의해 놓아서 데이터 소스에 상관 없이 모두 같은 방식으로 다룰 수 있으므로 코드의 재사용성이 높아진다.
  <br>

- 스트림 중간 연산
    - Filtering: 스트림 내 요소들을 하나씩 평가해서 걸러내는 작업
    - Mapping: 스트림 내 요소들을 하나씩 특정 값으로 변환하는 작업
    - Sorting: 스트림 내 요소들을 정렬하는 작업. Comparator 사용

- 스트림 최종 연산
    - Calculating: 기본형 타입을 사용하는 경우 스트림 내 요소들로 min,max,sum,avg 등을 구하는 연산 수행 가능
    - Reduction: 스트림의 요소를 하나씩 줄여가며 누적 연산을 수행
    - Collecting: 스트림의 요소를 원하는 자료형으로 반환
    - Matching: 특정 조건을 만족하는 요소가 있는지 체크한 결과를 반환
    - Iterating: forEach로 스트림을 돌면서 실행되는 작업
    - Finding: 스트림에서 하나의 요소를 반환
</div>
</details>
<br>
