# 📚 수학 오답노트 — APK 빌드 방법

Android Studio 설치 없이, GitHub이 대신 APK를 만들어줍니다.

## 1단계. GitHub 저장소 만들기
1. https://github.com 접속 후 로그인 (계정 없으면 무료 가입)
2. 오른쪽 위 **+** → **New repository**
3. 이름 입력 (예: `math-error-note`), Public 또는 Private 아무거나 선택 → **Create repository**

## 2단계. 이 폴더 통째로 업로드
1. 방금 만든 저장소 페이지에서 **uploading an existing file** 링크 클릭
2. 압축 푼 이 폴더 안의 파일/폴더를 **전부** 끌어다 놓기
   (`.github` 폴더가 안 보일 수 있는데, 숨김 폴더라 그렇습니다 — 웹 업로드 대신 아래 "git으로 올리기"를 쓰면 확실합니다)
3. **Commit changes** 클릭

> **더 확실한 방법 (git 사용 가능하면 추천):**
> ```
> cd 이-폴더-경로
> git init
> git add .
> git commit -m "first commit"
> git branch -M main
> git remote add origin https://github.com/내계정/math-error-note.git
> git push -u origin main
> ```

## 3단계. 자동 빌드 확인
1. 저장소 페이지 상단 **Actions** 탭 클릭
2. "Build Android APK" 실행이 자동으로 시작됨 (3~5분 소요)
3. 초록색 체크(✅)가 뜨면 완료

## 4단계. APK 다운로드
1. 완료된 빌드 클릭 → 맨 아래 **Artifacts** 섹션
2. **math-error-note-apk** 클릭 → zip 파일 다운로드
3. 압축 풀면 `app-debug.apk` 파일이 나옵니다

## 5단계. 폰에 설치
1. `app-debug.apk`를 안드로이드 폰으로 전송 (카카오톡 나에게 보내기, 이메일, USB 등)
2. 폰에서 파일 탭 → "출처를 알 수 없는 앱 설치 허용" 묻는 창이 뜨면 허용
3. 설치 완료!

---

### 참고
- 이 방식으로 만든 APK는 **디버그(debug) 버전**이라 개인 설치용으로는 충분하지만, Google Play 스토어에 올리려면 별도로 "서명(release)" 과정이 필요해요. 필요하면 말씀해주세요.
- 앱 내용을 수정하고 싶으면 `www/index.html` 파일만 고쳐서 다시 GitHub에 올리면, 자동으로 다시 빌드됩니다.
- 이미지/사진 첨부 기능은 안드로이드 기본 웹뷰에서도 잘 작동하지만, AI 분석 기능(Anthropic API 키 필요)은 인터넷 연결이 있어야 동작합니다.
