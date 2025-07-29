# 🚀 ISNSU - AI-Powered Social Media Automation Platform

AI 기반 소셜미디어 자동화 플랫폼으로, 스마트한 컨텐츠 생성과 멀티 플랫폼 발행을 지원합니다.

## ✨ 주요 기능

### 🤖 **AI 기반 컨텐츠 생성**
- **이미지 분석**: OpenAI Vision API로 이미지 콘텐츠 자동 분석
- **페르소나 엔진**: 브랜드별 맞춤 톤앤매너 적용
- **플랫폼 최적화**: 각 SNS 특성에 맞는 콘텐츠 자동 생성

### 📱 **멀티 플랫폼 SNS 연동**
- **Instagram** - 피드, 스토리, 캐러셀 포스팅
- **Facebook** - 페이지/개인 계정 관리
- **Twitter** - 트윗, 미디어 첨부
- **LinkedIn** - 전문적인 B2B 콘텐츠

### ⏰ **고급 스케줄링 시스템**
- 즉시 발행 / 예약 발행 / 반복 발행
- 우선순위 기반 작업 처리
- 다중 플랫폼 동시 발행
- 최적 발행 시간 추천

### 📝 **스마트 템플릿**
- 동적 변수 치환 시스템
- 플랫폼별 콘텐츠 최적화
- 브랜드 가이드라인 준수
- 템플릿 라이브러리

## 📦 패키지 구조

```
isnsu/
├── packages/
│   ├── ai-services/         # AI 기반 컨텐츠 생성
│   ├── sns-integrations/    # SNS 플랫폼 연동 ⭐
│   ├── database/           # 데이터베이스 스키마 & 마이그레이션
│   └── shared/             # 공통 유틸리티
```

## 🧪 테스트 결과

### ✅ SNS 통합 테스트 완료
- **기본 기능**: 100% 통과 (데이터 구조, 유틸리티, 스케줄링, 템플릿)
- **통합 테스트**: 100% 통과 (OAuth, API 호출, Rate Limiting, 에러 처리)
- **성능**: 6개 게시물 동시 처리, 성공률 66.7%

### 📊 지원 플랫폼별 제한사항
| 플랫폼 | 텍스트 길이 | 이미지 수 | 비디오 수 | 해시태그 |
|--------|-------------|-----------|-----------|----------|
| Instagram | 2,200자 | 10개 | 1개 | 30개 |
| Facebook | 63,206자 | 1개 | 1개 | 30개 |
| Twitter | 280자 | 4개 | 1개 | 10개 |
| LinkedIn | 3,000자 | 1개 | 1개 | 3개 |

## 🔧 API 사용 예제

### SNS 게시물 즉시 발행
```typescript
import { PostScheduler } from '@isnsu/sns-integrations';

const scheduler = new PostScheduler(platformConfigs);

const result = await scheduler.publishNow(
  'user123',
  ['instagram_account', 'facebook_account'],
  {
    text: '새로운 제품을 소개합니다! 🎉',
    hashtags: ['신제품', '론칭'],
    media: [{
      type: 'image',
      url: 'https://example.com/product.jpg'
    }]
  }
);
```

### 템플릿을 사용한 스케줄링
```typescript
// 템플릿 생성
const template = scheduler.createTemplate(
  'user123',
  '제품 출시 공지',
  {
    text: '🎉 {{productName}} 출시를 발표합니다!\n\n{{description}}',
    hashtags: ['신제품', '{{productName}}']
  }
);

// 템플릿으로 스케줄링
const posts = await scheduler.scheduleFromTemplate(
  'user123',
  ['account_1'],
  template.id,
  {
    productName: 'ISNSU Pro',
    description: 'AI 기반 소셜미디어 자동화 플랫폼'
  },
  new Date(Date.now() + 3600000) // 1시간 후
);
```

## 🚀 빠른 테스트

SNS 통합 패키지를 테스트해보세요:

```bash
cd packages/sns-integrations
node test-basic.js        # 기본 기능 테스트
node test-integration.js  # 통합 테스트
```

## 🛠️ 개발 환경

### 필수 요구사항
- Node.js 18+
- PostgreSQL 14+
- Redis 6+

### 추천 도구
- Docker & Docker Compose
- VS Code + TypeScript 확장
- Postman (API 테스트)

## 🤝 기여하기

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 라이센스

이 프로젝트는 MIT 라이센스 하에 배포됩니다.

---

**Made with ❤️ by ISNSU Team**  
*AI로 더 스마트한 소셜미디어 마케팅을 만들어갑니다!*