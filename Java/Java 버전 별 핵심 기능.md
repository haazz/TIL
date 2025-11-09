LTS 버전인 Java8, 11, 17, 21을 기준으로 작성

# Java8

- [Lambda Expression](Lambda 표현식.md) (람다 표현식)
- Stream API
- Optional class
- 함수형 인터페이스 @FunctionalInterface 예: Predicate, Function, Supplier, Consumer, BiFunction 등
- java.time 패키지 (LocalDate, LocalTime, ...)
- Default Methods
- Nashorn JavaScript 엔진 : JVM에서 JavaScript를 실행할 수 있는 엔진 제공
- Permanent Generation 제거
- CompletableFuture (논블로킹 + 비동기)

# Java11

- 로컬 변수 타입 추론 (var 키워드)
- 새로운 HTTP 클라이언트 API : HTTP/2 및 Websocket 등 변화하는 통신 체계에 맞춰 지원
- 읽기 쉬운 파일 메소드 : Files 클래스에 writeString, readString 메소드를 추가
- String 클래스 새로운 메소드 (isBlank(), lines(), strip(), repeat(int count) 등)
- Epsilon 가비지 컬렉터 : Epsilon GC는 "No-Op" 가비지 컬렉터로, 메모리 할당과 해제의 성능을 테스트하는 데 유용합니다. 이는 실제로 메모리를 수집하지 않으며, 주로 성능 테스트 용도로 사용됩니다.
- JFR (Java Flight Recorder) : JVM에서 실행되는 애플리케이션의 성능을 모니터링하고 분석할 수 있는 도구입니다.
- Optional 클래스에 isEmpty() 메소드 추가
- Java EE, CORBA 모듈 제거 (자바 코어의 더 작은 러타임 이미지와 경계 개선)
- 단일 파일 실행 : java 명령으로 바로 실행 (java Hello.java)

# Java17

- 패턴 매칭 for switch (Preview) : switch 문에서 패턴 매칭을 사용하여 코드의 가독성을 높입니다
- Sealed Classes : 상속 가능 타입을 명시적으로 제한해 도메인 모델의 닫힌 계층 구조를 안전하게 표현
- Foreign Function & Memory API (Incubator) : 자바 외부의 메모리와 함수를 안전하게 호출할 수 있는 API를 제공합니다
- Strong Encapsulation by Default : 강력한 캡슐화가 기본값으로 설정되어 모듈 간의 명시적 접근이 필요합니다 (리플렉션/바이트코드 조작 라이브러리의 불법 접근을 정리해야 함)
- Security Manager 제거 예고(폐지 예정으로 deprecate for removal, JEP 411)
- 향상된 난수 생성기(Enhanced PRNGs, JEP 356) : `java.util.random` 계열에 Jumpable/Splittable 등 현대 알고리즘 API 추가 병렬 시뮬레이션/몬테카를로에 유용
- RMI Activation 제거 (오래된 분산 컴퓨팅 메커니즘을 정리)
- Vector API – (Incubator 3차, JEP 414) : SIMD 벡터화로 데이터 병렬 처리 성능 향상(플랫폼 최적화 자동 활용)

# Java21

- 패턴 매칭 for switch (Standard Feature) : 패턴 매칭이 switch 문에 완전히 통합되었습니다
- Sequenced Collections : 목록 순서 유지 및 조작을 위한 새로운 컬렉션 인터페이스가 도입되었습니다
- Virtual Threads : 수많은 경량 스레드를 쉽게 만들 수 있는 새로운 기능입니다 (기존 Thread / Executor API와 그대로 호환돼 마이그레이션 부담이 적다)
- Foreign Function & Memory API (Standard Feature): 자바 외부의 메모리에 접근하고 외부 함수와 상호작용하는 기능이 표준화되었습니다
- String Templates (Preview) : 문자열을 더 간편하게 포맷할 수 있는 템플릿 기능이 도입되었습니다
- Improved Garbage Collectors : ZGC 및 Shenandoah 가비지 컬렉터의 성능이 개선되었습니다
- 새로운 JEPs : 다양한 JEPs(Java Enhancement Proposals)가 포함되어, 플랫폼의 전반적인 성능과 개발자 경험이 향상되었습니다
- 레코드 패턴 매칭: 패턴매칭과 레코드를 결합해 DTO/이벤트 처리 코드를 더 짧게 가져갈 수 있습니다
