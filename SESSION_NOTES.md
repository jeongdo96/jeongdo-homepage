# 작업 노트 — 2026-04-24 (디자인 정도)

집에서 이어서 작업하기 위한 메모. Claude에게 "SESSION_NOTES.md 읽고 이어서 하자" 라고 말하면 됨.

---

## ✅ 오늘 완료한 작업 (배포됨)

### 1. 한남 아파트 → 상도 더샵 34평 교체
- 시공사진 48장 추가 (`proj3-01.jpg` ~ `proj3-48.jpg`, `proj3-a.jpg`)
- 갤러리 36슬라이드 (가로사진 = 1장, 세로사진 = pair 2장)
- 예쁜 사진 앞쪽, 디테일/반복 뒤쪽 배치
- "RENOVATION · 34평" → "RESIDENTIAL · 34평" 통일 (전 프로젝트)
- 데스크탑: 갤러리 이미지 클릭 시 라이트박스 오픈

### 2. 새 갤러리 페이지 (3개 프로젝트)
- `gallery-proj1.html` — 서초 더샵 포레 (30장)
- `gallery-proj2.html` — 사당 대림아파트 (88장)
- `gallery-proj3.html` — 상도 더샵 (48장)
- 레이아웃: 왼쪽 큰 사진 + 텍스트 / 오른쪽 세로 썸네일 스트립
- 썸네일 hover → 왼쪽으로 작은 프리뷰 팝업 (70px)
- 썸네일 클릭 → 메인 사진 변경
- 메인 사진 클릭 → 라이트박스 (불투명 흰색 0.89, 화살표 사진 가까이 160px)
- 라이트박스 열렸을 때 슬라이드 화살표 자동 숨김
- "다른 프로젝트 보기" 버튼 → `history.back()` (이전 페이지로)
- 썸네일(200px) / 중간(1600px) 이미지 자동 생성 → `thumb/`, `mid/` 폴더

### 3. 메인 사이트와 새 갤러리 통합
- 4페이지 메인 사진 클릭 시 → 기존 인페이지 슬라이드쇼 대신 새 갤러리 페이지 이동
- 모바일 라이트박스 비활성화 (새 갤러리가 대체)

### 4. 마우스 사이드 버튼 네비게이션
- 마우스 뒤로 버튼(4번) → 이전 섹션
- 마우스 앞으로 버튼(5번) → 다음 섹션
- 브라우저 기본 뒤로가기 동작 차단

---

## 🟡 미적용 데모 (아직 적용 안함)

### 완료 페이지 (s6) 편지 추가
- 파일: `demo-complete.html`
- 미리보기: `http://localhost:8081/demo-complete.html?p=6`
- 변경 내용: 상담 완료 후 "편지" 추가
  - 메시지: "이 홈페이지를 한 페이지씩 넘기게 만든 이유는…"
  - "곧 만나뵐 첫 상담에서는 '평당 얼마예요?' 가 아니라 '이 공간에서 어떤 시간을 보내고 싶으세요?' 라는 질문으로…"
  - "당신의 공간이 당신을 닮아갈 수 있도록. — 디자인 정도"
- **다음에 적용할지 결정 후 index.html에 반영하기**

---

## 💡 대화 중 도출한 회사 철학 (중요)

### 타겟 고객 / 안 받고 싶은 고객
- ✅ **원하는 고객**: 집에 애정이 있고, 공간보다 가격을 먼저 묻지 않는 분
- ❌ **거르고 싶은 고객**: 견적 비교 쇼핑객, 집을 단순 수리 대상으로만 보는 사람

### 홈페이지 설계 철학
- 일반 인테리어 회사: 메뉴바로 원하는 페이지 바로 접근 가능
- 정도: **한 페이지씩 다 읽고 넘어가야** 마지막 상담 신청 페이지에 도달
- **이유**: 회사 정보 안 읽고 신청하면 견적 비교용/애정 없는 사람일 확률 높음

