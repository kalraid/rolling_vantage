# Grill TODO

Tracks the `/grill-with-docs` design interview backlog for Rolling Vantage. Update this alongside the in-session task tracker — check items off and add new ones as they surface. Resolved decisions themselves live in `CONTEXT.md` (glossary) and `docs/adr/` (architecture decisions), not here; this file is just the checklist of what's been talked through.

Items are broken down to atomic (single-decision) granularity by design — each line should be answerable without needing a sub-decision inside it. Where a topic naturally splits into "system/spec" (rules, numbers, structure) vs "pure design" (visuals, experience, content), those are tracked as separate items, since system usually needs to lock in first.

## Done

- [x] 랜덤 이벤트 / 시나리오 이벤트 설계 — Event Tile 6종 정리
- [x] 8인 프리포올 동시진행 충돌 규칙 — 거리 기준 리그식 큐
- [x] 그리드 규모 산정 — 맵마다 다름, 첫 프로토타입 ~20x20
- [x] Faction 패배/소멸 처리 규칙 — 영지 중립화 + 네이티얼 Wild화, 플레이어 사망=즉시 Run 종료
- [x] 주사위 사양 (면수/개수/범위) — D6 기본, N은 영지 수=무제한
- [x] Territory 점거/유지 판정 규칙 — 중립은 즉시 점거, 적대는 Contest/Skirmish, N=최대 클러스터 크기
- [x] Wild Faction 병합 규칙 — 근처 기존 Wild Faction에 흡수, 없으면 신규 생성
- [x] 챕터 재도전/실패 정책 — 일반 챕터=재도전 없이 다음화, 핵심 챕터(Act 마지막)=실패 시 캠페인 전체 리셋
- [x] Contest/Skirmish 결과 세분화 — 마진 3단계(데미지만/데미지+특수효과/즉사)

(자세한 내용은 `CONTEXT.md` 참고)

## Open

### 다이스 시스템 세부

CONTEXT.md의 "Open decisions"에 적혀 있었지만 태스크로 안 옮겨져 있던 것들 — Dice Pool/Contest 관련 잔여 규칙.

- [x] 소환/특수능력 판정의 다이스풀 사용 여부 — MP만 소모, 다이스 안 씀
- [x] 방어측 다이스 예비/고정방어값 규칙 — 별도 굴림 없이 자기 턴에 안 쓴 남은 다이스(Reserve)로 방어
- [x] Reinforce 사거리/범위 제약 — 제한 없음, 맵 어디든 가능
- [x] 마스터별 시그니처 주사위 종류 — 대부분 D6, 소수만 시그니처 주사위
- [x] 다이스 리롤 규칙 (범위/비용) — 풀 전체만 재굴림, 비용은 라운드당 리롤 횟수에 비례 증가

### 캠페인 구조 세부

- [x] 챕터 내 런간 이월 상태 규칙 — GP·영지 매런 리셋, 스토리 진행도만 이어짐
- [x] Run 성공/실패 GP 전환 비율 수치 — 성공 100% / 실패 25%

### Requisition (사령부 지원구매)

Support Skill(메타 해금 영구 스킬)과 이름이 헷갈려서 개명함 — 이전 이름 "Support Purchase".

- [ ] Requisition 구체 목록/비용

### 캐릭터 — 스펙

- [x] 마스터 로스터 규모 — Contender는 플레이어와 같은 로스터 공유, 출시 목표 12~16명
- [x] 속성/엘리멘탈 상성 시스템 여부 — VM V2식 4속성 순환+마스터 특례 채용, 다이스 값 보정 방식으로 통합
- [x] 마스터/네이티얼 기초 스탯 구조 — HP+이동력보정+MP상한/유지비, 별도 공격/방어력 없음
- [x] 네이티얼 이동 속도 관리 방식 — 개별 Speed 스탯(틱당 이동칸수)으로 실시간 이동

### 캐릭터 — 비주얼

- [ ] 캐릭터 실루엣 차별화 원칙
- [ ] AI 일러스트 프롬프트/스타일 가이드

### 맵 — 시스템

- [ ] 그리드 좌표계/기본 규격 원칙
- [ ] 지형 타입 목록과 게임플레이 효과
- [ ] 타일 분포 밀도 규칙

### 맵 — 비주얼

- [ ] 챕터별 맵 테마 차별화
- [ ] 타일/지형 아트 스타일 가이드

### 레벨 — 시스템

