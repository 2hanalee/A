# ChatGPT 이미지 생성 프롬프트 팩

## 역할 분담 원칙

| ChatGPT가 만드는 것 | ChatGPT가 만들지 않는 것 |
|---|---|
| 로고 워드마크, 진영 엠블럼 | 본문·UI 타이포그래피 (→ 웹폰트) |
| **텍스트 없는** 배경 플레이트 | 글자가 들어간 배너/버튼 |
| 캐릭터 키아트의 텍스트 없는 확장판 | 새 캐릭터 화풍 (기존 34명과 어긋남) |

**인터넷 검색은 '사실 고증'에만** 씁니다 (1946 비키니 환초, 크로스로드 작전 사진의 질감, 환초 지형). 화풍은 검색하지 말고 **우리 기존 이미지를 첨부**해서 맞춥니다. 실존 게임/작가 이름은 프롬프트에 넣지 않습니다.

## 공통 스타일 블록 (모든 프롬프트 끝에 붙이기)

```
STYLE LOCK: match the attached reference images exactly — glossy anime illustration,
high-contrast neon rim light, deep navy-black shadows, cyan/gold light particles,
cinematic depth of field. Color story: TIME = warm gold (#F2B544), SPACE = electric
blue (#3D6BFF). No watermark, no signature, no extra text unless specified.
```

---

## 1. 로고

### 1-1. City of Elegia 마스터 로고
첨부: `Tuna.jpg` 마지막 패널의 로고 크롭

```
Refine the attached "City of Elegia" logo into a clean master version.
Keep the exact lettering layout ("City" small script above, "of" small, "Elegia" large
elegant serif-script). Integrate a subtle broken hourglass (time) in the letter "g"
and a small constellation (space) behind the letters. Silver-white chrome letters
with cold blue glow, a thin gold accent line. Transparent background, centered,
wide composition, 3:1 ratio. Also produce a flat single-color white version for
small sizes.
```
→ 받은 뒤: Claude가 SVG로 트레이싱/재구성하여 웹에서 선명하게 사용

### 1-2. 오로라 유니온 엠블럼

```
Design an emblem for "AURORA UNION", a hero association in a neon city.
Hexagonal shield, an aurora arc crossing a stylized star, thin 1px neon line-art
style matching a sci-fi HUD (like the attached profile card frames). Cyan-white
glow on pure black. Text "AURORA UNION" in a small geometric sans below. Flat,
vector-friendly, symmetrical, no gradients inside lines.
```

### 1-3. 스파이럴 리전 엠블럼
첨부: `images/AP/0.webp`

```
Design an emblem for "SPIRAL LEGION", an invasion force. A spiral vortex made of
puppet strings converging into a single eye. Violet (#A77BFF) neon line-art on
black, menacing but elegant, same HUD line weight as the attached card.
Text "SPIRAL LEGION" small below. Flat, vector-friendly.
```

### 1-4. Bikini City! (기존 로고 보정)
첨부: `images/Tuna/Djfus.png`

```
Clean up the attached "비키니 CITY!" logo: fix the Korean letters so "비키니"
is clearly readable, keep the pink glossy script and blue chrome "CITY!", keep
palm trees, waves and skyline. Remove the female silhouette from the "!" and
replace it with a glowing hourglass to tie it to the main universe. Transparent background.
```

---

## 2. 배경 플레이트 (전부 텍스트 없음, 16:9, 2048px 이상)

| # | 용도 | 프롬프트 |
|---|---|---|
| P1 | 프롤로그 1막 | `Aerial view of a remote Pacific atoll in 1946, black-and-white archival film look, heavy film grain, overcast sky, a few naval ships far away, quiet and ominous. Historically accurate lagoon shape. No text.` |
| P2 | 선택 게이트 | `A neon city at night split vertically down the middle: left half bathed in warm gold light with floating hourglass sand particles, right half in electric blue with constellation lines and shattered space fragments. The seam glows white. Empty center for UI. No people, no text.` |
| P3 | 도시 엘레지아 | `Rebuilt futuristic Korean-style megacity at night, rain-wet streets, holographic billboards without readable text, faint scars of a destroyed old city visible beneath, crane silhouettes, cinematic wide shot. No text.` |
| P4 | DB 배경 텍스처 | `Seamless dark navy sci-fi HUD background texture: faint hexagon grid, thin scanlines, tiny tick marks, extremely subtle, low contrast, tileable, 2048x2048. No text, no numbers.` |
| P5 | 비키니 시티 | `Sunny tropical coastal megacity, turquoise lagoon, palm trees, glass towers, ferris wheel, bright summer anime background art, empty foreground beach for characters. No people, no text.` |

---

## 3. 캐릭터 키아트 확장 (선택)

카드(0.webp)에서 글자를 뺀 와이드 키아트가 있으면 도시에 페이지 히어로가 훨씬 좋아집니다.

```
Using the attached image as the exact character reference (same face, hair, outfit,
colors, pose), recreate ONLY the character illustration with NO UI, NO frames,
NO text. Extend the background to a 21:9 cinematic banner, character on the right
third, empty dark space on the left for website text. Same lighting and rendering.
```
첨부: `images/<ID>/0.webp` + `images/<ID>/7.webp`

---

## 4. 받은 이미지 넘길 때

`assets/generated/<P1|logo-elegia|...>.png` 로 저장 후 커밋해주세요. 파일명이 곧 용도입니다.
