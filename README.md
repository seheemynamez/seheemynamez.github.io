# seheemynamez.github.io

GitHub Pages **유저 사이트** — 호스트 루트 `https://seheemynamez.github.io/` 에 노출되는 정적 게이트웨이.

## 무엇

- 메인 콘텐츠(게임 두 가지)는 별도 레포 [seheemynamez/Brian](https://github.com/seheemynamez/Brian) 에 있고 `/Brian/` 경로로 서빙됩니다.
- 이 레포는 호스트 루트(`/`)에 들어왔을 때 보여줄 **게이트웨이 페이지**와 호스트 단위 **SEO 메타(robots.txt, sitemap.xml, llms.txt, OG/JSON-LD)**, 검색엔진 **소유권 확인 파일** 만 들어 있습니다.

## 구조

```
.
├── index.html                                          호스트 루트 게이트웨이
├── favicon.svg
├── og-image.svg
├── robots.txt                                          호스트 루트 sitemap.xml 안내
├── sitemap.xml                                         host root + /Brian/<game>/ 목록
├── llms.txt                                            LLM 친화 요약
├── naver609c7dc6764e26a700f29e4e94de674a.html          네이버 서치어드바이저 인증
└── .nojekyll                                           Jekyll 처리 비활성화
```

## 왜 분리되어 있나

- **네이버 서치어드바이저**가 호스트 단위 등록만 허용 → 호스트 루트(`https://seheemynamez.github.io/`) 에 인증 파일이 있어야 함
- GitHub Pages 의 "유저 사이트"는 `USERNAME/USERNAME.github.io` 레포만 호스트 루트에 매핑되므로 별도 레포가 필요
- 메인 콘텐츠 레포(Brian)는 그대로 두고 호스트 루트만 추가로 운영

## 배포

`main` 브랜치에 푸시하면 GitHub Pages 가 자동 배포. 별도 빌드 없음.
