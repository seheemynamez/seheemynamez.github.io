# seheemynamez.github.io

GitHub Pages **유저 사이트** — 호스트 루트 `https://seheemynamez.github.io/` 에 노출되는 정적 메인 페이지.

## 무엇

- **메인 진입 페이지** (`index.html`) 가 호스트 루트에 노출됩니다 — 게임 카드 두 장 (오목대전 / 2048), About 섹션, 풀 SEO 메타 (OG / Twitter Card / JSON-LD `ItemList`) 포함. `<link rel="canonical">` 도 이 루트를 가리킴.
- 게임 자체 콘텐츠는 별도 레포 [seheemynamez/Brian](https://github.com/seheemynamez/Brian) 에 있고 `/Brian/omok/` · `/Brian/2048/` 경로로 서빙됩니다 (`https://seheemynamez.github.io/Brian/` 자체는 인덱스가 없어 404). 메인 페이지의 게임 카드는 절대 경로 `/Brian/<game>/` 로 같은 호스트 안의 다른 레포로 이동합니다.
- 호스트 단위 SEO 메타 (`robots.txt`, `sitemap.xml`, `llms.txt`, `og-image.svg`, `favicon.svg`) 와 검색엔진 **소유권 확인 파일** (네이버 / Google) 도 이 레포에서 관리합니다.

## 구조

```
.
├── index.html                                          메인 페이지 (게임 카드 2장 + About + OG/JSON-LD ItemList)
├── favicon.svg                                         사이트 파비콘 (호스트 루트 절대 URL 로 게임 페이지가 참조)
├── og-image.svg                                        OG/Twitter Card 이미지
├── robots.txt                                          호스트 루트 sitemap.xml 안내
├── sitemap.xml                                         host root + /Brian/<game>/ 목록
├── llms.txt                                            LLM 친화 요약
├── naver609c7dc6764e26a700f29e4e94de674a.html          네이버 서치어드바이저 인증
├── googled511cee7148991dc.html                         Google Search Console 파일 인증 (백업)
└── .nojekyll                                           Jekyll 처리 비활성화
```

## 왜 분리되어 있나

- **네이버 서치어드바이저**가 호스트 단위 등록만 허용 → 호스트 루트(`https://seheemynamez.github.io/`) 에 인증 파일이 있어야 함
- **Google Search Console** 도 호스트 단위 등록 시 같은 위치의 인증 파일 / 메타 태그 필요
- GitHub Pages 의 "유저 사이트"는 `USERNAME/USERNAME.github.io` 레포만 호스트 루트에 매핑되므로 별도 레포가 필요
- Brian 레포의 게임 본문은 그대로 두고, 사이트의 메인 페이지와 호스트 단위 메타·인증 파일만 이 레포에서 운영

## 배포

`main` 브랜치에 푸시하면 GitHub Pages 가 자동 배포. 별도 빌드 없음.
