# best-ing

염지은 · 이커머스 포트폴리오 2026

빌드 도구 없이 HTML 한 장으로 동작하는 정적 사이트입니다. Vercel로 배포합니다.

운영 주소: <https://best-ing.vercel.app>

## 구조

```
.
├── portfolio/
│   ├── index.html   # 포트폴리오 본문 (CSS·JS 인라인, 이미지도 전부 내장)
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

## 되돌린 내역

2026-09-17, 아래 작업을 넣었다가 되돌렸습니다. 내용이 많아져 전달하려는 바가
흐려진다고 판단했기 때문입니다. 필요하면 커밋에서 다시 꺼내면 됩니다.

| 커밋 | 내용 |
|---|---|
| `04a670d` | 카드뉴스 섹션 (인스타 피드 + 라이트박스, 카드 19장) |
| `981a62c` | 운영 도구 섹션 (대시보드 3종 목업) · 광고 배너 시트 |
| `bb77329` | 섹션 순서 변경 |
| `24073a4` | 7섹션 MECE 재편 |

되살리려면 예를 들어 `git checkout 04a670d -- portfolio/img` 처럼 꺼냅니다.
