# junwoobeck.github.io — 콘텐츠 스펙

이 문서는 al-folio v1.x 템플릿 레포에 반영할 콘텐츠 명세다.
- 사이트 노출 텍스트는 전부 영어, 한국어는 지시문이다.
- front matter 키나 파일 구조가 실제 레포(v1.x)와 다르면 **레포 구조를 우선**하고, 여기 내용은 값/본문으로만 사용한다.
- `TODO` 표시는 사람이 채울 항목이다. **추측으로 채우지 말 것.**

---

## 1. `_config.yml` — 아래 키만 수정 (파일 전체 교체 금지)

```yaml
first_name: Jun Woo
middle_name:
last_name: Beck
email: jbeck85@gatech.edu
description: >
  Jun Woo Beck — M.S. student in Music Technology at Georgia Tech
  (Music Informatics Group). Machine learning and music information
  retrieval for sound effects and music audio.
keywords: music technology, machine learning, music information retrieval, sound effects, audio

url: https://junwoobeck.github.io   # 이미 설정됨 — 확인만
baseurl: ""                          # 이미 설정됨 — 확인만

github_username: JunWooBeck
linkedin_username:                   # TODO: LinkedIn 커스텀 URL 아이디
scholar_userid:                      # 비워둠 — DAFx 인덱싱 후 추가 예정
```

jekyll-scholar 계열의 저자 이름 강조 설정이 있으면 (예: `scholar:` 블록의 `last_name` / `first_name`):

```yaml
scholar:
  last_name: [Beck]
  first_name: [Jun Woo, J. W., J.]
```

---

## 2. `_bibliography/papers.bib` — 전체 교체

```bibtex
@inproceedings{beck2026envsounducs,
  abbr        = {DAFx},
  bibtex_show = {true},
  selected    = {true},
  title       = {Sound Effects Dataset Unification with the Universal Category System},
  author      = {Beck, Jun Woo and Lerch, Alexander},
  booktitle   = {Proceedings of the International Conference on Digital Audio Effects (DAFx)},
  year        = {2026},
  address     = {Boston, MA, USA},
  note        = {Accepted; oral presentation, September 2026},
  code        = {https://github.com/JunWooBeck}
}

@inproceedings{oh2026singingskin,
  abbr        = {ICMC},
  bibtex_show = {true},
  selected    = {true},
  title       = {The Singing Skin: An Audience-Centered Biofeedback System for Musical Interaction Based on Galvanic Skin Response},
  author      = {Oh, Eun Ji and Beck, Jun Woo and Smith, A.},
  booktitle   = {Proceedings of the International Computer Music Conference (ICMC)},
  year        = {2026},
  address     = {Hamburg, Germany},
  note        = {In press}
}
```

- TODO: DAFx 항목의 `code`는 현재 GitHub 프로필 링크임 → EnvSound-UCS **메인 레포 URL**로 교체.
- TODO: `Smith, A.`의 풀네임 확인 후 `Smith, <FirstName>` 형태로 교체.
- PDF 링크(`pdf` 필드)는 프로시딩 공개 전이므로 넣지 않는다. 공개 후 추가.

---

## 3. `_pages/about.md`

front matter는 기존 파일 구조를 유지하되 아래 값으로:

```yaml
layout: about
title: about
permalink: /
subtitle: >
  M.S. student in Music Technology · Music Informatics Group, Georgia Tech

profile:
  align: right
  image: prof_pic.jpg        # TODO: 본인 사진으로 교체 (assets/img/)
  image_circular: false
  more_info: >
    <p>Atlanta, GA</p>

news: true
selected_papers: true
social: true
```

본문 (기존 데모 본문 전체 교체):

```markdown
I am a Master's student in Music Technology at the Georgia Institute of
Technology, working in the Music Informatics Group with
[Dr. Alexander Lerch](https://www.alexanderlerch.com/). My research applies
machine learning and music information retrieval to sound effects and music
audio.

I am the first author of a DAFx 2026 paper on sound-effects dataset
unification (EnvSound-UCS) and a co-author of an ICMC 2026 paper on an
audience-centered biofeedback system. My master's thesis, beginning Fall
2026, develops multimodal music recommendation for video — combining visual
and text inputs to produce natural-language music suggestions.

Before Georgia Tech, I earned a B.M. in Electronic Production and Design at
Berklee College of Music and worked in Seoul as a recording/mixing engineer
and string arranger; I am also a classically trained violinist. This
combination of musicianship, studio practice, and computational methods
shapes how I approach audio ML research.

My full CV is available [as a PDF](/assets/pdf/JunWooBeck_CV.pdf).

<!-- TODO: 음악 포트폴리오 사이트 완성 후 여기에 링크 한 줄 추가 -->
```

---

## 4. `_news/` — 데모 뉴스 전부 삭제 후 아래 4개 생성

**모든 날짜는 placeholder다. TODO: 실제 날짜로 교체.**

### `_news/announcement_1.md`
```markdown
---
layout: post
date: 2025-08-18 09:00:00-0400
inline: true
related_posts: false
---

I joined the Music Informatics Group at Georgia Tech as an M.S. student in
Music Technology, advised by Dr. Alexander Lerch.
```