---

## 📝 다음 작업 (집 데스크탑에서 이어서)

### 우선순위 1 — 네이버 블로그 작업 (오늘 못함)
**핵심 전략**: 블로그가 홈페이지의 "예열실" 역할

1. **블로그 글 3가지 카테고리로 분류**:
   | 카테고리 | 끝에 붙일 CTA | 도착지 |
   |---|---|---|
   | 철학/가치관 | "정도가 일하는 방식" | `/?from=blog-philosophy` → 철학 페이지부터 |
   | 시공 사례 | "전체 포트폴리오 보기" | `/?from=blog-project` → 프로젝트 섹션부터 |
   | 인테리어 팁 | "정도와 상담받기" | `/?from=blog-tip` → 상담폼부터 |

2. **첫 블로그 글 작성**: "왜 이 홈페이지는 한 페이지씩 넘기게 되어 있을까"
   - 초안은 이 대화에서 정리됨 (대화 기록 참조)
   - 두 종류의 손님 비교 → 공간은 사람을 닮습니다 → 그래서 우리는 → 마치며

3. **홈페이지에 URL 파라미터 받는 JS 추가**
   - `?from=blog-philosophy` 등 들어오면 첫 섹션 다르게

### 우선순위 2 — 완료 페이지 편지 적용
- `demo-complete.html`에서 만든 편지를 `index.html`에 반영
- 적용 후 GitHub 푸시 → designjeongdo.co.kr 자동 반영

### 우선순위 3 (한 달 내)
- GA4 설치 → 섹션별 체류시간, 이탈 지점 추적
- 데이터 기반 개선

---

## 🔗 주요 URL

### 라이브 (배포된 버전)
- https://designjeongdo.co.kr (메인)
- https://designjeongdo.co.kr/gallery-proj1.html (서초 더샵 포레)
- https://designjeongdo.co.kr/gallery-proj2.html (사당 대림아파트)
- https://designjeongdo.co.kr/gallery-proj3.html (상도 더샵)

### 로컬 데모 (미적용)
- `http://localhost:8081/demo-complete.html?p=6` (완료 페이지 편지 데모)
- `http://localhost:8081/demo-gallery.html` (단일 갤러리 데모)
- `http://localhost:8081/demo-index.html` (통합 데모, 이미 본 적용과 동일)

### 깃허브
- https://github.com/jeongdo96/jeongdo-homepage

---

## 🛠️ 개발 환경

- **로컬 서버 시작**: `npx http-server /home/kyb0319/jeongdo -p 8081 -c-1 &`
- **WSL → Windows 브라우저**: `cmd.exe /c start "" "http://localhost:8081/..."`
- **이미지 리사이즈** (sharp 설치됨):
  ```js
  await sharp(file).resize(200, 200, {fit:'cover'}).jpeg({quality:70}).toFile('thumb/' + file);
  await sharp(file).resize(1600, null, {fit:'inside'}).jpeg({quality:80}).toFile('mid/' + file);
  ```

---

## 📂 파일 구조

```
/home/kyb0319/jeongdo/
├── index.html              ← 메인 (배포됨)
├── gallery-proj1.html      ← 서초 갤러리 (배포됨)
├── gallery-proj2.html      ← 사당 갤러리 (배포됨)
├── gallery-proj3.html      ← 상도 갤러리 (배포됨)
├── demo-complete.html      ← 완료 페이지 편지 데모 (미적용)
├── demo-gallery.html       ← 단일 갤러리 데모
├── demo-index.html         ← 통합 데모
├── proj1-*.jpg             ← 서초 사진
├── proj3-*.jpg             ← 상도 사진
├── sd*.jpg                 ← 사당 사진
├── thumb/                  ← 200px 썸네일
├── mid/                    ← 1600px 중간 이미지
└── SESSION_NOTES.md        ← 이 파일
```
