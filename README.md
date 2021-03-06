# 움찬러너(가제)


움찬은 돋아오르는 싹처럼 힘차게 라는 뜻입니다.

서울시 시민들이 러닝에 참여하여 건강도 챙기고 일상에서 움차게 살아가자는 의미를 담았습니다.

다들 뛰어봅시다!


---

## Design

### Workflow(v1.0)
![Workflow](https://github.com/YukJiSoo/UMCNAN-Document/blob/master/WorkFlow.png)

## UI(v1.1)

### 탭바 3개

- 크루
  - 내가 참여중인 크루 목록
  - 선택하면 크루 세부정보(모달)
  
- 메인
  - 러닝 섹션
    - 서울시 지도에 마크가 떠있고 마크를 누르면 해당지역 러닝 조회(누르면 모달로 목록)
    - 내 주위 러닝 조회 버튼(누르면 모달로 목록) > 아직 적용 X
  - 크루 섹션
    - 활발하게 활동중인 크루 보여줌
    - 가로 콜렉션 뷰
    - 누르면 해당 크루 정보 보여줌(모달)
    
- 러닝 기록
  - 말 그대로
  - 목록 중에서 누르면 상세정보 보여줌(모달)
    - 이름
    - 날짜
    - 코스
    - 주최한 사람 / 참여한 사람 (누르면 프로필 확인)



### 개인정보

우상단의 프로필이미지 누르면 모달

앱정보 설정도 여기서 가능(알림 같은거)



### 초기화면

로그인 및 회원가입

네이버, 카카오 로그인 지원(페이스북은 싫어)


### ERD(v1.0)
![ERD](https://github.com/YukJiSoo/UMCNAN-Document/blob/master/ERD_190804_v1.0.png)

### Class Diafgram(v1.0)
![Class Diagram](https://github.com/YukJiSoo/UMCNAN-Document/blob/master/Class_190804_v1.0.png)

---

## Requirement

### Client - iOS

- Language
  - Swift 5.0
  
- Deployment target
  - 11.0
  
- 사용기술
  - Alamofire, Kingfisher, RxSwift, MVVM



### Server - Node.js

- REST API

- Framework
  - Express.js
  
- DB
  - MySQL
  
- AWS
  - EC2
  - RDS
  - S3
  
- Docker

- Admin
  - React !!
  - 데이터 관리 용도의 관리자 페이지


---

## 기능

- 러닝코스 선택
  - default
    - 둘레길 api
    - 서울시 길에 대한 api 더 찾아보기
  - custom
    - 사용자가 직접 지정
    - Map API사용 (카카오 or 네이버)
  - 혼자 뛰기 / 같이 뛰기 선택
  - 같이뛰기 > 러너모집
  - data
    - name
    - date
    - course
    - location(대략적인 위치 정보?)
    - lastEnrollmentDate(같이 뛰는 경우 아니면 null)
    
- 러너 모집
  - 자신이 설정한 러닝코스를 공지
  - 지원기간 설정가능
    
- 러닝 참여
  - 공지된 러닝중에서 원하는 러닝 참여
  - 러닝 당일 까지 목록에서 조회가능(지원기간이 지났으면 빨갛게 표시)
  - default로 자신과 가까운 코스를 상위목록에서 보여줌
  - 위치 지정가능(ex. 한강주변, 잠실주변)
  
- 크루 생성
  - 몇번 이상 러닝을 진행하면 크루 생성 가능 
    - 러닝 기록이 일정 개수 이상이면 가능
    - 개인이 러닝한 것은 체크안함
  - 크루장이 같이뛰기 러닝을 등록하면 자동으로 크루원들에게 알림이 감
  - 크루장은 크루에 대한 모든 권한
  - 개인은 여러 크루 생성 및 참여 가능
  - data
    - name
    - creationDate
    - captin
    - crewImage
    
- 크루 참여
  - 크루 목록을 보고 참여가능
  - 위치순
  - 참여 인원순
  - 최신 생성순
  - 이름조회
  
- 러닝 기록
  - 내가 지금까지 진행한 러닝 목록 확인
  - 러닝 기록은 같이 러닝을 진행한 모든 사람이 참가확인을 해줘야 등록됨
  - 등록한 사람도 예외는 없음
  - data
    - name
    - date
    - course
    - location(대략적인 위치 정보?)
    
- 회원가입
  - 동의서같은 것도 작성해야되는지 확인(모임을 모집하면서 혹시라도 벌어질 불미스러운 사고같은 것들에 대한 사전처리)
  - data
    - email
    - name
    - password
    - address
    - phone
    - gender
    - profileImage



### 일단 나중에 고려 할 것

- 따릉러너
  - 따릉이 대여소를 기점으로 한 따릉러닝
  
- 러닝이 시작되면 현재 위치를 기준으로 러닝코스를 잘 따르고 있는지 백그라운드에서 확인
  - 러닝 기록 등록할 때 이용할 수 있을 듯
  
