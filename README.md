# 🛒 Project _ LOTDIZ


 <span style="color:gray">*__Project Summary__*</span>


✔️ **프로젝트 명** 

크라우드 펀딩 쇼핑몰 LOTDIZ 

**✔️ 프로젝트 기간**

2023.09.04 ~ 2023.11.03

**✔️ 홈페이지 url** 

https://lotdiz.lotteedu.com/

**✔️ 관리자 페이지 url** 

[https://admin.lotdiz.lotteedu.com/](https://admin.lotdiz.lotteedu.com/)

**✔️ 프로젝트 설명**

롯디즈 서비스는 펀딩 개설자(메이커)와 후원자(서포터)간의 펀딩 거래를

중개하는 온라인 중개 플랫폼입니다. 

**✔️ 기술 스택**

![기술스택](https://github.com/lotteon2/LOTDIZ_README/assets/66711073/8a7d994a-4864-42a1-82ff-f5034ec6e6fa)

<br/>


## 01. 팀 소개

**✔️ 팀 ‘ OJJOK ’**

| 이름 | 주 포지션 | 세부 담당  | GITHUB 주소 |
| --- | --- | --- | --- |
| 이상원 | Leader <br/> Back <br/> Front <br/> Infra | **Project Service** <br/> - 프로젝트 등록하기 <br/> **Notification Service** <br/> - 배송 시작 알림, 목표 금액 달성 알림 <br/> - event-bridge와 sqs를 이용한 주기적 알림 구성  | https://github.com/nowgnas |
| 이우엽 | Back <br/> Front | **Member Service** <br/> - 회원가입 및 이메일 인증, 로그인 (인증, JWT 토큰 발급), 로그아웃 <br/> - 마이페이지 (서포터 활동 내역 + 회원 정보 조회 및 수정) <br/> - 찜 조회, 삭제 <br/> **APIGateway Service** <br/> - JWT를 통한 인가 로직 구현 <br/> **Payments Service** <br/> - 멤버십 가입 (단건 결제) | https://github.com/leewooyup |
| 이진우 | Back <br/> Front | **Funding Service** <br/> - 펀딩 결제 <br/> - 펀딩 내역 조회 <br/> - 펀딩 상세 내역 조회 | https://github.com/binarywoo27 |
| 이채민 | Back <br/> Front <br/> Infra | **Admin Service** <br/> - 회원 정보 조회, 메이커 정보 조회 <br/> - 프로젝트 정보 조회 및 프로젝트 인증  <br/> - 각 정보 통합 검색 <br/> **Delivery Service** <br/> - 배송 조회 <br/> **Notification Service** <br/> - 알림 조회, 프로젝트 마감 및 프로젝트 미달성 알림 <br/> **Infrastructure** <br/> - MicroService 별, 개별 컨테이너 환경 AWS Fargate EKS를 사용하여 구축 → 운영과 관리의 편리함을 고려하여 Serverless 환경 도입 <br/> - MicroService 단위의 DB 독립적으로 구축 → 하나의 Pod에 App과 DB를 두어 생명주기를 함께하도록 구성 <br/> - AWS EFS & Kubernetes Persistent Volume 및 Claim을 사용한 DB 정보 독립적으로 영구 저장환경 구축 <br/> - Kubernetes Rolling Update 전략으로 Pod 재배포시 Service의 Downtime을 제거 <br/> - AWS NLB를 사용하여 Spring Cloud API Gateway의 엔드포인트를 외부로 노출 <br/> - AWS Route 53 + AWS Certificate Manager + AWS NLB를 연결해 DNS → Load Balancer로 라우팅 <br/> - EventBridge + SQS를 사용한 이벤트 스케줄러 구축 <br/> - SNS + SQS를 사용한 이벤트 기반 Pub/Sub 환경 구축 <br/> - Cloudfront + S3 웹 퍼블리싱 기능을 사용하여 Vue App 구축 <br/> - Github Actions Workflows를 사용하여 각 마이크로서비스 및 프론트엔드 CI/CD 구축 <br/> - 각 마이크로서비스 로깅을 위한 CloudWatch와 연동후 로그 모니터링 | https://github.com/CokeLee777 |
| 최소영 | Back <br/> Front | **Project Service** <br/> - 메인 페이지 (배너, 베스트 롯딜, 마감임박순 롯드+) <br/> - 프로젝트 리스트 조회 (롯드+, 롯딜, 기획전 조회, 좋아요 생성/삭제) <br/> - 프로젝트 리스트 상세 조회 (상세 정보, 지지서명, 함께 하는 서포터, 좋아요 생성/삭제) <br/> - 지지서명 작성, 수정 | https://github.com/cso6005 |


## 02. 프로젝트 기획

**✔️ 주제 선정 방식**

⇒ 마인드 맵을 통해 기획

![mindmap](https://github.com/lotteon2/LOTDIZ_README/assets/66711073/d67dbd1a-476c-4725-b348-37bf654000c8)

 <br/>
 
**✔️ 주제 선정 이유 및 기획 의도**

온라인 쇼핑몰 웹사이트 제작을 위해 이커머스와 유사한 경매 서비스와 티켓팅, 공동구매를 떠올리게 되었습니다.

동시성 처리와 트래픽을 고려해 티켓팅과 공동구매에서 많은 아이디어가 나왔습니다.

투자와 펀딩에서 다양한 기술을 경험할 수 있다는 점에서 펀딩 플랫폼을 선정하게 되었습니다.

 <br/>
 
**✔️ 주요 기능**

🛒 **메인 기능**
![](https://github.com/lotteon2/LOTDIZ_README/assets/55802893/4a6ecfa3-f7df-4097-a20b-14b7a63c9b79)

- **회원**
    - 회원 가입, 로그인, 로그아웃, 개인 정보 조회 및 수정
    - 상품 찜 누르기, 찜 조회, 찜 삭제
- **프로젝트**
    - 프로젝트 리스트 페이지
        - 베스트 롯드+ 조회, 마감임박순 롯딜 조회
        - 카테고리 별, 롯드+ 조회, 기획전 롯드+ 조회, 롯딜 조회
    - 프로젝트 상세 페이지
        - 프로젝트 상세 조회
        - 지지서명 조회, 작성, 수정
        - 함께 하는 서포터 조회
- **롯딜 프로젝트**
    - 특가 할인 적용 이벤트
- **펀딩**
    - 프로젝트 펀딩 및 취소 환불
    - 펀딩 내역 조회, 펀딩 상세 내역 조회
- **멤버십**
    - 멤버십(펀딩 프렌드, 펀딩 파트너) 가입
- **알림**
    - 목표 펀딩 금액 달성 알림
    - 프로젝트 마감 알림, 목표 펀딩금액 미달성 알림
    - 배송 시작 알림

<br/>
 
**🙋‍♀️ Maker  전용 기능**

- **프로젝트 개설**
    - 프로젝트 등록
- **펀딩 관리**
    - 등록한 프로젝트 목록, 상세 조회
    - 각 프로젝트에 대한 펀딩 내역 조회
    - 펀딩 내역 건에 대한 배송 시작
- **알림**
    - 목표 펀딩 금액 달성 알림
    - 프로젝트 마감 알림, 목표 펀딩금액 미달성 알림

 <br/>
 
**🧑‍💼 Back Office**

- 회원, 메이커, 프로젝트 조회 및 검색
- 프로젝트 관리
    - 프로젝트 인증


## 03. 프로젝트 설계

 
✔️ **USE CASE**

![Untitled (1)](https://github.com/lotteon2/LOTDIZ_README/assets/66711073/d8b23333-6211-4ad3-a73a-be7ba7d13b04)
 
 <br/>
 
**✔️ 와이어 프레임**

https://www.figma.com/file/d8jErJg73JWxxqms1BYZ2F/%EB%A1%AF%EB%94%94%EC%A6%88?type=design&node-id=1158-14&mode=design&t=TV939ndKw3PjmX8l-0

 <br/>
 
**✔️ ERD**

![LOTDIZ (1)](https://github.com/lotteon2/LOTDIZ_README/assets/66711073/9e836edd-a879-4579-96e9-8d6c8ddf41ef)
 
 <br/>
 
✔️ **아키텍처**

![Untitled (2)](https://github.com/lotteon2/LOTDIZ_README/assets/66711073/9d832695-a5b0-49f5-906d-aff818c864f6)


## 04. 프로젝트 수행 내용

✔️ **프로젝트 진행 및 협업 방식**

1. **데일리 스크럼**
    - 매일 정해진 시간에 스크럼 미팅을 통해 진행 상황을 공유하고 전날의 성과와 그날의 계획, 그리고 겪고 있는 어려움을 공유하였습니다.
2. **회의록 작성**
    - 모든 회의에 대한 내용을 작성하여 팀원들 간의 결정 사항을 기록하였습니다.
3. **문서화**
    - 노션
    - 마인드맵
    - 요구사항 명세서
    - ERD
    - Use-Case diagram
    - 아키텍처
    - API 명세서
    - 포스트맨
4. **스케줄 달력**
    - 일정, 공지, 업무 마감일을 스케줄 달력에 기록하여 전체 프로젝트 일정을 관리하였습니다.
 
 <br/>
 
**✔️ 개발 및 기술 구현 결과**

- **회원**
    - 인증 및 인가(JWT)
    외부로부터의 요청은 단일 진입점인 Spring Cloud Gateway을 거쳐 (Authorization) Filter를 탄다.
    ( 단, 로그인/회원가입 요청만 Spring Cloud Gateway의 Filter 거치지 않음. )
        
        Member-Service에서 로그인 시 DB의 이메일 및 비밀번호가 입력한 값과 일치한다면,
        JWT Token 발급. 브라우저의 Local Storage에 TOKEN을 저장.
        
        이후, 회원만 할 수 있는 요청에 대해 Spring Cloud Gateway의 필터에서 토큰 유효성 검사를 시행.
        토큰이 유효하다면, 정보를 꺼내 ‘회원(Member)’의 고유 id인 memberId를 Header에 넣어준다.
        
        해당 과정을 거쳐 유효한 회원과 비회원을 구분하고,
        이에 따라, 접근할 수 있는 페이지에 제한을 둔다.
        
    - 멤버십 가입
    Kakao Payments API(단건 결제)를 이용하여, 멤버십 가입을 진행.
    단건 결제 과정은 ‘준비 요청’과 ‘승인 요청’으로 나뉜다.
        
        준비 요청에서, 멤버십 명, 멤버십 가격, 가맹점 코드, approval_url 등의 값을
        
        Kakao Payments Server로 보낸다.
        준비 요청이 완료되면 Kakao Payments Server가 보내주는 응답 중 하나인 값인 ‘next_redirect_pc_url’을 클라이언트로 넘겨 카카오 결제 QR코드가 팝업 창으로 뜨게 한다.
        
        사용자가 결제 정보를 입력하고, 결제하기 버튼을 누르면, 준비 요청 때 보내주었던
        
        approve_url로 요청이 보내지고, Kakao Payments Server에 최종적인 승인 요청을 보내게 된다. Kakao Payments Server에서 정상적인 응답이 오면, DB에 최종적인 결제 정보를
        
        넣고, 트랜잭션 처리하여 결제처리를 완료딩

- **알림**
  - 메시지 큐 서비스인 AWS SQS를 사용해서 알림 서비스와 다른 마이크로서비스간의 결합도를 최소화하였다.
  - AWS SQS는 메시지 건당 비용이 발생하기 때문에 비용 최적화적으로 사용할 수 있고, 자동으로 수평 스케일링이 가능하고, 실패시 DLQ 및 리드라이브 정책을 적용하여 관리가 용이하기 때문에 사용하게 되었다.
  - 같은 이벤트에 대해서 구독하고있는 여러 클라이언트에게 메시지를 발행하기 위해서 SNS + SQS 를 사용한 팬아웃 패턴을 사용하였다.
  - 스케줄링 같은 경우 Spring Batch 또는 여러 스케줄링 전략을 사용할 수 있지만 직접 서버를 관리하고 Cron Job을 스케일링시나 재배포시 관리해주어야 하기 때문에 현재는 관리가 따로 필요없는 AWS EventBridge를 사용하였다.

- **배송**
  - 펀딩이 완료됨과 동시에 반드시 배송 레코드가 생성될 필요가 없기 때문에 펀딩이 완료되면 펀딩 서비스에서 create-order topic에 Message를 발행하고, 이를 배송 서비스가 Polling 하여 배송 레코드가 비동기적으로 생성될 수 있도록 하였다.

- **관리자**
  - 관리자 서비스에서 다른 마이크로서비스에 있는 데이터를 조회하려면 OpenFeign을 사용할 수도 있었지만, 관리자 서비스에 DB를 따로 구성하여 관리자 데이터 형식에 맞게 테이블을 구성하였고, 관리자가 관리하는 데이터가 있는 다른 마이크로서비스에서 데이터 생성 이벤트가 발행되면 Kafka를 통해서 관리자 서비스가 이를 폴링하여 관리자 서비스 DB에 데이터를 삽입할 수 있도록 구성하였다.
  - 프로젝트 인증에 대한 부분은 Real time으로 인증이 될 필요는 없기 때문에 관리자가 프로젝트 인증 이벤트를 발행해서 Kafka로 메시지를 보내면 프로젝트 서비스에서 이를 Polling하여 DB에서 프로젝트 인증 정보를 업데이트할 수 있도록 구현하였다.
 
- **펀딩**
   - 로그인한 사용자는 펀딩하기 버튼을 통해 원하는 프로젝트의 상품을 펀딩할 수 있다.  
     선택한 상품을 카카오페이 API(단건 결제)를 통해 구매를 진행한다.  
     펀딩하기 버튼을 클릭하면 백엔드 서버에서 카카오페이 API를 통해 결제 준비 요청을 보내고 QR코드가 담긴 redirect_url 주소와 tid를 전달받게 된다.  
     사용자에게 redirect_url과 tid를 반환하여 사용자에게 QR코드를 띄워준다. 사용자는 핸드폰으로 QR를 찍어 결제를 진행하고 서버는 이를 받아 데이터 정합성을 맞추기 위한 다음 작업을 수행한다.  
     funding-service 백엔드 서버에서 재고차감을 위해 project-service에서 확인 후 재고가 있다면, 카카오서버로 최종적으로 결제 승인 요청을 보낸다.  
     이후 포인트 차감을 위해 member-service 에 요청을 보내고 상품 배송 정보를 kafka를 통해 delivery-service로 전달하게 된다.  
          
 <br/>
  
**✔️ 회고**

| 이름 | 내용 |
| --- | --- |
| 이상원 | msa 환경에서 서비스에 적절한 테이블 분리와 클래스 설계가 잘 이뤄졌으며, 이후 프로젝트에서는 성능에 대한 고민과 함께 설계를 진행하고 싶습니다.     jpa의 영속성에 대한 더 깊은 이해가 필요하다고 느꼈으며, 데이터베이스 성능에 대한 학습과 고민을 통해 프로젝트에 적용해 보고 싶습니다.    프론트 기술스택에 대한 이해가 부족해 기술을 제대로 사용하지 못한 것이 아쉽습니다. 이후 프로젝트에서는 효율적인 협업과 코드리뷰로 잘 설계된 프로젝트를 수행하고 싶습니다.  |
| 이우엽 | Spring Security와 JWT에 대해 배우고 적용하는 부분에서 동작원리에 대해 시행착오를 많이 겪으면서, 많이 배울 수 있었습니다. 이 과정에서 Spring Security에서 더 깊게 알아보고자 하는 욕심도 생겨서 더 파보고 싶습니다. 이번 프로젝트에서 github 활용이나 협업하는 방식에 대해 가장 많이 배울 수 있었습니다. |
| 이진우 | 결제 과정에서 필요한 API 설계와 데이터 정합성에 대해 고민해볼 수 있었습니다. 또한 MSA 구조에서 DB설계 방법과 Spring Data JPA에 대해 공부해볼 수 있는 소중한 시간이었습니다. 다른 사람들의 잘 짜여진 코드를 보면서 많이 배울수 있었습니다. 결제 서비스를 구현하는 과정에서 프론트 기술을 완전히 이해하지 못할채로 구현한 것이 아쉬웠습니다. 다음 프로젝트에서 보완할 점들을 깨달을 수 있어서 좋았습니다. |
| 이채민 | 기획 과정에서 기능을 너무 방대하게 잡아놨더니 기능을 고도화시키지 못한 부분이 컸던것 같다. 다음부터는 기능을 고도화시킬부분 생각하고 기능을 생각해야겠다. 비록 아쉬움이 남지만 잘 맞는 팀원들을 만나서 성장할 수 있었던 시간이었다.|
| 최소영 | MSA, VUE3, Kafka 등 처음 시도하는 기술 스택이 많은 만큼 배운 점이 많은 프로젝트였습니다. 맡은 기능을 모두 구현하였지만, 코드 리펙토링, 디벨롭을 하지 못해, 아쉬움이 있습니다. 이번 프로젝트를 통해, 각 서비스에 적합한 설계를 찾으며, 탄탄하게 설계를 하는 것이 얼마나 중요한지 알게 되었습니다. 좋은 팀원을 만나서 좋은 결과물을 얻을 수 있었고, 또, 잦은 회의와 소통을 통해 짧은 가간에도 프로젝트를 원활하게 진행할 수 있었던 것 같습니다. 
