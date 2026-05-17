# GitHub Pages 배포 가이드

## 1. 사전 준비 (1회만)

- GitHub 계정
- Git for Windows 설치 (이미 있음)

## 2. 새 저장소 생성

GitHub 웹사이트에서:

1. https://github.com/new 접속
2. **Repository name**: `portfolio` (또는 본인이 원하는 이름)
3. **Public** 선택 (Private 은 GitHub Pages 사용 시 유료)
4. **Add a README** 체크하지 말 것 (이미 있음)
5. **Create repository** 클릭

## 3. 로컬 → GitHub 푸시

PowerShell 또는 Git Bash 에서:

```powershell
cd C:\Users\rkadu\ai-ppt\portfolio

git init
git add .
git commit -m "Initial portfolio: AI data pipeline + SCM KPI dashboards"
git branch -M main
git remote add origin https://github.com/<YOUR-GITHUB-USERNAME>/portfolio.git
git push -u origin main
```

`<YOUR-GITHUB-USERNAME>` 부분만 본인 GitHub 사용자명으로 교체.

처음 push 시 GitHub 인증 창이 뜨면 GitHub 계정으로 로그인.

## 4. GitHub Pages 활성화

GitHub 저장소 페이지에서:

1. **Settings** 탭 클릭
2. 좌측 사이드바 **Pages** 클릭
3. **Source**: `Deploy from a branch` 선택
4. **Branch**: `main` / `/ (root)` 선택 → **Save**
5. 1~2분 대기

배포 완료 후 다음 URL로 접속:

```
https://<YOUR-GITHUB-USERNAME>.github.io/portfolio/
```

## 5. URL 전달

이력서·자기소개서·면접 단계에서 위 URL을 별도 자료로 전달.
(사이트 자체에는 이름·연락처를 노출하지 않으므로, URL 만 공유해도 신원이 직접 드러나지 않음.)

## 6. 수정·업데이트 시

로컬에서 파일 수정 후:

```powershell
cd C:\Users\rkadu\ai-ppt\portfolio
git add .
git commit -m "<수정 내용 한 줄 요약>"
git push
```

1~2분 후 GitHub Pages 에 자동 반영.

## 트러블슈팅

- **404 페이지**: GitHub Pages 활성화 후 1~2분 대기 필요. 그래도 안 뜨면 Settings → Pages 에서 배포 상태 확인.
- **outbound 대시보드 차트가 안 뜸**: `data/dashboard.json` 경로가 깨졌을 가능성. `dashboards/outbound/data/dashboard.json` 파일 존재 확인.
- **CSS·폰트가 깨짐**: 인터넷 연결 확인 (Pretendard 폰트가 CDN 에서 로드됨).
- **저장소 이름을 다르게 했을 때**: 위 URL 의 `portfolio` 부분을 실제 저장소 이름으로 교체.

## GitHub 사용자명 자체에 본명이 들어가는 경우

`rkadudtls.github.io/portfolio` 같은 URL은 GitHub 사용자명이 드러납니다. 사용자명에 본명/식별 정보가 포함되어 있다면:
- 새 GitHub 계정을 별칭(예: `scm-portfolio-2026`)으로 만들어 배포
- 또는 본명이 안 드러나는 도메인(예: `scm-kpi.netlify.app`)을 쓰는 Netlify·Vercel 배포로 전환

권장: 사용자명에 부담이 있으면 새 별칭 계정 생성. 절차는 GitHub 가입과 동일하고 5분이면 됨.
