# Fitness Project

헬스장 회원 관리 서비스의 초기 설계 문서입니다. 웹은 관리자 화면이며, 앱은 회원과 트레이너가 함께 사용하는 구조를 목표로 합니다.

## 목표
- **웹 관리자**: 회원/트레이너/수업/결제 관리, 운영 리포트 제공.
- **모바일 앱**: 회원과 트레이너가 모두 사용하며 스케줄, 출결, 메시지, 기록을 공유.

## 사용자 역할
- **관리자(웹)**: 지점 관리, 사용자 관리, 권한 부여, 결제/정산, 공지.
- **트레이너(앱)**: 회원 관리, 수업 일정, 운동/식단 기록 피드백, 출결 체크.
- **회원(앱)**: 일정 확인, 예약/취소, 운동 기록 확인, 채팅/공지 열람.

## 주요 기능 범위 (MVP)
### 웹(관리자)
- 회원/트레이너 목록 및 상세 관리
- 수업/프로그램 관리
- 결제/정산 관리
- 공지/배너 관리
- 리포트: 신규 가입, 활성 회원, 매출 요약

### 앱(회원/트레이너)
- 로그인/역할 기반 홈
- 일정/예약
- 출결 체크
- 운동 기록 및 피드백
- 1:1 또는 그룹 채팅
- 공지 확인

## 초기 데이터 모델 (요약)
- **User**: id, role(admin|trainer|member), name, phone, status
- **Membership**: userId, planId, startAt, endAt, remainingSessions
- **Session**: id, trainerId, startAt, endAt, capacity, status
- **Booking**: sessionId, memberId, status
- **Attendance**: sessionId, memberId, checkedAt
- **WorkoutLog**: memberId, trainerId, note, createdAt
- **Payment**: memberId, amount, method, paidAt

## 다음 단계
1. 화면/플로우 정의 (웹/앱)
2. API 스펙 작성 (인증/권한 포함)
3. DB 스키마 확정 및 마이그레이션
4. 디자인 시스템과 UI 컴포넌트 정리

## 기술 스택 제안 (초안)
- **웹**: React + TypeScript + Vite + TanStack Query
- **앱**: React Native + TypeScript
- **백엔드**: Node.js + NestJS + PostgreSQL
- **인증**: JWT + Refresh Token
