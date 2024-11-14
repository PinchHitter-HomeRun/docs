# RESTFUL API 설계

## 멤버 관련

- 아이디 중복체크 (requestId = 사용하고자할 ID)
`POST /customers/{requestId}`

- 회원가입
`POST /members/`
```JSON
{
    "member": {
        "loginId": "ohjang@daeta.com",
        "passWord": "7387ECF02490D22F6E6D98A8F0C638D683778B9D329C5081CE4DCAF8BF2E59B9",
        "sns": "None", // None, Kakao, Google, Facebook
        "name": "오장원",
        "birthDay": "930903",
        "sex": "Male", // Male, Female
        "phone": "010123456",
        "branchId": 1,
        "role": {
            "id": 1
        }
    },
    "hintId" : 1, // 힌트 시퀀스 번호
    "answer": "안녕" // 힌트 답변
}
```

- 사용자 정보 (memberId = 로그인할 때 들어오는 json의 id 속성)
`GET /members/{memberId}`

- 탈퇴
`DELETE /members/{memberId}`

- 로그인 
`POST /members/{loginId}`  
    - 이메일 로그인
        - password 필요 (sha256 암호화)
    - 소셜 로그인
        - password X

- 사용자 정보 수정 (수정할 내용 정하기)
`PUT /members/{memberId}`

- 찜하기 (미구현)
`PUT /members/{memberId}/favorite`

- 계정 찾기 (계정 찾는 조건 - 이름, 생년월일)
`POST /customers/`

- 비밀번호 수정
`PUT /members/{loginId}/password`
    - password

- 지점 신청


- 로그인 토큰 파기 (로그아웃)


- 힌트 가져오기
`GET /members/{memberId}/hint`

- 사용 가능한 모든 힌트 가져오기
`GET /members/hint`

- 답변 확인
`POST /members/{memberId}/answer`  
    - answer

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
`POST bbs/{bbsId}/chat/{memberId}`

- 채팅 수락/거절
`PUT bbs/{bbsId}/chat/{accept or deny}`

## 매칭 관련

- 매칭 신청
`POST bbs/{bbsId}/match/{memberId}`

- 매칭 수락/거절
`PUT bbs/{bbsId}/match/{accept or deny}`
