## 영속성 컨텍스트(Persistence Context)

영속성 컨텍스트는 JPA가 관리하는 엔티티 객체의 집합
엔티티 객체가 영속 컨텍스트에 들어오게 되면 JPA는 엔티티 객체의 매핑정보를 가지고 DB에 반영
영속 컨텍스트에 들어온 엔티티 객체를 영속객체라고 부른다

영속성 컨텍스트는 세션 단위의 생명주기를 가지고 있고 이에 접근하기 위해 EntityManager을 사용

**Entity Mangager(하나의 세션)**
1. Entity Manager생성(by Entity Manager Factory)
2. Entity Manager가 가지고 있는 트랜잭션 시작
3. Entity Manager를 통해 영속 컨텍스트에 접근하고 객체를 작업
4. 트랜잭션을 커밋 -> DB반영 (AI 되는 ID값은 그전에 반영될 수 있는 예외존재)
5. Entity Manager 종료

<br />

## Entity Class

> JPA 어노테이션을 통해 엔티티 클래스 정의

- @Entity : 해당 클래스가 JPA Entity임을 정의
- @Table : DB의 어떤 테이블과 매핑되는지 정의
- @Id : DB의 pk와 매핑
- @Column : 매핑할 테이터베이스의 칼럼 이름과 필드변수의 이름이 다를때 매핑하기 위해 사용
