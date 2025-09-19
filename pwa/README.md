# 천억부자 타이머 — PWA 패키지

## 폴더 구조 (업로드/배포용)
```
pwa/
├─ public/
│  ├─ index.html        # 업로드 시 루트로 배치
│  ├─ offline.html
│  └─ icons/
│     ├─ icon-192.png
│     └─ icon-512.png
├─ manifest.webmanifest
├─ sw.js
└─ src/
   └─ app.js            # (선택) 스크립트 외부화 시 사용
```

## Google Drive 정리 가이드
- `Apps/천억부자타이머/` 폴더를 만들고 아래처럼 두세요.
```
Apps/천억부자타이머/
├─ public/    # 배포 산출물(정적 파일)
├─ src/       # 원본 코드
└─ Design/    # 아이콘/브랜딩 소스
```
- 팀과 공유하려면 상위 폴더 권한을 "링크가 있는 모든 사용자 보기"로 설정하고,
  개발자는 `src/`만 편집 권한을 주세요.

## 배포 방법
### Vercel (추천)
1. 이 폴더를 GitHub 저장소로 push
2. vercel.com → New Project → Import → Framework: Other → Root: `pwa/`
3. Build Command/Output 비움 (정적 사이트). 배포 후 `https` 주소에서 설치 가능

### GitHub Pages
1. `pwa/public` 폴더 내용을 저장소 루트로 올림
2. Settings → Pages → Branch: `main` / Folder: `/ (root)`
3. 페이지가 열리면 브라우저 메뉴에서 "앱 설치" 또는 주소창의 설치 아이콘으로 PWA 설치

## 주의
- PWA 설치/오프라인은 **HTTPS**여야 합니다 (GitHub Pages/Vercel OK).
- 서비스워커 `sw.js`는 사이트 **루트(/)**에 있어야 전체 스코프 제어가 가능합니다.
