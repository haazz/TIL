람다 표현식 (Lambda expression)은 함수형 프로그래밍을 구성하기 위한 함수식이다.
메서드의 이름과 반환값을 생략할 수 있고 이를 통해 자바 코드를 간결하게 만들 수 있는 장점이 있다.
이러한 특징으로 람다식을 익명 함수 (anonymous function)이라고도 부른다.

```java
int add(int x, int y) {
    return x + y;
}

(int x, int y) -> {
	return x + y;
};

(x, y) -> {
	return x + y;
};

(x, y) -> x + y;
```

장점

- 간결성·가독성
- Stream, CompletableFuture, map/filter/reduce 등 선언적 스타일에 활용 가능

단점 (한계)

- 람다는 문서화 할 수 없다.
  - 람다가 길거나 읽기 어렵다면 쓰지 않는 방향으로 리팩토링을 고려해 보자
- 디버깅이 까다롭다.
  - 콜 스택 (call stack) 추적이 어렵고
- 과용 시 가독성이 저하될 수 있다.
- stream에서 람다를 사용할 시 for문 보다 성능이 떨어진다.
- 재귀 함수를 구축하는 경우에는 부적합하다.

<br/>
참고자료: https://inpa.tistory.com/entry/☕-Lambda-Expression#람다식과_함수형_인터페이스
