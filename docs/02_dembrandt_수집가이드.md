# 레퍼런스 수집 가이드 (dembrandt)

dembrandt는 **디자인 토큰**(색·폰트·크기·간격·라운드·그림자·버튼 등)만 추출합니다.
레이아웃·스크롤 연출·정보구조는 잡히지 않으므로 **반드시 스크린샷과 메모를 함께** 주세요.

## 1. 레퍼런스 고르는 기준

- 3~6개면 충분합니다. 많을수록 평균값이 돼서 오히려 흐려집니다.
- 역할을 나눠서 고르세요:
  - **A. 스크롤 스토리텔링** 이 뛰어난 곳 (게임 티저/세계관 사이트)
  - **B. 캐릭터 도감/로스터** 가 뛰어난 곳 (필터, 카드 그리드, 상세 페이지)
  - **C. HUD/SF 인터페이스** 감성이 좋은 곳
  - **D. AI 캐릭터 채팅 플랫폼** 의 캐릭터 상세/대화 시작 화면 (CTA 동선 참고)

## 2. 명령어 (사이트당 1회)

```bash
npx dembrandt install-browser            # 최초 1회

# 데스크톱
npx dembrandt <URL> --save-output --dtcg --design-md --crawl 5 --wcag --slow \
  --screenshot ref/<이름>-desktop.png

# 모바일
npx dembrandt <URL> --save-output --mobile --screenshot ref/<이름>-mobile.png
```

- `--design-md` : AI 에이전트용 DESIGN.md — 제가 읽기 가장 좋은 형식
- `--dtcg` : W3C 표준 토큰 — 나중에 우리 토큰과 비교할 때 사용
- `--crawl 5` : 메인 1장만 보면 서브페이지 컴포넌트를 놓침
- 무거운 연출 사이트는 `--slow` 필수

## 3. 제출 형식 (사이트당 폴더 1개)

```
references/
└─ <이름>/
   ├─ output/            # dembrandt --save-output 결과 전체
   ├─ DESIGN.md
   ├─ desktop.png / mobile.png
   ├─ fullpage-*.png     # 브라우저 확장으로 찍은 전체 스크롤 캡처 (중요!)
   └─ note.md            # 아래 3줄만
```

`note.md` 예시:

```
URL: https://...
훔칠 것: 캐릭터 선택 시 배경색이 캐릭터 컬러로 전환되는 연출
버릴 것: 폰트가 너무 얇아서 한글에선 안 읽힐 것 같음
```

"훔칠 것" 한 줄이 토큰 JSON 100줄보다 기획에 더 중요합니다.

## 4. 주의

- 로그인 필요 페이지는 `--login --save-storage-state` 로 본인 계정 세션만 사용
- 레퍼런스의 브랜드 컬러·로고를 그대로 쓰지 않습니다 — 비율(타입 스케일, 간격 리듬, 대비)만 참고
