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
