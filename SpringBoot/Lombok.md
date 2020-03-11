#  Lombok 정리해두기
> 스프링부트 공부 중 사용한 Lombok들을 정리하면서 빨리 익히도록 하자.

### @SpringBootApplication

> 스프링부트의 자동설정, 스프링 Bean읽기와 생성을 모두 자동으로 설정한다.
@SpringBootApplication 이 있는 위치부터 설정을 읽어가기 때문에 항상 최상단에 위치 해야한다.

### @RestController

> 컨트롤러를 JSON을 반환하는 컨트롤러로 만들어 준다.

### @RequiredArgsConstrutor

> final로 선언된 모든 필드를 포함한 생성자를 생성

---

## In Test Code

### @RunWith(SpringRunner.class)

> 테스트를 진행할 때 JUnit에 내장된 실행자 외에 다른 실행자를 실행.
여기서는 SpringRuunner 실행자를 실행하며 스트링부트 테스트와 JUint 의 연결자

### @WebMvcTest

> 여러 테스트 어노테이션 중 Web(Spring MVC)에 집중할 수 있는 어노테이션

### @Autowired

> 스프링이 관리하는 빈을 주입