### `_news/announcement_2.md`
```markdown
---
layout: post
date: 2026-01-15 09:00:00-0500
inline: true
related_posts: false
---

Awarded a GTCMT Seed Grant by the Georgia Tech Center for Music Technology.
```

### `_news/announcement_3.md`
```markdown
---
layout: post
date: 2026-05-15 09:00:00-0400
inline: true
related_posts: false
---

*The Singing Skin*, led by Eun Ji Oh, is in press at ICMC 2026 (Hamburg). I
designed and implemented the system's full audio component.
```

### `_news/announcement_4.md`
```markdown
---
layout: post
date: 2026-06-15 09:00:00-0400
inline: true
related_posts: false
---

My first-author paper *Sound Effects Dataset Unification with the Universal
Category System* (with Alexander Lerch) was accepted to DAFx 2026 for an
oral presentation in Boston this September.
```

---

## 5. `_projects/` — 데모 프로젝트 전부 삭제 후 아래 4개 생성

카테고리는 `research` 하나만 사용. `_pages/projects.md`의 `display_categories`도 이에 맞게 수정.
이미지(`img`)는 아직 없음 — 필드 생략 (TODO: 추후 썸네일 추가).

### `_projects/envsound-ucs.md`
```markdown
---
layout: page
title: EnvSound-UCS
description: Unifying environmental sound-effects datasets under the Universal Category System (DAFx 2026)
importance: 1
category: research
---

A rule-based tag-to-UCS conversion framework that unifies environmental
sound-effects datasets under the Universal Category System, reaching
98.5–100% automatic conversion across FSD50K, AudioSet, and ESC-50. The
result is **EnvSound-UCS**, a 58,057-clip corpus spanning 59 categories,
validated with audio-classification benchmarks. The conversion pipeline,
tools, and converted datasets are open-sourced across four public
repositories.

First-author paper at DAFx 2026 (with Alexander Lerch; oral presentation,
September 2026). [Code](https://github.com/JunWooBeck)
<!-- TODO: Code 링크를 메인 레포 URL로 교체 -->
```

### `_projects/multimodal-music-recommendation.md`
```markdown
---
layout: page
title: Multimodal Music Recommendation for Video
description: Master's thesis — beginning Fall 2026
importance: 2
category: research
---

My master's thesis project, beginning Fall 2026: a multimodal model that
recommends fitting music for silent video by combining visual and text
inputs to produce natural-language music recommendations.
```

### `_projects/textron-panel.md`
```markdown
---
layout: page
title: Speaker-Panel Acoustic Evaluation & Digital EQ
description: Industry collaboration with Textron (Spring 2026)
importance: 3
category: research
---

Conducted controlled acoustic measurements (THD, SINAD, frequency response)
of speaker-panel audio quality in an isolation room against a
consumer-laptop reference, and designed parametric EQ tuning presets that
substantially reduced measured harmonic distortion and flattened the
frequency response.
```

### `_projects/singing-skin.md`
```markdown
---
layout: page
title: The Singing Skin
description: Audience-centered biofeedback system for musical interaction (ICMC 2026)
importance: 4
category: research
---

An audience-centered biofeedback system that translates real-time galvanic
skin response (GSR) signals from listeners into interactive musical output.
I designed and implemented the full audio system. Led by Eun Ji Oh;
in press at ICMC 2026 (Hamburg) and performed in a live concert in May 2026.
```

---

## 6. CV 페이지

- 데이터 기반 CV(`cv.yml` / JSON Resume / RenderCV) 방식은 사용하지 않는다.
- `/assets/pdf/JunWooBeck_CV.pdf` 다운로드 방식으로 전환 (버전에서 `cv_pdf` front matter를 지원하면 그것 사용, 아니면 페이지 본문을 다운로드 링크로 교체).
- TODO: PDF 파일 자체는 사용자가 docx→PDF 파이프라인에서 최신본을 export해 `assets/pdf/JunWooBeck_CV.pdf`로 업로드.

---

## 7. 네비게이션 및 정리

- 노출 메뉴: **about / publications / projects / cv** 만.
- blog, 데모용 dropdown/기타 페이지, 사용하지 않는 컬렉션(books, teachings 등)은 nav에서 제거하거나 비활성화.
- 템플릿 데모 콘텐츠(샘플 포스트, Einstein 예시 자료, 샘플 뉴스·프로젝트) 삭제.

---

## TODO 요약 (사람이 채울 것)

1. 뉴스 4건의 날짜 → 실제 날짜로
2. papers.bib 및 EnvSound-UCS 프로젝트의 `code` 링크 → 메인 레포 URL로
3. ICMC 공저자 `Smith, A.` 풀네임 확인
4. `linkedin_username`
5. `prof_pic.jpg` — 본인 사진 업로드
6. `assets/pdf/JunWooBeck_CV.pdf` — 최신 연구용 CV export 후 업로드
7. (선택) 프로젝트 썸네일 이미지
8. (추후) `scholar_userid` — DAFx 인덱싱 후 / 음악 포트폴리오 링크 — 사이트 완성 후
9. Singing Skin 라이브 공연(May 2026) 표기 사실 확인 — 아니면 해당 구절 삭제
