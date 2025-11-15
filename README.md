# Nomad 개인 홈페이지

Aeon + Pageflow 스타일의 철학자 개인 홈페이지

## 특징

- **Aeon 영감**: 깔끔하고 세련된 에세이 중심 디자인
- **Pageflow 영감**: 멀티미디어 스토리텔링 경험
- **반응형 디자인**: 모바일, 태블릿, 데스크톱 모두 지원
- **3권의 책**: 각각 목차 페이지 포함
- **Nomad Nexus 연동**: 플랫폼으로 연결

## 파일 구조

```
nomad-website/
├── index.html          # 메인 페이지
├── book1.html          # 타자상실시대, 서로의 풍경이 되다
├── book2.html          # 미술, 인간의 무늬를 그리다
├── book3.html          # 콤플렉스로 읽는 그리스 신화
├── css/
│   ├── style.css       # 메인 스타일
│   └── book-page.css   # 책 페이지 스타일
├── js/
│   └── script.js       # 인터랙션 스크립트
└── images/             # 이미지 폴더 (직접 추가 필요)
```

## 사용 방법

### 1. GitHub에 업로드

```bash
cd nomad-website
git init
git add .
git commit -m "Initial commit"
git remote add origin YOUR_GITHUB_REPO_URL
git push -u origin main
```

### 2. Netlify 배포

1. Netlify 로그인
2. "Add new site" → "Import an existing project"
3. GitHub 연결
4. 저장소 선택
5. Build settings:
   - Build command: (비워두기)
   - Publish directory: (비워두기 또는 `/`)
6. "Deploy site" 클릭

### 3. 이미지 추가

`images/` 폴더에 다음 이미지들을 추가하세요:

- `book1-cover.jpg` - 타자상실시대 표지
- `book2-cover.jpg` - 미술, 인간의 무늬 표지
- `book3-cover.jpg` - 콤플렉스로 읽는 그리스 신화 표지
- `nomad-profile.jpg` - 프로필 사진
- `lecture1.jpg`, `lecture2.jpg` - 강의 이미지

이미지가 없으면 자동으로 placeholder가 표시됩니다.

## 커스터마이징

### 색상 변경

`css/style.css` 파일의 `:root` 섹션에서 색상 변경:

```css
:root {
    --accent: #e63946;  /* 강조 색상 */
    --dark-bg: #1a1a1a; /* 어두운 배경 */
    /* ... */
}
```

### YouTube 연동

`index.html`의 YouTube 섹션에서 실제 채널 URL로 변경:

```html
<a href="https://youtube.com/@yourchannel" target="_blank">
```

### 이메일 변경

모든 HTML 파일에서 `nomad@example.com`을 실제 이메일로 변경

### Nomad Nexus 링크

현재 `https://nomad-nexus.netlify.app`로 설정되어 있습니다.
실제 플랫폼 URL로 변경하려면 모든 HTML 파일에서 해당 링크를 찾아 수정하세요.

## 브라우저 지원

- Chrome, Firefox, Safari, Edge 최신 버전
- 모바일 브라우저 지원

## 라이센스

© 2025 Nomad. All rights reserved.
