## Index
### Index란?
읽기 성능을 향상시키기 위한 일종의 자료구조라고 볼 수 있다.
Index는 관련된 Table과 별도로 저장되며 Index로 설정한 컬럼값이 변경되거나 추가되면 Index도 업데이트가 동시에 된다.
Index에 주료 사용하는 자료구조는 B+-Tree 알고리즘이다.
Primary Key에는 Database가 자동으로 Index기능을 설정하여 관리한다.
### Index를 사용하는 이유
1. WHERE 구문과 일치하는 열을 빨리 찾기 위해서.
2. 열을 고려 대상에서 빨리 없애 버리기 위해서. 
3. 조인 (join)을 실행할 때 다른 테이블에서 열을 추출하기 위해서.
4. 특정하게 인덱스된 컬럼을 위한 MIN() 또는 MAX() 값을 찾기 위해서.
5. 사용할 수 있는 키의 최 좌측 접두사 (leftmost prefix)를 가지고 정렬 및 그룹화를 하기 위해서.
6. 데이터 열을 참조하지 않는 상태로 값을 추출하기 위해서 쿼리를 최적화 하는 경우에.

### Index 장점
- 키 값을 기초로 하여 테이블에서 검색과 정렬 속도를 향상시킵니다.
- 질의나 보고서에서 그룹화 작업의 속도를 향상시킵니다.
- 인덱스를 사용하면 테이블 행의 고유성을 강화시킬 수 있습니다.
- 테이블의 기본 키는 자동으로 인덱스 됩니다.
- 필드 중에는 데이터 형식 때문에 인덱스 될 수 없는 필드도 있습니다.
- 여러 필드로 이루어진(다중 필드) 인덱스를 사용하면 첫 필드 값이 같은 레코드도 구분할   수 있습니다.
  참고로 액세스에서 다중 필드 인덱스는 최대 10개의 필드를 포함할 수 있습니다.
  
### Index 단점
- 인덱스를 만들면 .mdb 파일 크기가 늘어난다.
- 여러 사용자 응용 프로그램에서의 여러 사용자가 한 페이지를 동시에 수정할 수 있는 병행성이 줄어든다.
- 인덱스 된 필드에서 데이터를 업데이트하거나, 레코드를 추가 또는 삭제할 때 성능이 떨어집니다.
- 인덱스가 데이터베이스 공간을 차지해 추가적인 공간이 필요해진다. (DB의 10퍼센트 내외의 공간이 추가로 필요)
- 인덱스를 생성하는데 시간이 많이 소요될 수 있다.
- 데이터 변경 작업이 자주 일어날 경우에 인덱스를 재작성해야 할 필요가 있기에 성능에 영향을 끼칠 수 있다.

### Clustered Index
1. 테이블당 한개만 생성이 가능
2. 행 데이터를 인덱스로 지정한 열에 맞춰서 자동 정렬
3. 영어사전처럼 책의 내용 자체가 순서대로 정렬이 되어있어, 인덱스 자체가 책의 내용과 같음

### Non-Clustered Index
1. 테이블당 여러개를 생성할 수 있음
2. 그냥 찾아보기가 있는 일반 책과 같다.

## Stored Procedure
### 장점
- DB 보안
SQL 인젝션과 문법적 취약점을 이용해 해킹하기 어렵다.
자체적인 보안설정. SP 단위로 실행권한 부여 가능
- 코드 재사용에 용이
- 네트워크 소요시간 감소
- 매개변수만 보내 트래픽양 감소
- 컴파일 후에 캐시를 가지고 있어 성능 향상
### 단점
- 낮은 성능
- 유지보수 문제
- 디버깅 어려움

## NoSQL
NoSQL 데이터베이스는 확장 가능한 성능 및 스키마 없는 데이터 모델에 최적화된 비관게형 데이터베이스이다. 또한 NoSQL 데이터베이스는 개발 용이성, 짧은 지연 시간, 짧은 복원력으로 널리 인정받고 있다.
기존 관계형 데이터베이스보다 더 큰 규모와 더 빠른 응답성이 필요한 많은 양의 빅데이터, 모바일 및 웹 애플리케이션에 매우 적합하다고 한다. 간단한 데이터 구조와 수평적 확장 덕분에 일반적으로 NoSQL 데이터베이스는 관계형 데이터베이스보다 더 빠르게 응답하고 더 쉽게 확장할 수 있다.
### 특징
- RDBMS와는 달리 데이터 간의 관계를 정의하지 않는다. 
- RDBMS에 비해 훨씬 더 대용량의 데이터를 저장할 수 있다. 
- 분산형 구조를 갖는다.
- 고정되지 않은 테이블 스키마를 갖는다.
