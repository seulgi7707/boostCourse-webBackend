# boostCourse-webBackend
## 데이터 베이스
  - 데이터베이스의 기본개념 (정의)
    - 데이터의 집합 ( a Set of Data )
    - 여러 응용 시스템(프로그램)들의 통합된 정보들을 저장하여 운영할 수 있는 공용(share) 데이터의 집합
    - 효율적으로 저장, 검색, 갱신할 수 있도록 데이터 집합들끼리 연관시키고 조직화되어야 한다.

  - 데이터베이스의 특성
    - 실시간 접근성(Real-time Accessability)
      - 사용자의 요구를 즉시 처리할 수 있다.
    - 계속적인 변화(Continuous Evolution)
      - 정확한 값을 유지하려고 삽입·삭제·수정 작업 등을 이용해 데이터를 지속적으로 갱신할 수 있다.
    - 동시 공유성(Concurrent Sharing)
      - 사용자마다 서로 다른 목적으로 사용하므로 동시에 여러 사람이 동일한 데이터에 접근하고 이용할 수 있다.
    - 내용 참조(Content Reference)
      - 저장한 데이터 레코드의 위치나 주소가 아닌 사용자가 요구하는 데이터의 내용, 즉 데이터 값에 따라 참조할 수 있어야 한다.


----------------------------------------------------------------------------------------------------------------------------------------------------------------------
## 데이터베이스 관리 시스템 (Database Management System = DBMS)
  - 데이터베이스의 기본개념 (정의)
    - 데이터베이스를 관리하는 소프트웨어
    - 여러 응용 소프트웨어(프로그램) 또는 시스템이 동시에 데이터베이스에 접근하여 사용할 수 있게 한다
    - 필수 3기능
      - 정의기능 :  데이터 베이스의 논리적, 물리적 구조를 정의
      - 조작기능 : 데이터를 검색, 삭제, 갱신, 삽입, 삭제하는 기능
      - 제어기능 :  데이터베이스의 내용 정확성과 안전성을 유지하도록 제어하는 기능
    - Oracle, SQL Server, MySQL, DB2 등의 상용 또는 공개 DBMS가 있다.
    


- 데이터베이스 관리 시스템의 장/단점
  - 장점
    - 데이터 중복이 최소화
    - 데이터의 일관성 및 무결성 유지
    - 데이터 보안 보장
  - 단점
    - 운영비가 비싸다
    - 백업 및 복구에 대한 관리가 복잡
    - 부분적 데이터베이스 손실이 전체 시스템을 정지
    
--------------------------------------------------------------------------------------------------------------------------------------------------------------------
## SQL(Structured Query Language)
  SQL은 데이터를 보다 쉽게 검색하고 추가, 삭제, 수정 같은 조작을 할 수 있도록 고안된 컴퓨터 언어입니다.
  관계형 데이터베이스에서 데이터를 조작하고 쿼리하는 표준 수단입니다.
 
 -  종류
    - DML (Data Manipulation Language): 데이터를 조작하기 위해 사용합니다.
      - INSERT, UPDATE, DELETE, SELECT 등이 여기에 해당합니다.
    - DDL (Data Definition Language): 데이터베이스의 스키마를 정의하거나 조작하기 위해 사용합니다.
      - CREATE, DROP, ALTER 등이 여기에 해당합니다.
    - DCL (Data Control Language) : 데이터를 제어하는 언어입니다.
      - 권한을 관리하고, 테이터의 보안, 무결성 등을 정의합니다.
      - GRANT, REVOKE 등이 여기에 해당합니다.
     
     
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## mySql 환경설정
### Database생성하기
1. __cmd 접속__

2. __MySQL 관리자 계정인 root로 데이터베이스 관리 시스템에 접속__
    ```
    mysql -uroot -p
    ```
    window 사용자는 설치 시에 입력했던 암호를 입력합니다.

    맥 사용자는 암호가 없으니 그냥 엔터를 입력하면 됩니다.

    MySQL DBMS에 접속하면 “mysql>” 프롬프트가 보입니다.
    
3. __Database 생성하기__
    * 관리자 계정으로 MySQL에 접속했다면, 다음과 같은 명령으로 데이터베이스를 생성합니다.
     ```
     mysql> create database DB이름;
      ```
    * DB이름을 “connectdb＂로 생성
     ```
     mysql> create database connectdb;
     ```
    *  __Database 사용자 생성과 권한 주기__
      -Database를 생성했다면, 해당 데이터베이스를 사용하는 계정을 생성해야 합니다.
      -또한, 해당 계정이 데이터베이스를 이용할 수 있는 권한을 줘야 합니다.
      -아래와 같은 명령을 이용해서 사용자 생성과 권한을 줄 수 있습니다.
      -db이름 뒤의 * 는 모든 권한을 의미한다.
      -@’%’는 어떤 클라이언트에서든 접근 가능하다는 의미이고, @’localhost’는 해당 컴퓨터에서만 접근 가능하다는 의미입니다.
      -flush privileges는 DBMS에게 적용을 하라는 의미입니다.
      -해당 명령을 반드시 실행해줘야 합니다.
      (ver8.0기준)
      ```
         
      CREATE DATABASE connectdb;

      CREATE USER connectuser@localhost IDENTIFIED BY 'connect123!@#';

      GRANT ALL PRIVILEGES ON connectdb.* TO 'connectuser'@'localhost';

       FLUSH PRIVILEGES:
      ```
4. __MySQL 연결끊기__
  * 프롬프트에서 quit혹은 exit라고 입력
     ```
     mysql> QUIT
     mysql> exit
     ```
   Bye라고 나오면 연결 끊기 성공
   
      

  

          