- [ ] 런 예상 플레이타임/턴수
- [ ] 챕터별 난이도 곡선
- [ ] 절차적 파트풀 구성
- [ ] 보스/특수 인카운터 존재 여부

### 레벨 — 경험

- [ ] 레벨 디자인 (공간감/플레이 리듬/경험 흐름)

### 내러티브 — 구조

- [ ] 스토리 전달 트리거 방식
- [ ] Act/Chapter-스토리 진행 연결 구조
- [ ] 분기 서사 여부

### 내러티브 — 콘텐츠

- [ ] 세계관 설정
- [ ] 플롯/스토리라인
- [ ] 캐릭터 서사/대사 톤

### 적 AI

- [ ] Contender 다이스풀 배분 AI 로직
- [ ] 네이티얼 Command AI 로직
- [ ] 난이도별 AI 차별화 방식
- [ ] Wild Faction 개수/영지경쟁 참여 여부

### UI/HUD — 시스템

- [ ] 카메라 조작 방식 (줌/패닝)
- [ ] 다이스풀 배분 인터랙션 흐름
- [ ] 네이티얼 Command 지정 UI 흐름
- [ ] 8 Faction 정보 노출 구조

### UI/HUD — 비주얼

- [ ] UI 비주얼 디자인 (스타일/아이코노그래피/레이아웃 미감)

### 전투 연출 — 시스템

- [ ] 연출 트리거 목록
- [ ] 연출 구현 파이프라인 아키텍처

### 전투 연출 — 비주얼

- [ ] VFX 비주얼 디자인 (이펙트 스타일/임팩트감)

### 스킬 시스템

- [ ] 마스터 고유 스킬 종류/발동조건
- [ ] Support Skill 종류/발동조건
- [ ] 네이티얼 스킬 종류/발동조건

### 난이도 모드

- [ ] 난이도 단계 수
- [ ] 난이도별 조절 변수

### 아이템/장비

- [ ] 장비 슬롯 존재 여부
- [ ] 아이템 획득 경로
- [ ] 소모품 vs 영구장비 구분

### 네이티얼 편성/합성/강화

- [ ] 런 시작 전 네이티얼 로스터 편성
- [ ] 네이티얼 합성 시스템 여부
- [ ] 네이티얼 강화 시스템 여부

### 상태이상/버프·디버프

- [ ] 상태이상 종류 목록
- [ ] 상태이상/버프 지속시간·스택 규칙

### 타겟 플랫폼/입력

- [ ] PC/모바일 지원 범위
- [ ] 터치 조작 방식
- [ ] 최소 지원 해상도/화면비

### 튜토리얼/온보딩

- [ ] 첫 플레이 온보딩 시퀀스
- [ ] 심화 시스템 학습 방식

### 밸런싱/플레이테스트

- [ ] 밸런스 검증 지표
- [ ] 시드 고정 리플레이/디버그 도구
- [ ] 플레이테스트 사이클

### 로컬라이제이션

- [ ] 출시 언어 범위
- [ ] 텍스트 파이프라인

### 접근성

- [ ] 색맹 모드
- [ ] 드래그앤드랍 대체 조작 수단
- [ ] UI 스케일링/텍스트 크기 옵션

### 사운드 콘텐츠

- [ ] BGM 트랙 목록
- [ ] SFX 목록

### MVP/콘텐츠 로드맵

- [ ] 출시 시 마스터/챕터 수
- [ ] 출시 제외 기능 목록
- [ ] MVP 성공 기준

### 업데이트 로드맵/시즌제

- [ ] 콘텐츠 공급 주기
- [ ] 시즌제 여부

### 세이브 데이터 스키마

- [ ] 세이브 slot 필드 구조
- [ ] 세이브 account 필드 구조
- [ ] 세이브 패치 호환성 정책

### 퍼포먼스 목표

- [ ] 프레임률 목표
- [ ] Skirmish 동시 연산 부하 예산
- [ ] 모바일 성능 예산

### 분석/텔레메트리

- [ ] 로깅할 텔레메트리 이벤트 목록
- [ ] 텔레메트리 데이터 활용 방식

### 법률/비즈니스

- [ ] 유료화 방식
- [ ] 결제 수단/포털 연동
- [ ] 확률형 아이템 여부 명시 (컴플라이언스)
- [ ] 연령등급/게임물 심의
- [ ] 원작 IP 유사성/클리어런스 범위
