Java의 Optional<T>는 값이 있을 수도, 없을 수도 있음을 타입 수준에서 표현하고 NPE를 줄이는 역할을 한다.

# 사용

1. 값이 없을 수 있음을 반환타입으로 표현

```java
Optional<User> findById(long id);
```

2. 체이닝 변환/검증 파이프라인이 필요할 떄

```java
Optional.ofNullable(req.getEmail())
        .filter(EmailValidator::isValid)
        .map(String::toLowerCase)
        .ifPresent(service::register);

```

3. 컬렉션/스트림과 결합해 플로우를 만들 때

```java
List<String> names = users.stream()
    .map(User::getNameOptional)
    .flatMap(Optional::stream)
    .toList();
```

# 안티 패턴

1. Optional 변수에 null을 할당하지 않는다.
   빈 값으로 Optional을 만들려면 Optional.empty()로 객체를 생성해야 합니다.

2. Optional을 필드 타입, 메소드 인자로 사용하지 않는다
   Optional은 메소드의 리턴 타입으로 사용하기 위한 용도로 설계되었기 때문에, Optional을 클래스의 필드 혹은 메소드 인자로 선언하는 것은 잘못된 사용 방식이다.

3. 빈 컬렉션이나 배열을 나타낼 때는 Optional을 사용하지 않는다.
   빈 컬렉션을 리턴하고 자 하는 경우는 Optional을 사용할 것이 아니라, 빈 컬렉션을 리턴하는 것이 올바른 사용 방식입니다.
   ArrayList()나 HashMap() 등은 최초 객체를 생성하면 비어있는 컬렉션이 생성이 되므로 이를 사용해서 리턴하면 됩니다.

4. 원시 타입을 값으로 가지는 Optional이 필요할 때는 원시 타입 용도로 만들어진 클래스를 사용한다.
   원시 타입(primitive type)을 Optional로 사용해야 할 때는 Wrapper 클래스로 된 Optional 클래스를 사용하지 말고, 원시 타입 용도로 만들어진 OptionalInt, OptionalLong, OptionalDouble 형태의 클래스를 사용하는 것이 성능 측면에서 유리합니다.
   또한 Optional 형태를 사용하게 되면, boxing, unboxing이 일어나면서 성능이 저하되게 됩니다.

<br/>
참고자료:

- https://www.elancer.co.kr/blog/detail/265
