# 테이블 생성
CREATE TABLE topic (
	id NUMBER NOT NULL,
	title VARCHAR2(50) NOT NULL,
	description VARCHAR2(4000),
	created DATE NOT NULL
);

SELECT table_name FROM all_tables WHERE OWNER = 'gwanzo';

# 행 추가
INSERT INTO topic
	(id,title,description,created)
	VALUES
	(1,'ORACLE','ORACLE is...', SYSDATE);

INSERT INTO topic
	(id,title,description,created)
	VALUES
	(2,'MySQL','MySQL is...', SYSDATE);

INSERT INTO topic
	(id,title,description,created)
	VALUES
	(3,'SQL Server','SQL Server is...', SYSDATE);

# id를 추가 할때마다 자동 생성
CREATE SEQUENCE SEQ_TOPIC;

INSERT INTO topic
	(id,title,description,created)
	VALUES
	(SEQ_TOPIC.NEXTVAL,'ORACLE','ORACLE is...', SYSDATE);

INSERT INTO topic
	(id,title,description,created)
	VALUES
	(SEQ_TOPIC.NEXTVAL,'MySQL','MySQL is...', SYSDATE);

INSERT INTO topic
	(id,title,description,created)
	VALUES
	(SEQ_TOPIC.NEXTVAL,'SQL Server','SQL Server is...', SYSDATE);

INSERT INTO topic
	(id,title,description,created)
	VALUES
	(SEQ_TOPIC.NEXTVAL,'MongoDB','MongoDB is...', SYSDATE);

# 자동배정된 ID의 현재 시퀀셜값을 조회
SELECT SEQ_TOPIC.CURRVAL FROM DUAL;
*DUAL은 가상 특수테이블을 사용하면 값을 하나만 출력함 
  - DUAL을 안쓰면 값을 topic 테이블의 행 갯수만큼 아이디를 출력

# 행 조회
SELECT * FROM topic;

# 컬럼 선택해서 조회
SELECT id, title, created FROM topic;

# id 컬럼으로 정렬
SELECT * FROM topic WHERE id = 1;

SELECT * FROM topic WHERE id > 1;

# 내림차순 정렬
SELECT * FROM topic ORDER BY id DESC;


SELECT * FROM topic 
	OFFSET 1 ROWS;

#행 수정
UPDATE topic                
	SET
      	  title = 'MSSQL',
	  description = 'MSSQL is ...'
	WHERE
	  id = 3;

# 행 삭제
DELETE FROM topic;

# 테이블 삭제
DROP TABLE topic;

# id를 primary key로 설정한 테이블 생성 
CREATE TABLE topic (
	id NUMBER NOT NULL,
	title VARCHAR2(50) NOT NULL,
	description VARCHAR2(4000),
	created DATE NOT NULL,
	CONSTRAINT PK_TOPIC PRIMARY KEY(id)
);
