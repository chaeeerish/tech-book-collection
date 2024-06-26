### 데이터의 무결성이란
- 데이터에 결함이 없는 성질이다.
- 데이터가 정확하고 일관적이며 누락 등의 문제가 없다.

**✅ 아래의 코드만으로는 데이터의 무결성을 보장할 수 없다. 이유는?**
```
/* 아이디 중복 체크 의사코드*/
입력한 아이디가 사용자 테이블에 존재하는지 확인하기 위한 조회 쿼리문 실행

만약, 사용자 테이블에 아이디가 존재한다면,
    사용자에게 안내 메시지("이미 등록된 아이디입니다.")를 출력
만약, 사용자 테이블에 아이디가 존재하지 않는다면,
    사용자에게 안내 메시지("사용 가능한 아이디입니다.")를 출력
```
> 동시성이 발생하는 상황에서 무결성 보장을 고려하지 않기 때문이다.

### DBMS에서 제공하는 세 가지 무결성
1. 개체 무결성 
   1. 유일한 값이 들어가도록 강제하는 것이 개체 무결성이다.
   2. Unique 제약 조건 or Primary Key 제약 조건
2. 참조 무결성
   1. Foreign key 제약 조건
3. 도메인 무결성
   1. 정해진 범위에서 허용된 값만 입력하도록 보장하는 성질이다.
   2. Unique 제약 조건, not null 제약 조건, check 제약 조건

🚨 소스 코드에서 입력 값의 범위를 확인하는 것은 매우 좋은 코딩 습관이다. 그렇다 해도 DBMS의 CHECK 제약 조건을 함께 사용하는 것이 좋다. 그 이유는 소스 코드로 구현한 유효성 검사가 제대로 동작하지 않는 등의 예외 상황이 발생할 수 있기 때문이다.