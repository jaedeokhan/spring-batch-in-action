## 스프링 배치를 공부하면서 이동욱님의 프로젝트 참고해서 공부

### 버전
- Spring Boot 2.7.8
- Java 11

### 사용 라이브러리
- batch

- jpa
- jdbc

- lombok

- h2
- mysql

### 메타 테이블 
![image](https://github.com/jaedeokhan/spring-batch-in-action/assets/45028904/7a7e52ff-c69d-46eb-ae5e-0589811a56fb)

- batch_job_instance
- batch_job_execution
- batch_job_execution_context
- batch_job_execution_params
- batch_job_execution_seq
- batch_job_seq
- batch_step_execution
- batch_step_execution_context
- batch_step_execution_seq

#### BATCH_JOB_INSTANCE
Job Parameter에 따라 생성되는 테이블이다.
같은 Batch Job이라도 Job Parameter가 다르면 BATCH_JOB_INSTANCE에는 기록되고, 
JOB parameter가 같다면 기록되지 않는다.
즉, 동일한 파라미터의 배치를 실행하면 새로운 행이 쌓이지 않는다.

#### BATCH_JOB_EXECUTION
JOB_EXECUTION과 JOB_INSTANCE는 부모-자식 관계이다.
JOB_EXECUTION은 자신의 부모 JOB_INSTANCE가 성공/실패했던 모든 내역을 가지고 있다.


