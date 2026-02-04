---
layout: single
title: "AssoAI 아키텍처 소개"
date: 2026-02-04 17:00:00 +0900
categories: [devlog, architecture]
toc: true
toc_sticky: true
---

AssoAI의 기술 아키텍처를 소개합니다.

## 전체 구조

```
┌─────────────────────────────────────────┐
│              Frontend                    │
│         (Next.js + React)               │
├─────────────────────────────────────────┤
│              API Layer                   │
│      (Next.js API Routes + tRPC)        │
├─────────────────────────────────────────┤
│           Business Logic                 │
│    ┌─────────┬─────────┬─────────┐     │
│    │ Inbox   │ Agent   │ Integ.  │     │
│    │ System  │ System  │ System  │     │
│    └─────────┴─────────┴─────────┘     │
├─────────────────────────────────────────┤
│              Data Layer                  │
│    ┌─────────┬─────────┬─────────┐     │
│    │PostgreSQL│  Redis  │   S3   │     │
│    └─────────┴─────────┴─────────┘     │
└─────────────────────────────────────────┘
```

## 핵심 시스템

### 1. Inbox 시스템

모든 파일과 문서를 관리하는 중앙 허브.

**특징:**
- 벡터 검색 기반 시맨틱 서치
- AI 자동 태깅
- 실시간 동기화

### 2. Agent 시스템

자동화된 작업을 수행하는 AI 에이전트.

**에이전트 종류:**
- Meeting Prep Agent
- Event Reminder Agent
- Inbox Processor Agent
- Task Tracker Agent
- Organization Analyzer Agent

**트리거 방식:**
- 스케줄 기반 (cron)
- 이벤트 기반 (webhook)
- 수동 트리거

### 3. Integration 시스템

외부 서비스 연동 관리.

**지원 서비스:**
- Google Calendar
- Google Drive
- Notion
- Slack
- Discord
- GitHub (NEW!)

## 기술 스택

| 영역 | 기술 |
|------|------|
| Frontend | Next.js 14, React, TailwindCSS |
| Backend | Next.js API Routes, Prisma |
| Database | PostgreSQL (Supabase) |
| Cache | Redis (Upstash) |
| Storage | S3 (Cloudflare R2) |
| AI | Claude API, Gemini API |
| Auth | NextAuth.js |
| Deploy | Vercel |

## 확장성

AssoAI는 수평적 확장이 가능하도록 설계되었습니다.

- Serverless 아키텍처로 자동 스케일링
- Edge Functions로 글로벌 저지연
- Database Connection Pooling

---

*질문이 있으시면 GitHub Issues로 문의해주세요.*
