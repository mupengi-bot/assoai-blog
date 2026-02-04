---
layout: single
title: "개발 일지: Inbox 시스템 대규모 업데이트"
date: 2026-02-04 18:00:00 +0900
categories: [devlog, feature]
toc: true
---

오늘 AssoAI Inbox 시스템에 대규모 업데이트를 진행했습니다.

## 완료된 기능

### 1. 태그/라벨 시스템
파일에 태그를 달아 분류할 수 있습니다.

```typescript
// 태그 추가 예시
await addTag(fileId, "urgent");
await addTag(fileId, "review-needed");
```

### 2. 파일 내용 검색 (벡터검색)
AI 기반 시맨틱 검색으로 파일 내용을 검색합니다.

- 키워드 매칭이 아닌 의미 기반 검색
- 유사 문서 자동 추천

### 3. 공유 링크 생성
외부 공유용 링크를 생성할 수 있습니다.

- 만료일 설정 가능
- 비밀번호 보호 옵션

### 4. Google Drive 연동
Google Drive 파일을 AssoAI로 가져올 수 있습니다.

- OAuth 2.0 인증
- 폴더 동기화
- 실시간 업데이트

### 5. AI Fallback 시스템
Claude 크레딧이 부족할 때 Gemini로 자동 전환됩니다.

```typescript
// 자동 fallback 로직
const response = await analyzeWithFallback(content);
// Claude 실패 시 → Gemini 자동 시도
```

### 6. 분석 재시도 API
분석 실패 시 재시도할 수 있는 API를 추가했습니다.

## 다음 목표

- [ ] 실시간 협업 (멀티 커서)
- [ ] 버전 관리
- [ ] Notion 양방향 동기화

## 기술 스택

- **Frontend**: Next.js 14, React, TailwindCSS
- **Backend**: Next.js API Routes, Prisma
- **AI**: Claude API, Gemini API
- **Storage**: PostgreSQL, S3

---

*AssoAI 개발팀*
