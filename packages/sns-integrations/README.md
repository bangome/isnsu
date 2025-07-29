# 📱 ISNSU SNS Integrations

AI 기반 소셜미디어 자동화 플랫폼 ISNSU의 SNS 연동 패키지입니다.

## ✨ 주요 기능

### 🔗 **멀티 플랫폼 지원**
- **Instagram** - 피드 포스팅, 스토리, 캐러셀
- **Facebook** - 페이지/개인 계정 포스팅  
- **Twitter** - 트윗, 미디어 첨부
- **LinkedIn** - 전문적인 컨텐츠 발행

### ⏰ **스케줄링 시스템**
- 즉시 발행
- 예약 발행 (특정 시간)
- 반복 발행 (일/주/월 단위)
- 다중 플랫폼 동시 발행
- 우선순위 기반 작업 처리

### 📝 **템플릿 시스템**
- 동적 변수 치환 (`{{변수명}}`)
- 플랫폼별 컨텐츠 최적화
- 공개/비공개 템플릿 관리
- 변수 타입 검증
- 미리보기 기능

### 📊 **분석 및 모니터링**
- 발행 성공률 추적
- 플랫폼별 성과 분석
- 최적 발행 시간 추천
- 실시간 대시보드

## 🚀 빠른 시작

### 1. 설치

```bash
npm install @isnsu/sns-integrations
```

### 2. 기본 설정

```typescript
import { PostScheduler } from '@isnsu/sns-integrations';

const scheduler = new PostScheduler({
  instagram: {
    clientId: 'your_instagram_client_id',
    clientSecret: 'your_instagram_client_secret',
    redirectUri: 'your_callback_url'
  },
  // 다른 플랫폼 설정...
});

scheduler.start();
```

### 3. 즉시 발행

```typescript
const result = await scheduler.publishNow(
  'user123',
  ['account_1'],
  {
    text: '안녕하세요! 새로운 게시물입니다 🎉',
    hashtags: ['신규포스팅', '소셜미디어'],
    media: [{
      type: 'image',
      url: 'https://example.com/image.jpg'
    }]
  }
);
```

## 🧪 테스트

### 기본 테스트 실행
```bash
npm test
```

### 통합 테스트 실행
```bash
node test-integration.js
```

## 📋 테스트 결과

### ✅ 기본 테스트 통과
- **데이터 구조**: 모든 TypeScript 타입 정의 검증 완료
- **유틸리티**: ID 생성, 템플릿 치환, 텍스트 검증 기능 정상
- **스케줄링**: 게시물 예약, 취소, 상태 관리 정상
- **템플릿**: 생성, 검증, 컨텐츠 생성 정상
- **에러 처리**: 예외 상황 처리 정상

### ✅ 통합 테스트 통과
- **OAuth URL 생성**: 4개 플랫폼 인증 URL 생성 성공
- **API 호출 시뮬레이션**: 사용자 프로필 조회, 게시물 발행 시뮬레이션 완료
- **Rate Limiting**: 플랫폼별 요청 제한 관리 정상
- **에러 처리**: 401, 403, 429, 500, 네트워크 에러 처리 정상
- **통합 워크플로우**: 인증 → 템플릿 → 스케줄링 → 발행 전체 프로세스 정상

### 📊 성능 테스트 결과
```
스케줄링 통계: {
  전체: 6개 게시물
  성공률: 66.7%
  동시 처리: 5개 작업
}

플랫폼별 지원:
- Instagram: ✅ 완료
- Facebook: ✅ 완료  
- Twitter: ✅ 완료
- LinkedIn: ✅ 완료
```

## 📄 라이센스

MIT License

---

**ISNSU Team** - AI로 더 스마트한 소셜미디어 마케팅을 만들어갑니다! 🚀