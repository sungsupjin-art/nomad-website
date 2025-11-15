# Nomad 홈페이지 배포 가이드

## 빠른 시작 (5분 안에 배포하기)

### 1단계: GitHub에 업로드

1. GitHub에서 새 저장소 생성
   - 저장소 이름: `nomad-website` (또는 원하는 이름)
   - Public 선택

2. 로컬에서 업로드:
   ```bash
   cd nomad-website
   git init
   git add .
   git commit -m "Initial commit: Nomad personal website"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/nomad-website.git
   git push -u origin main
   ```

### 2단계: Netlify 배포

1. https://netlify.com 접속 및 로그인
2. "Add new site" 클릭
3. "Import an existing project" 선택
4. "Deploy with GitHub" 클릭
5. 방금 만든 `nomad-website` 저장소 선택
6. 설정 확인:
   - Branch: `main`
   - Build command: (비워두기)
   - Publish directory: (비워두기)
7. "Deploy site" 클릭

**완료!** 몇 초 후 사이트가 배포됩니다.

## 다음 단계

### 이미지 추가하기

현재는 placeholder 이미지가 표시됩니다. 실제 이미지를 추가하려면:

1. `images/` 폴더에 다음 파일들을 추가:
   - `book1-cover.jpg` (400x600px 권장)
   - `book2-cover.jpg` (400x600px 권장)
   - `book3-cover.jpg` (400x600px 권장)
   - `nomad-profile.jpg` (500x600px 권장)
   - `lecture1.jpg` (600x400px 권장)
   - `lecture2.jpg` (600x400px 권장)

2. Git으로 업로드:
   ```bash
   git add images/
   git commit -m "Add images"
   git push
   ```

Netlify가 자동으로 재배포합니다!

### YouTube 채널 연동

1. `index.html` 파일에서 YouTube 섹션 찾기 (약 230번째 줄)

2. 실제 채널 URL로 변경:
   ```html
   <a href="https://youtube.com/@your-actual-channel" target="_blank">
   ```

3. YouTube 비디오 임베드 (선택사항):
   ```html
   <iframe width="100%" height="500" 
     src="https://www.youtube.com/embed/VIDEO_ID" 
     frameborder="0" allowfullscreen>
   </iframe>
   ```

### 이메일 주소 변경

모든 HTML 파일에서 `nomad@example.com`을 실제 이메일로 변경:

```bash
# 일괄 변경 (Mac/Linux)
sed -i '' 's/nomad@example.com/your-real-email@example.com/g' *.html

# 일괄 변경 (Windows Git Bash)
sed -i 's/nomad@example.com/your-real-email@example.com/g' *.html
```

### 커스텀 도메인 연결

1. Netlify 사이트 설정 → "Domain management"
2. "Add custom domain" 클릭
3. 도메인 입력 (예: nomad.com)
4. DNS 설정 지시사항 따르기

## 콘텐츠 업데이트 방법

### 에세이 추가하기

1. `index.html`의 Essays 섹션에 새로운 카드 추가:
   ```html
   <article class="essay-card">
       <div class="essay-media">
           <div class="video-placeholder">
               <span class="play-icon">▶</span>
           </div>
       </div>
       <div class="essay-content">
           <span class="essay-category">카테고리</span>
           <h3 class="essay-title">에세이 제목</h3>
           <p class="essay-excerpt">간단한 설명...</p>
           <div class="essay-meta">
               <span class="read-time">읽기 X분</span>
               <span class="watch-time">영상 X분</span>
           </div>
       </div>
   </article>
   ```

2. Git으로 업데이트:
   ```bash
   git add index.html
   git commit -m "Add new essay"
   git push
   ```

### 책 정보 수정하기

각 책 페이지(`book1.html`, `book2.html`, `book3.html`)를 직접 수정하면 됩니다.

## 색상 테마 변경

`css/style.css` 파일의 맨 위 `:root` 섹션에서 색상 변경:

```css
:root {
    --accent: #e63946;        /* 강조 색상 (빨강) */
    --dark-bg: #1a1a1a;       /* 어두운 배경 */
    --text-primary: #1a1a1a;  /* 기본 텍스트 */
    --text-secondary: #666666; /* 보조 텍스트 */
}
```

예시: 파란색 테마로 변경
```css
:root {
    --accent: #3b82f6;  /* 파란색으로 변경 */
}
```

## 문제 해결

### 사이트가 업데이트되지 않아요
- Netlify 대시보드에서 "Trigger deploy" → "Clear cache and deploy"

### 이미지가 안 보여요
- 이미지 파일 이름과 경로가 정확한지 확인
- 이미지 형식이 .jpg 또는 .png인지 확인

### 모바일에서 레이아웃이 이상해요
- 브라우저 캐시 삭제 후 다시 확인
- 반응형 디자인이 적용되어 있어 자동으로 조정됩니다

## 지원

문제가 있거나 질문이 있으시면:
1. GitHub Issues에 문의
2. Netlify 문서: https://docs.netlify.com
3. HTML/CSS 수정이 필요하면 Claude에게 문의

---

**축하합니다! 🎉**
멋진 철학자 홈페이지가 완성되었습니다!
