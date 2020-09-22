# RESTFUL API 설계

## 멤버 관련

- 아이디 중복체크
`POST /customers/{userId}`

- 회원가입
`POST /members/{userId}`

- 사용자 정보
`GET /members/{userId}`

- 탈퇴
`DELETE /members/{userId}`

- 로그인
`POST /member/local/{userId}`

- 사용자 정보 수정
`PUT /members/{userId}`

- 찜하기
`PUT /members/{userId}/favorite`

## 게시글 관련

- 게시글 등록
`POST /bbs`

- 게시글 삭제
`DELETE /bbs/{bbsId}`

- 게시글 수정
`PUT /bbs/{bbsId}`

- 게시글 리스트
`GET /bbs`

## 채팅 관련

- 채팅 신청
`POST bbs/{bbsId}/chat/{userId}`

- 채팅 수락/거절
`PUT bbs/{bbsId}/chat/{accept or deny}`

## 매칭 관련

- 매칭 신청
`POST bbs/{bbsId}/match/{userId}`

- 매칭 수락/거절
`PUT bbs/{bbsId}/match/{accept or deny}`