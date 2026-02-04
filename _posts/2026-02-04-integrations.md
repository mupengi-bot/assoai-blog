---
layout: single
title: "AssoAI 연동 시스템 가이드"
date: 2026-02-04 16:00:00 +0900
categories: [guide, integration]
toc: true
---

AssoAI를 외부 서비스와 연동하는 방법을 안내합니다.

## 지원 서비스

| 서비스 | 기능 | 상태 |
|--------|------|------|
| Google Calendar | 일정 동기화 | ✅ |
| Google Drive | 파일 가져오기 | ✅ |
| Notion | 페이지 동기화 | ✅ |
| Slack | 알림, 메시지 | ✅ |
| Discord | 알림, 명령어 | ✅ |
| GitHub | 이슈, PR 동기화 | ✅ NEW |

## Google Calendar 연동

### 설정 방법

1. 설정 > 연동 메뉴로 이동
2. "Google Calendar 연결" 클릭
3. Google 계정 로그인
4. 권한 허용

### 사용 방법

연동 후 자동으로:
- 조직 일정이 캘린더에 동기화
- 캘린더 이벤트가 AssoAI에 표시
- AI가 일정 충돌 자동 감지

## Notion 연동

### 설정 방법

1. 설정 > 연동 메뉴로 이동
2. "Notion 연결" 클릭
3. Notion 워크스페이스 선택
4. 공유할 페이지 선택

### 동기화 옵션

- **단방향**: Notion → AssoAI
- **양방향**: 양쪽 모두 반영 (Coming Soon)

## GitHub 연동 (NEW!)

### 설정 방법

1. 설정 > 연동 메뉴로 이동
2. "GitHub 연결" 클릭
3. Repository 선택
4. 권한 설정

### 기능

- Issues를 AssoAI 태스크로 동기화
- PR 상태 실시간 추적
- 코드 리뷰 알림

## API 연동

개발자를 위한 REST API도 제공합니다.

```bash
curl -X GET https://api.assoai.com/v1/files \
  -H "Authorization: Bearer YOUR_API_KEY"
```

API 문서: [docs.assoai.com](https://docs.assoai.com)

---

*연동 관련 문의: support@assoai.com*
