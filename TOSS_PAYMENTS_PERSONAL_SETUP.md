# 개인 토스 페이먼츠 계정 설정 가이드

## 🎯 목적
현재 "부스트웹" 상호로 표시되는 결제를 본인 상호로 변경

## 📋 단계별 설정

### 1. 토스 페이먼츠 계정 생성
1. [토스 페이먼츠 개발자센터](https://developers.tosspayments.com/) 접속
2. 회원가입 (개인/사업자 선택)
3. 본인 정보로 계정 생성

### 2. 테스트 키 발급
1. 대시보드 → **개발 정보** → **API 키** 메뉴
2. **테스트 키** 섹션에서 키 복사:
   - **클라이언트 키**: `test_ck_개인키...`
   - **시크릿 키**: `test_sk_개인키...`

### 3. 환경 변수 교체
`.env.local` 파일 수정:
```env
# 기존 (부스트웹 계정)
NEXT_PUBLIC_TOSS_CLIENT_KEY=test_ck_P9BRQmyarYymBN4obxjNrJ07KzLN
TOSS_SECRET_KEY=test_sk_zXLkKEypNArWmo50nX3lmeaxYG5R

# 새로운 (본인 계정)
NEXT_PUBLIC_TOSS_CLIENT_KEY=본인_클라이언트_키
TOSS_SECRET_KEY=본인_시크릿_키
```

### 4. 개발 서버 재시작
```bash
npm run dev
```

## ✅ 확인 사항
- 결제 시 상호명이 본인 이름/회사명으로 변경됨
- 테스트 결제는 여전히 실제 결제되지 않음
- 모든 기능 정상 작동

## 📝 참고
- 테스트 키는 실제 결제가 발생하지 않는 시뮬레이션용
- 프로덕션 배포 시에는 **라이브 키**로 교체 필요
- 라이브 키는 실제 결제가 발생하므로 주의 필요
