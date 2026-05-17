# SCM 데이터 파이프라인·KPI 대시보드 포트폴리오

SCM 운영기획 의사결정 자동화를 검증하기 위해 만든 AI 데이터 파이프라인·KPI 대시보드 결과물 2종 모음.

## 구성

```
portfolio/
├── index.html                ← 케이스 스터디 진입점
├── dashboards/
│   ├── pipeline/index.html   ← AI 데이터 파이프라인 대시보드 (scm-data-v1, 8단계)
│   └── outbound/             ← 물류센터 입출고 KPI 대시보드 v3
│       ├── index.html
│       └── data/dashboard.json
├── assets/
└── README.md
```

## 로컬에서 보기

정적 파일이라 더블클릭으로도 열리지만, `outbound` 대시보드는 `fetch()` 로 JSON 을 불러오므로 **로컬 HTTP 서버**가 필요합니다.

```powershell
# 포트폴리오 디렉터리에서
python -m http.server 8080
# 또는 Node.js
npx serve .
```

이후 `http://localhost:8080/` 접속.

## 배포 (GitHub Pages)

자세한 절차는 [DEPLOY.md](./DEPLOY.md) 참조.

## 공개 정책

- 사이트는 공개 URL이지만 `<meta name="robots" content="noindex, nofollow">` 로 검색엔진 색인을 차단함
- 데이터는 모두 샘플·모의 데이터로, 어떤 실 회사 데이터도 포함하지 않음
- 개인 식별 정보(이름·연락처)는 사이트에 노출하지 않음 — 면접·서류 제출 단계에서 별도 자료로 전달
