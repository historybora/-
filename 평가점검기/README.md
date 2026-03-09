# 평가계획 점검기 - 배포 가이드

## 폴더 구조
```
평가점검기/
├── netlify.toml                  ← Netlify 설정
├── netlify/
│   └── functions/
│       └── gemini.js             ← API 키가 숨겨진 서버 함수
└── public/
    └── index.html                ← 사이트 본체
```

## Netlify 배포 순서

### 1단계 - GitHub에 업로드
1. github.com 에서 새 저장소(repository) 생성
2. 이 폴더 전체를 업로드

### 2단계 - Netlify 연결
1. netlify.com 로그인 → "Add new site" → "Import from Git"
2. GitHub 저장소 선택 → Deploy

### 3단계 - ★ API 키 환경변수 설정 (가장 중요)
1. Netlify 대시보드 → Site settings → Environment variables
2. "Add variable" 클릭
3. Key: `GEMINI_API_KEY`
4. Value: `AIzaSyCUGMol2cDGR2DONjnvUJo_X2nxxlp3iog`
5. Save → **Deploys 탭에서 "Trigger deploy" 클릭**

### 완료!
- API 키는 Netlify 서버에만 존재 → 브라우저 소스코드에서 절대 안 보임
- 사이트 URL을 선생님들께 공유하면 바로 사용 가능

## Vercel로 배포할 경우
1. vercel.com → "New Project" → GitHub 저장소 선택
2. Settings → Environment Variables → `GEMINI_API_KEY` 추가
3. netlify/functions/gemini.js 파일명을 api/gemini.js 로 변경
4. netlify.toml 불필요 (삭제해도 됨)
