# audiobook-audio

MacsALogs 오디오북 페이지(`https://magpie1st.github.io/MacsALogs/audiobook.html`)가 재생하는 **암호화된 음원**만 두는 저장소입니다.
GitHub Pages(`https://magpie1st.github.io/audiobook-audio/`)로 서빙되고, 블로그와 같은 도메인이라 페이지가 받아서 브라우저 안에서 풉니다.

- 파일: `<책 id>/<엔진>-<챕터>-<태그>.bin` = iv(12바이트) + AES-256-GCM 암호문. 열쇠는 페이지 암호에서 만든다 — 이 저장소만으로는 들을 수 없다
- **손으로 고치지 않는다.** MacsALogs `scripts/build_audiobook.py` 가 복사하고, tts-maker `gemini/audiobook_auto.sh`(6시간마다)가 커밋·푸시한다
- 블로그 저장소와 Pages 용량(각 1GB)을 나눠 쓰지 않으려고 분리했다 (2026-11-01)
- 엔진: `gemini`(Sulafat, 40k) · `kokoro-bf_emma`(Emma, 24k) · `kokoro-af_heart`(Heart, 24k). 엔진·챕터마다 파일 하나 — 새로 만들면 예전 것은 지워진다
- 크기: 222MB (2026-11-02, Gemini 는 일부만). 전부 차면 약 420MB 예상 — Pages 1GB 안
