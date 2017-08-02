
# 5조 프로젝트 : 편리해(편의점 리뷰해)


## Ground Rule

1. 아침에 출근하고 전날했던거 리뷰, 이슈 공유
* 한 가지 이상 의견 제시하기
* 서로의 이야기 경청하기
* 회의 내용 기록하기(깃허브 위키에 기록한다. 서기는 매일 돌아가며 한다.)
2. 회의시간(30분 ~ 1시간)
* 시간은 9시에서 10시 사이로 정한다.
* 구현했던 것에 대한 리뷰
* 풀리퀘스트한 것 Merge
* 오늘의 할일에 대한 논의
* 추가 기능에 대한 논의
* 개발하면서 생기는 문제점과, 구현할 때 어려운 부분을 논의.
3. 의사결정은 다수결의원칙으로 정한다.
* 다만 2:2로 나뉠경우 강현구 멘토님에게 여쭤본다.
* 결정이 안날 경우 설문조사를 실시한다.
* 결정이 안날 경우 사다리 타기를 진행한다.
4. Git 사용법
* Commit 메시지는 “170802 - 변경 및 추가사항” 한글로 쓸 것
* Commit은 의미있는 하나의 기능 단위로 한다.
* 매일 아침에 각각의 branch 가 기능적으로 완료 됬을 경우, 원격저장소로 branch를 push한 뒤에, master에 pull request를 보낸다. 이후 각 트랙별로 코드리뷰를 통해 master와 merge를 한다
* master branch는 항상 동작 가능한 상태로 둘 것 
* 한 주마다 데모시, 혹은 큰 기능이 완료 되었다고 판단했을 경우 TAG를 부여한다.
* TAG Name은   V.0.주차.1  / V.1.0.0 - 마지막 최종 릴리즈


----------------------------
## 데이터 가져오는 방법
> 크롤링으로 각 3사(GS25, CU, 7Eleven)에서 가져오며, 해당 데이터를 JSON화 하여 Firebase RealtimeDatabase에 저장한다.
> 각각 iOS와 Web에서 Firebase를 import하고, 화면마다 적절한 쿼리를 적용하여 필요한 부분만 가져온다.
----------------------------
## 코딩스타일
### 웹
* 한줄처리 하지 말것(가독성)
* 프레임워크는 Pure Javascript로 한다.(추후에 Vue.js 가능성이 있다.)
* CSS는 div-header-wrapper와 같이 선언하며, [tag이름-기능]과 같이 구현한다.(우리만의 룰 정리가 더 필요하다)
* JS에서는 클래스는 대문자, 함수는 소문자로 사용하며 동사+명사로 사용한다.
* 변수는 소문자로 시작하며 중간 구분을 대문자로 한다(ex. httpRequest)
* Template은 Handlebar.js 를 사용한다.
* Template 형식은 HTML 내부에 작성하여 보관한다.
* 페이지이름은 서로 의논하에 정한다.
* 변수 선언은 const/let만 사용한다.
* Event를 사용할 때 초기에 event.preventDefault()를 선언해준다.
* HTML DOM에서 ID값 사용을 최소화한다. - QuerySelector를 사용하자!
* TAB/NAV부분은 EventDelegation 방식을 사용한다.
* Webpack을 이용하여 모든 브라우저 호환되게끔
* UnitTest는 데이터 Request/Response 때만 사용한다.
* 주석은 한줄 단위가 아니라 문장으로 묶는다. (ex )
* 서로 다른 페이지를 개발한다.(ex 통일 : index, 세훈 : item)
* 총 코드리뷰는 17시~18시 사이에 한다.
* Airbnb의 JS 스타일을 준수한다.
* [function의 형식은 자유롭게 한다. ex (x) => ... or function(x){ ... }]
> function의 형식은 function(params){ ... } 로 고정한다.
----------------------------

### iOS
* 변수 / 함수 소문자 카멜케이스하고 클래스는 대문자 카멜케이스 로 작성한다.
* 함수명에 동사가 들어가고 파라미터에 목적어 / 보어가 들어가도록 함수명을 작성한다.
* 라벨 / 버튼 / 텍스트 뷰의 변수명인 경우 각각  label / btn / text 로 단다.
* 코멘트는 한글로 한다.
* 함수 / 기능 / 모델별 코멘트를 단다.
* Notification 쓸 때는 받는 쪽 / 보내는 쪽 둘다 명시해서 코멘트를 단다.
* 기기 아이폰 7 을 기준으로 한다.
* indent는 tab으로 한다.
* 상대방 파일 건드릴 일있으면 짝코딩을 한다.
* 뷰 컨트롤러 단위로 작업한다.
* 통신하는 모델은 하나에 몰아서 쓴다
* 통신 시 받아오는 데이터를 무조건 클래스로 만들어서 관리한다.
* 중요한 string은 plist로 관리한다.
=======

## 기획서 링크 
[편리해 기획서 초안 링크](https://docs.google.com/document/d/1jVmS0zjNG-4lkVaPkqFE1c6sU9i3j-eR2COsos0fbHE/edit)

## 데이터 모델링 링크 (firebase,NOSQL)
[데이터 모델링 스프레드 시트 링크](https://docs.google.com/spreadsheets/d/1NzoCFyUQgactdnypufIrkrYPb2KS8XLQwqlvuBE_gJ4/edit?usp=sharing)

# 웹 백로그
[웹 백로그 스프레드 시트 링크](https://docs.google.com/spreadsheets/d/1VxQ7uHRMojI4kAINT8IKsNo_10K-AX_7Z-9kQjrHyrM/edit?usp=sharing) 
