# AI Commerce Agent

> B2B 이화학·시약 전문 커머스 플랫폼을 위한 AI 상담 에이전트

**395,820개** 상품 데이터를 벡터 임베딩하여, 연구원의 복잡한 구매 상담을 전문 상담원 수준으로 24시간 무중단 제공합니다.

[![Built by Hadeulsoft](https://img.shields.io/badge/Built%20by-Hadeulsoft-blueviolet)](https://hadeul.com)
[![Website](https://img.shields.io/badge/Website-hadeul.com-blue)](https://hadeul.com)

---

## Overview

AI Commerce Agent는 [하들소프트(Hadeulsoft)](https://hadeul.com)에서 개발한 특수 도메인(이화학·시약) B2B 커머스에 특화된 RAG 기반 상담 에이전트입니다. CAS 번호, IUPAC 화학명, 카탈로그 번호 등 도메인 특화 데이터를 이해하고, 일반 LLM이 답변하기 어려운 정밀한 기술 상담을 수행합니다.

### Key Features

- **하이브리드 검색** — 키워드 검색과 시맨틱 검색을 결합하여 395,820개 상품에서 최적의 결과 도출
- **도메인 특화 상담** — 시약 구매 시 순도, CAS 번호, 용량, 제조사를 자동 역질문하여 전문 상담 수행
- **멀티턴 맥락 유지** — 지시대명사, 번호 참조 등 후속 질문 패턴 인식 및 대화 맥락 유지
- **상담 유형 자동 감지** — 구매대행, 견적 요청, 서류 발급, 특수 주문 등 50+ 상담 패턴 인식
- **멀티 LLM 폴백** — 다단계 LLM 체인으로 특정 모델 장애 시에도 무중단 서비스 보장
- **할루시네이션 검증** — 다층 검증 시스템으로 AI 응답 신뢰도 극대화
- **엔터프라이즈 보안** — Rate Limiting, 프롬프트 인젝션 탐지, 토큰 제한 등 통합 보안

---

## Tech Stack

| Category | Technologies |
|----------|-------------|
| **Frontend** | Next.js, React, Tailwind CSS, TypeScript |
| **Backend** | Next.js API Routes, Prisma ORM |
| **Database** | PostgreSQL (pgvector, pg_trgm), MySQL |
| **LLM** | Multi-provider |
| **Embedding** | sentence-transformers MiniLM (384dim, CUDA) |
| **OCR** | PaddleOCR (GPU), Tesseract.js |
| **ML Runtime** | PyTorch (CUDA), sentence-transformers |
| **Infrastructure** | Docker, Nginx, Cloudflare Tunnel |

---

## Architecture

```
사용자 메시지
  → 보안 검증
  → 상담 유형 감지 & 쿼리 라우팅
  → RAG 검색 (키워드 + 시맨틱)
  → LLM 응답 생성 (멀티 폴백)
  → 응답 검증 & 후처리
  → 응답 반환
```

### Dual Database

| Role | Database | Purpose |
|------|----------|---------|
| E-Commerce | MySQL | 쇼핑몰 (상품, 주문, 회원) |
| AI Engine | PostgreSQL | 벡터 검색, 대화 이력, 분석 |

MySQL → PostgreSQL 증분 동기화로 상품 데이터 실시간 연동

---

## Performance

| Metric | Value |
|--------|-------|
| QA 정확도 | **83.25%** (400건 벌크 테스트) |
| 상품 벡터화 | **395,820개** |
| 무중단 상담 | **24/7** |
| 상담 패턴 인식 | **50+** |
| OCR 처리 | **65,638개** 상품 이미지 |

---

## Admin Dashboard

- 상담 패턴 분석 및 검색 성능 모니터링
- LLM 상태 확인 및 대화 이력 관리
- 제조사 우선순위 · 시스템 설정 관리

---

## Screenshots

> *Coming soon*

---

## About

이 프로젝트는 [하들소프트(Hadeulsoft)](https://hadeul.com)에서 개발·운영하고 있습니다.

하들소프트는 AI, 게임, 소프트웨어 개발 전문 기업으로, 도메인 특화 AI 솔루션과 엔터프라이즈 시스템을 구축합니다.

- **홈페이지**: [hadeul.com](https://hadeul.com)
- **서비스**: AI 솔루션 · 게임 개발 · 소프트웨어 개발 · IT 컨설팅
- **문의**: [hadeul.com/inquiry](https://hadeul.com/inquiry)

### Developer

| | |
|---|---|
| **소속** | 하들소프트 개발팀 |
| **담당** | 양동건 책임연구원 |
| **이메일** | ydg@hadeul.com |

## License

This project is proprietary software. All rights reserved.

---

<p align="center">
  <b>Developed by <a href="https://hadeul.com">하들소프트 (Hadeulsoft)</a></b><br>
  AI · Game · Software Development<br><br>
  <a href="https://hadeul.com">🌐 hadeul.com</a>
</p>
