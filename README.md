# 성경공부 프로젝트 문서

## 요약
성경읽기를 할 수 있는 어플리케이션 만들기

## 도메인
### 멤버
엔티티
- Member
  - id
  - name
  - email
  - password
  - createdAt
  - lastModifiedAt

기능
- 회원가입
- 로그인
- 회원조회
- 회원정보 변경

### 성경읽기 그룹
엔티티
- BibleStudyGroup
  - id
  - name
  - memberList (oneToMany)
  - expireAt
  - createdAt
  - lastModifiedAt

- BibleStudyTimeLine
  - id
  - content
  - memberId (manyToOne)
  - createdAt
  - lastModifiedAt

- BibleStudyTimeLineReply
  - id
  - content
  - memberId (manyToOne)
  - createdAt
  - lastModifiedAt

- BibleStudyTimeLineReaction
  - id
  - type (like, cry ...)
  - memberId (manyToOne)
  - createdAt
  - lastModifiedAt

기능
  - 그룹 만들기
  - 그룹 멤버 추가, 제거
  - 그룹내 타임라인 댓글
  - 그룹내 타임라인 리액션

성경읽기
- 엔티티
  - id
  - memberId (manyToOne)
  - bibleStudyId (manyToOne)
  - readAt
  - createdAt
  - lastModifiedAt
- 기능  
  - 날짜, 성경권, 몇장, 몇절 선택
    - 성경읽기를 제출했을때 타임라인에 뜨게

성경
- 성경각권, 장, 절 DB화
