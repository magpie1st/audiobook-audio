# audiobook-audio

MacsALogs 오디오북 페이지(`https://magpie1st.github.io/MacsALogs/audiobook.html`)가 재생하는 **암호화된 음원**만 두는 저장소입니다.
GitHub Pages(`https://magpie1st.github.io/audiobook-audio/`)로 서빙되고, 블로그와 같은 도메인이라 페이지가 받아서 브라우저 안에서 풉니다.

- 파일: `<엔진>/<책 id>/<챕터>-<태그>.bin` = 잠근 mp3(iv 12바이트 + AES-256-GCM 암호문), `<엔진>/<책 id>/manifest.bin` = 잠근 목록(챕터별 파일명·길이·문장 타임라인·본문 해시). 열쇠는 페이지 암호에서 만든다 — 이 저장소만으로는 들을 수 없다
- **손으로 고치지 않는다.** MacsALogs `scripts/publish_audiobook_audio.py --engine <엔진>` 이 만든다 (페이지 `build_audiobook.py` 와는 따로 돈다)
- 블로그 저장소와 Pages 용량(각 1GB)을 나눠 쓰지 않으려고 분리했다 (2026-11-01)
- 엔진: `drama3-ann`(Drama3-Ann, 40k, 31챕터) 하나. Gemini·Kokoro Emma·Kokoro Heart 는 2026-11-10 에 삭제했다
- 크기: 약 190MB (2026-11-10, Pages 1GB 안). Pages 배포가 `syncing_files` 에서 타임아웃 나면 100~200MB 씩 나눠 푸시한다
