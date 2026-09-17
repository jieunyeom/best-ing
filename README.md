# best-ing

염지은 · 이커머스 포트폴리오 2026

빌드 도구 없이 HTML 한 장으로 동작하는 정적 사이트입니다. Vercel로 배포합니다.

운영 주소: <https://best-ing.vercel.app>

## 구조

```
.
├── portfolio/
│   ├── index.html         # 포트폴리오 본문 (CSS·JS 인라인)
│   ├── img/cardnews/      # 카드뉴스 19장 (가습기 10 · 토스터기 9)
│   ├── img/creative/      # 운영 배너 소재 시트 2장
│   └── robots.txt         # 검색엔진 수집 차단
├── vercel.json      # 배포 설정 (outputDirectory: portfolio)
└── README.md
```

## 로컬에서 보기

`portfolio/index.html` 을 브라우저로 바로 열면 됩니다. 로컬 서버가 필요하면:

```bash
npx serve portfolio
```

## 배포

Vercel CLI로 직접 올립니다.

```bash
vercel --prod
```

`vercel.json` 의 `outputDirectory` 가 `portfolio` 를 가리키므로,
사이트 루트(`/`)에서 `portfolio/index.html` 이 서빙됩니다.

Git 연동(푸시하면 자동 배포)은 아직 걸어두지 않았습니다.
필요하면 Vercel 프로젝트 설정의 Git 탭에서 이 레포를 연결하세요.

## 메모

- 검색 노출을 원하지 않아 `<meta name="robots" content="noindex">` 와 `robots.txt` 를 함께 두었습니다. 공개하려면 두 곳을 모두 지우세요.
- 폰트는 Google Fonts(IBM Plex Sans KR / Mono)를 CDN에서 불러옵니다.
- 다크 모드는 `prefers-color-scheme` 를 따라갑니다.

## 확대 보기 컴포넌트

지면을 늘리지 않으려고, 큰 화면은 전부 `한 줄 썸네일 → 클릭 확대` 로 넣었습니다.

- `.ztile` + `<template>` — 업무 시트 2종, 대시보드 3종.
  썸네일은 템플릿을 복제해 `transform: scale()` 로 축소한 것이고,
  누르면 라이트박스가 원본 크기로 다시 복제해 띄웁니다. 이미지 파일이 아니라 항상 선명합니다.
- `.ftile` — 카드뉴스. 덱 단위로 좌우 이동 · 키보드 · 스와이프.
- `.shot` — 배너 소재 시트. 가로로 긴 단일 이미지.
