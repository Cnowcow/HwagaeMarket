# 화개장터

## ✏ 프로젝트 개요
  - '중고나라'와 '번개장터'를 모티브로한 중고거래 홈페이지.
  - 프론트엔드 부분은 중고나라 홈페이지를 클론코딩 함으로써 백엔드에 집중하고 REST API를 적용해 CRUD 및 홈페이지 내의 기능들을 구현.

![홈페이지](https://github.com/user-attachments/assets/f2c943f0-fc0e-4151-bda7-d9ee6db78386)
<hr><br>

## ✨기술스택✨

|<img src="https://github.com/user-attachments/assets/e37eb89d-abd8-4b73-913a-970ef8ac2db4">|<img src="https://github.com/user-attachments/assets/0ca1da0e-40a4-463f-8c5f-c4eb59a6d1ef">|<img src="https://github.com/user-attachments/assets/2c166b50-46c8-4ae3-a911-16f7c952f7a1">|<img src="https://github.com/user-attachments/assets/656335a5-c1ac-4c03-b776-c79ad84ea36b">|<img src="https://github.com/user-attachments/assets/cd84b695-c17d-4b28-b031-0f30827ca785">|<img src="https://github.com/user-attachments/assets/04750eda-60a5-4b85-9fba-1870789c0677">
|:---:|:---:|:---:|:---:|:---:|:---:|
|Java|JPA|RESTful API|MySQL|Spring|GitHub|

|<img src="https://github.com/user-attachments/assets/57985638-3de9-45b8-9519-47b6c0f96342">|<img src="https://github.com/user-attachments/assets/ca92d296-cae7-46d6-9aea-c7ee41925eee">|<img src="https://github.com/user-attachments/assets/80a15ed0-7f5f-48c4-ae4e-1e18f717a824">|<img src="https://github.com/user-attachments/assets/30667665-8e8c-4887-9092-7e168e04a717">|
|:---:|:---:|:---:|:---:|
|JavaScript|HTML5|CSS3|Thymeleaf|
<br>
<hr>

## ✅ 맡은 역할
  - ### 메인페이지 구성 및 Front-end
    <br><img src="https://github.com/user-attachments/assets/565d08cb-866b-4f95-b301-ab48d40302db"><br>
    <hr>
  - ### 데이터베이스 설계
    - #### 요구사항 분석
    - #### ERD 작성 (Entity, 속성, 관계 정의)
    - #### 정규화 작업 (중복 최소화, 테이블 구조 설정, key 설정)
    - #### 데이터베이스 구현 및 테스트
    <br><img src="https://github.com/user-attachments/assets/232fac6b-a2ab-4b65-9015-85d28ffe1061"><br>
    <hr>
  - ### 회원가입 및 로그인
      - #### 이메일 인증
        - Java Mail API를 사용해서 8자리 임의문자를 생성하고, 입력한 이메일로 전송. 생성된 올바른 8자리 문자를 입력하면 유효성 검증을 통해 성공/실패/중복 결과 출력
        <br><img src="https://github.com/user-attachments/assets/3f14a3b5-ff60-45de-9778-f67128becf24">
        <img src="https://github.com/user-attachments/assets/bef49a29-c398-4e0d-943e-b02fb2e82707"><br>
    
      - #### 중복체크
        - 사용자가 입력한 ID / 닉네임을 파라미터로 받아놓고, 체크 버튼을 누르면 데이터베이스에서 값을 찾은 후 결과 출력. 같은 값이 있다면 가입 불가, 값이 없다면 가입 성공.
        <br><img src="https://github.com/user-attachments/assets/b4304e16-65b0-401e-9755-ea3f38bee076"><br>

      - #### 카카오맵, 다음 우편번호 API 연동
      - 우편번호 검색 API를 사용하여 주소를 검색하면, 검색된 값을 이용해 지도 위에 Marker를 띄운다. 그리고 시,구,동 까지의 값을 데이터베이스로 보내서 회원 정보에 같이 저장한다. 이 값은 후에 유저의 활동지역 설정을 위해 사용한다.
        <br><img src="https://github.com/user-attachments/assets/e3940ab2-9dfd-4df7-a229-19f0fb357363">
        <img src="https://github.com/user-attachments/assets/6b758082-19de-4d64-b0d2-1c566eff5e10"><br>
        <hr>
      
  - ### 글쓰기 / 수정하기 / 삭제
      - #### 글쓰기
        - 글쓰기를 할 때 모든 form을 채워야 하고, 사진은 1장 이상 필수 첨부할 수 있게 코드 작성, 글쓰기에 성공하면 postId값을 받아와서 바로 글을 확인할 수 있게 redirect.
          <br><img src="https://github.com/user-attachments/assets/34d09037-ce16-48ed-8dda-4167835d1c4f"><br>
          <br><img src="https://github.com/user-attachments/assets/edb96735-9ab0-43fa-8d73-a2a34c2d8e54"><br>

      - #### 수정하기
        - update라는 post 요청을 받으면, 해당 post_num로 PostEntity 데이터베이스를 조회 후 우선 form에 값을 출력. 사용자가 값을 수정한다면, 파라미터로 값을 다시 받아와 기존 PostEntity의 내용을 새로 덮어 저장(업데이트).
        - 예외처리를 통해 게시물 번호가 null일 때  IllegalArgumentException 을 발생 시키고, 게시물이 존재하지 않을 경우 Exception 발생.
          <br><img src="https://github.com/user-attachments/assets/babd1e0a-c3d3-451b-87f5-d752506d8c24"><br>
          <br><img src="https://github.com/user-attachments/assets/47e21374-543f-458f-803c-70324bc6c03c"><br>
          <hr>

  - ### 회원간 실시간 채팅
      - #### 사용자의 user_num 값을 받아서 해당 값을 가진 사용자와의 채팅방 입장 / 채팅 전송 기능
        - userEntity를 조회하여 user_num 대신 user_nick(닉네임) 출력.
        <br><img src="https://github.com/user-attachments/assets/fe11a774-7877-4014-abb2-a5904351e191"><br>
    
      - #### to_user, from_user 구분
        - 보낸사람, 받는사람, 메세지 내용, 시간 등을 데이터베이스에 저장
        <br><img src="https://github.com/user-attachments/assets/0a895ff5-8fbd-4043-8a8d-12b1720d3164"><br>
        
      - #### 실시간 입력 및 출력 (Ajax)
        - Ajax 비동기 방식을 통해 페이지 내에서 post요청 실행.
        - 채팅방 페이지 2초마다 한 번씩 reload를 통해 업데이트 되는 채팅 List 출력
        <br><img src="https://github.com/user-attachments/assets/31d4aee5-b064-40b1-939e-1a502bc38b02"><br>
        <br><img src="https://github.com/user-attachments/assets/2f467d46-633b-4786-aca6-a5d787703c88"><br>
        <br><img src="https://github.com/user-attachments/assets/2b4827c7-733b-4ed1-96f0-01ca3b334ee7"><br>
        <hr>

  - ### 데이터베이스 서버 구축
  - ### 배포


## 🔎 문제점 및 해결방안

- ### 실시간 채팅기능에 Web Socket을 사용하지 못한 점.
    → 여러 기능들을 구현하는 데에 시간 배분을 잘못해서 자료는 많이 찾아보았지만 실제로 적용하는 데에는 어려움이 있었다. 적용하진 못했지만 덕분에 Web Socket에 대해서 공부할 수 있었던 시간.
    
- ### 사용자들의 구매내역을 출력하는 기능을 구현하지 못했다.
    → 실시간 채팅과 이어지는 맥락인데, 채팅내용을 토대로 구매자/판매자를 구분하여 구매여부를 결정하는 기능을 넣으려고 했으나 데이터베이스 설계부터 서비스 로직을 구현하는데 어려움이 많았다. 구매내역을 구현한 프로젝트들을 서치 해보고, 적용 가능한지 공부가 필요한 상황.

##  🔍프로젝트 기간
2024-01-15 ~ 2024-03-20 (2개)
