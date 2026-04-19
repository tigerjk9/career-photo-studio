# CLAUDE.md — 직업 변신 사진관

## 한 줄 정의
사진 한 장 → 8가지 직업 모습으로 변환 → 13:10 인쇄용 직업카드.

## 라이브 / 저장소
- 🌐 https://career-photo-studio.vercel.app/
- 🐙 https://github.com/tigerjk9/career-photo-studio

## 기술 스택
- 단일 `index.html` (Vanilla JS)
- Tailwind CSS CDN + Pretendard + JSZip 3.10.1
- Gemini 2.5 Flash Image (`gemini-2.5-flash-image`, BYOK)

## 핵심 데이터 구조
- `CAREERS[]` 8개: `{id, emoji, name, color, prompt}` (의사·셰프·우주비행사·디자이너·과학자·교사·개발자·운동선수)
- 모든 프롬프트에 `COMMON_SUFFIX` 자동 결합 (얼굴 보존 + 13:10 인쇄용)
- `selectedIdx: Set` — 사용자가 체크한 직업 인덱스만 호출

## 핵심 결정
- **8장 동시 → 사용자 선택** (예산 절감) — 기본 1개, 「전체 선택/해제」 토글
- **얼굴 정체성 보존 프롬프트** — `core facial features, ethnicity, age range, gender preserved`
- **Before/After 슬라이더** — 결과 카드 위 원본 오버레이, pointer events로 좌우 드래그

## 자주 마주치는 이슈
- **8개 모두 호출하면 비용↑:** UI에서 기본 1개 + 안내 문구로 유도
- **얼굴 흐리게 변환:** 사진 해상도/정면 여부에 따라 결과 편차 큼 → 재시도 안내

## 변경 핵심 이력
- 2026-04-19: 초기 출시 → 사용자 선택 모드 → Before/After 슬라이더

## 관련 문서
- [PRD.md](./PRD.md)
