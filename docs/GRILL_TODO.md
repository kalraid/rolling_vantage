# Grill TODO

Tracks the `/grill-with-docs` design interview backlog for Rolling Vantage. Update this alongside the in-session task tracker — check items off and add new ones as they surface. Resolved decisions themselves live in `CONTEXT.md` (glossary) and `docs/adr/` (architecture decisions), not here; this file is just the checklist of what's been talked through.

## Done

- [x] 랜덤 이벤트 / 시나리오 이벤트 설계 — Event Tile 6종 정리, `CONTEXT.md`
- [x] 8인 프리포올 동시진행 충돌 규칙 — 거리 기준 리그식 큐, `CONTEXT.md`
- [x] 그리드 규모 산정 — 맵마다 다름, 첫 프로토타입 ~20x20, `CONTEXT.md`
- [x] Faction 패배/소멸 처리 규칙 — 영지 중립화 + 네이티얼 Wild화, 플레이어 사망=즉시 Run 종료, `CONTEXT.md`

## Open

### 핵심 규칙 공백 (우선순위 높음)

- [ ] 주사위 사양 (면수/개수/범위) — Dice Pool 전체가 이 위에서 작동함
- [ ] Territory 점거/유지 판정 규칙 — Dice Pool 크기(N)의 유일한 결정 요인
- [ ] Wild Faction 병합 규칙
- [ ] 챕터 재도전/실패 정책
- [ ] Contest/Skirmish 결과 세분화 (판정 마진별 결과 종류)

### 디자인

- [ ] 캐릭터 디자인 (마스터 로스터/속성/스킬 정체성)
- [ ] 맵 디자인 (그리드 규격/지형/타일 분포 규칙)
- [ ] 레벨 디자인 (런 페이싱/난이도 곡선/절차적 콘텐츠)
- [ ] 내러티브/스토리텔링 방식
- [ ] 적 AI 설계 (Contender 다이스풀 배분 + 네이티얼 Command)
- [ ] UI/HUD 종합 설계
- [ ] 스킬 시스템 설계
- [ ] 전투 연출/VFX 파이프라인
- [ ] 난이도 모드
- [ ] 아이템/장비 시스템
- [ ] 네이티얼 편성/합성/강화 시스템
- [ ] 상태이상/버프·디버프 시스템

### UX/제작

- [ ] 타겟 플랫폼/입력 방식 (PC vs 모바일 터치)
- [ ] 튜토리얼/온보딩 설계
- [ ] 밸런싱/플레이테스트 계획
- [ ] 로컬라이제이션 범위
- [ ] 접근성 고려사항
- [ ] 사운드 콘텐츠 목록
- [ ] MVP 범위/콘텐츠 로드맵
- [ ] 업데이트 로드맵/시즌제

### 엔지니어링

- [ ] 세이브 데이터 스키마
- [ ] 퍼포먼스 목표
- [ ] 분석/텔레메트리 설계

### 법률/비즈니스

- [ ] 수익화/비즈니스 모델
- [ ] 확률형 아이템 여부 명시 (컴플라이언스)
- [ ] 연령등급/게임물 심의
- [ ] 원작 IP 유사성/클리어런스 범위
