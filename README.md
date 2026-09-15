# best-ing

염지은 · 이커머스 포트폴리오 2026

빌드 도구 없이 HTML 한 장으로 동작하는 정적 사이트입니다. Vercel로 배포합니다.

## 구조

```
.
├── portfolio/
│   ├── index.html   # 포트폴리오 본문 (CSS·JS 인라인)
│   └── robots.txt   # 검색엔진 수집 차단
├── vercel.json      # 배포 설정 (outputDirectory: portfolio)
└── README.md
```

## 로컬에서 보기

`portfolio/index.html` 을 브라우저로 바로 열면 됩니다. 로컬 서버가 필요하면:

```bash
npx serve portfolio
```

## 배포

`master` 브랜치에 푸시하면 Vercel이 자동으로 다시 배포합니다.
`vercel.json` 의 `outputDirectory` 가 `portfolio` 를 가리키므로,
사이트 루트(`/`)에서 `portfolio/index.html` 이 서빙됩니다.

## 메모

- 검색 노출을 원하지 않아 `<meta name="robots" content="noindex">` 와 `robots.txt` 를 함께 두었습니다. 공개하려면 두 곳을 모두 지우세요.
- 폰트는 Google Fonts(IBM Plex Sans KR / Mono)를 CDN에서 불러옵니다.
- 다크 모드는 `prefers-color-scheme` 를 따라갑니다.
