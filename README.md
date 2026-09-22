# Math Stories (중1 수학 — 공식이 아니라 이야기)

A static, Korean-language site that teaches first-year middle-school math
"as stories" rather than as formulas to memorize. Each unit is a single HTML
page with interactive SVG figures (drag, slide, animate), a step-by-step
"assemble the formula" walkthrough, quick check questions, and a free-text
box for the learner to explain the idea in their own words. Progress and notes
are stored only in the browser's `localStorage`. The first unit covers circles
and sectors (원과 부채꼴); more units are planned.

No build step, no framework, no dependencies. The only external requests are
to Google Fonts.

## Why I built it

I built this to help a middle-school student I was tutoring see where the
formulas come from instead of memorizing them. Textbooks state "arc length is
proportional to the central angle" in one line and move on; I wanted a page
where you could actually stamp congruent sectors around a circle and watch the
proportion appear. This is an independent personal project, built on my own
time.

## What this is not

Not affiliated with any school or academy. Contains no student information;
nothing is sent to a server.

## Author

Hyunsoo Ray Shin (Ray). Licensed under MIT, see [LICENSE](LICENSE).

---

## 소개 (Korean)

중학교 1학년 수학을 공식 암기가 아니라 **이야기로** 배우는 학습·복습 사이트입니다.
공식을 외우기 전에, 그 공식이 태어난 과정을 그림으로 직접 그려 보며 익힙니다.

## 구성

| 파일 | 설명 |
| --- | --- |
| `index.html` | 단원 목록(홈). 학기(1·2학기)와 단원 카드를 보여 줍니다. |
| `circle.html` | **원과 부채꼴** 단원 (2학기). |
| `netlify.toml` | Netlify 배포 설정 (빌드 없이 루트를 게시). |

## 단원 추가하는 법

**2학기에 새 단원 추가** — `index.html`의 `<section id="sem-2">` 안 `.grid`에서
아래 카드 블록을 복사해 아이콘·번호·제목·설명과 `href`만 바꾸면 됩니다.

```html
<a class="lesson live" href="새단원.html">
  <span class="badge on">학습하기</span>
  <span class="ico">…아이콘 SVG…</span>
  <span class="num">단원 02</span>
  <h3>단원 이름</h3>
  <p>단원 한 줄 소개.</p>
  <span class="go">탐험 시작 …화살표…</span>
</a>
```

**1학기 시작** — `index.html`의 `<section id="sem-1">` 안 `.emptybox`를
`<div class="grid"> … </div>` 로 바꾸고 같은 형식의 카드를 넣습니다.

각 단원 페이지는 `circle.html`을 복제해서 만들면 디자인이 그대로 유지됩니다.
페이지 상단의 `단원 목록으로` 링크(`index.html`)는 그대로 두세요.

## 로컬에서 보기

빌드가 필요 없습니다. `index.html`을 브라우저에서 바로 열거나, 로컬 서버로 확인하세요.

```bash
python3 -m http.server 8000
# http://localhost:8000
```

## 배포 (Netlify)

1. 이 저장소를 GitHub에 올립니다.
2. Netlify → **Add new site → Import an existing project** → GitHub 저장소 선택.
3. 빌드 명령 없음, 게시 디렉터리 `.` (`netlify.toml`에 이미 설정됨) → 배포.
