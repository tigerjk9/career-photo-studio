# 👔 직업 변신 사진관 (Career Photo Studio)

> **내 사진 한 장 → 8가지 직업 모습으로 변신!**
> Google Gemini 2.5 Flash Image(나노 바나나)를 활용해 학교·진로 부스에서 즉석 인쇄 가능한 직업카드를 생성합니다.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Try%20Now-black?logo=vercel)](https://career-photo-studio.vercel.app/)
[![Gemini](https://img.shields.io/badge/Gemini-2.5%20Flash%20Image-blue)](https://ai.google.dev/gemini-api/docs/image-generation)
[![BYOK](https://img.shields.io/badge/Bring%20Your%20Own-API%20Key-orange)](https://aistudio.google.com/apikey)
[![Print Ready](https://img.shields.io/badge/Print-13%3A10%20Card-emerald)](#)

---

## 🎯 기획 의도

> "내가 의사가 된다면? 우주비행사가 된다면?"

진로 체험 부스에서 학생이 막연하게 상상하던 직업의 모습을 **즉석에서 시각화**하여, 미래 자신의 모습을 손에 쥐고 갈 수 있도록 한 도구입니다. 13:10 가로 비율로 출력되어 **포토프린터 직업카드** 인쇄에 최적화되어 있습니다.

---

## ✨ 주요 기능

| 기능 | 설명 |
|------|------|
| 📤 **사진 한 장 업로드** | JPG/PNG, 얼굴이 잘 보이는 사진 권장 |
| 🎭 **8개 직업 동시 변환** | 한 번 클릭으로 8장 병렬 생성 |
| 📐 **13:10 인쇄 비율** | 직업카드·포토프린터 출력에 최적화 |
| 🔍 **결과 확대 보기** | 모달 뷰로 디테일 확인 |
| 💾 **개별/전체 다운로드** | 한 장씩 또는 ZIP 일괄 |
| 🔐 **BYOK 방식** | 사용자 본인의 Gemini API 키 사용 (브라우저 내에서만 처리) |
| 🧬 **얼굴 정체성 보존** | 인종·성별·나이대 유지하고 복장·배경만 변환 |

---

## 🚀 바로 사용하기

👉 **[https://career-photo-studio.vercel.app/](https://career-photo-studio.vercel.app/)**

### 사용 단계

1. **사진 업로드** - 정면 얼굴 사진 권장
2. **API 키 입력** - [Google AI Studio](https://aistudio.google.com/apikey)에서 무료 발급
3. **「✨ 직업 변신 시작!」** 클릭 → 8장 동시 생성 (10~30초)
4. **결과 저장** - 마음에 드는 카드 개별 저장 또는 ZIP 일괄 다운로드
5. **포토프린터 인쇄** → 학생에게 직업카드로 배부

> ⚠️ AI는 얼굴 특징을 항상 완벽히 반영하진 못합니다. 마음에 드는 결과를 위해 여러 번 시도해 보세요.

---

## 👔 지원 직업 8종

| # | 직업 | 핵심 비주얼 |
|---|------|------------|
| 1 | 🩺 **의사** | 흰 가운, 청진기, 모던 병원 복도 |
| 2 | 👨‍🍳 **셰프** | 흰 셰프복+모자, 고급 레스토랑 주방 |
| 3 | 🚀 **우주비행사** | 우주복, 헬멧 들고 우주정거장 + 지구 배경 |
| 4 | 🎨 **디자이너** | 모던 캐주얼, 디자인 스튜디오 |
| 5 | 🔬 **과학자** | 흰 가운, 안전 안경, 첨단 실험실 |
| 6 | 📚 **교사** | 단정한 정장, 책 들고 밝은 교실 |
| 7 | 💻 **개발자** | 캐주얼+후디, 멀티 모니터 사무실 |
| 8 | ⚽ **운동선수** | 유니폼, 골든아워 스타디움 |

---

## 🛠️ 기술 스택

| 분류 | 기술 |
|------|------|
| **AI 모델** | Google **Gemini 2.5 Flash Image** (`gemini-2.5-flash-image`) |
| **프론트엔드** | Vanilla JavaScript (단일 `index.html` 파일) |
| **스타일링** | Tailwind CSS (CDN) + 커스텀 글래스/오로라 디자인 |
| **압축 다운로드** | [JSZip](https://stuk.github.io/jszip/) 3.10.1 |
| **타이포그래피** | Pretendard |
| **호스팅** | Vercel (정적, GitHub 연동 자동 배포) |

> 💡 백엔드 서버 없음 · 빌드 도구 없음 · `index.html` 단일 파일

---

## 💡 핵심 노하우: 직업별 프롬프트 설계

각 직업 프롬프트에 공통 접미사를 붙여 **얼굴 정체성 보존 + 13:10 인쇄 출력**을 강제합니다.

```
The original person's core facial features, ethnicity, age range, and gender must be preserved.
Highly realistic, natural lighting, professional photography quality.
The image must not contain any text or letters.
Final output: high-resolution horizontal image with strict 13:10 aspect ratio,
suitable for printing as a career card.
```

각 직업별로 **복장·도구·배경·표정·조명**을 구체적으로 명시하여 AI가 직업의 분위기를 정확히 표현하도록 했습니다.

---

## 📦 로컬 실행

```bash
git clone https://github.com/tigerjk9/career-photo-studio.git
cd career-photo-studio
python -m http.server 8000
# 브라우저에서 http://localhost:8000 접속
```

> 💡 `index.html`을 직접 열어도 동작하지만, 카메라/HTTPS 정책상 **로컬 서버 사용 권장**.

---

## 🔑 API 키 발급 가이드

1. [Google AI Studio](https://aistudio.google.com/apikey) 접속
2. Google 계정 로그인
3. **"Create API Key"** 클릭 → 키 복사
4. 본 앱 입력란에 붙여넣기

> 🔒 **보안:** API 키는 사용자 브라우저 내에서만 사용되며, 외부 서버로 전송·저장되지 않습니다.

---

## 📁 저장소 구성

```
career-photo-studio/
├── README.md       # 본 문서
├── index.html      # 단일 파일 웹앱 (HTML + CSS + JS 통합)
└── .gitignore
```

---

## 🎯 활용 사례

- 🎓 **학교 진로 부스** - AI 직업카드 즉석 인쇄
- 🏫 **진로 동아리 활동** - 미래 직업 시각화 워크숍
- 📸 **진로 박람회** - 체험 + 기념품 한 번에
- 🧑‍🏫 **AI·진로 융합 수업** - 멀티모달 모델 시연

---

## 🐛 알려진 제약

- 얼굴 인식이 어려운 사진(측면, 가림, 저해상도)은 결과 품질 저하
- 모델 응답 시간: 8장 동시 생성 시 10~30초 소요
- API 무료 할당량 초과 시 429 오류 (자동 재시도 2회)

---

## 🌟 향후 개선 아이디어

- [ ] 직업 선택 옵션 (필수/선택 분리)
- [ ] 직업별 한국 문화 맞춤 옵션 (한복 의사, 한국 우주청 등)
- [ ] 학년별 추천 직업 큐레이션
- [ ] 양면 직업카드 PDF (앞면 사진 + 뒷면 직업 설명)

---

## 🔗 관련 프로젝트 (진로 시리즈)

| 프로젝트 | 설명 | 라이브 |
|---------|------|--------|
| **Career Photo Studio** *(본 프로젝트)* | 사진 → 8가지 직업 변신 | [link](https://career-photo-studio.vercel.app/) |
| **RIASEC Career Cards** | 흥미 검사 → 매칭 직업 3장 카드 | [link](https://riasec-career-cards.vercel.app/) |
| **Future Business Card** | 10년 후 나의 명함 + 자서전 | [link](https://future-business-card.vercel.app/) |

본 프로젝트는 [AI Hands-On 부스](https://ai-hands-on-booth-v2.vercel.app/)에 등록되어 있습니다.

---

## 🙏 크레딧

- **Google Gemini 2.5 Flash Image** — 멀티모달 이미지 생성
- **Tailwind CSS** · **Pretendard** · **JSZip**

---

## 📝 라이선스

MIT License

---

## 👤 제작자

**김진관 (닷커넥터)**
- GitHub: [@tigerjk9](https://github.com/tigerjk9)
- Linktree: [litt.ly/dot_connector](https://litt.ly/dot_connector)

---

> 👔 **지금 바로 [직업 변신 사진관](https://career-photo-studio.vercel.app/)에서 미래의 내 모습을 만나보세요!**
