# 연동 설정 가이드 — Obsidian × GitHub × Claude × ChatGPT

> 최종 갱신: 2026-09-09
> 이 문서는 이 볼트(`COREHEDGE-FUND`)를 여러 기기에서 동일하게 쓰기 위한 설정 절차다.

---

## 0. 전체 구조

```
        [Claude]  ──파일 쓰기──┐
                              ↓
[Obsidian 편집] ──→ 로컬 폴더(= git 리포) ──obsidian-git──→ GitHub
                              ↑                              │
        [ChatGPT] ──읽기 전용────────────────────────────────┘
```

핵심: **로컬 폴더 하나가 Obsidian 볼트이자 git 저장소**다. 모든 도구가 이 폴더를 매개로 만난다.

| 도구 | 역할 | 방향 |
|---|---|---|
| Obsidian | 편집기 + 동기화 엔진(obsidian-git 플러그인) | 읽기·쓰기 |
| GitHub | 기기 간 동기화 허브, 버전 이력 | 저장소 |
| Claude (데스크톱) | 폴더 연결로 파일 직접 작성·수정 | 읽기·쓰기 |
| ChatGPT | GitHub 앱 연결 | **읽기 전용** |

**리포:** `https://github.com/COREMAN-SH/COREHEDGE-FUND`

---

## 1. Windows (현재 구성 — 이미 완료됨)

### 경로
```
C:\Users\Master\Documents\GitHub\CoreHedgeFund
```

### obsidian-git 플러그인 설정값
| 항목 | 값 | 의미 |
|---|---|---|
| Auto commit-and-sync interval | 5 | 5분마다 자동 커밋 |
| Auto push interval | 5 | 5분마다 자동 push |
| Auto pull interval | 5 | 5분마다 자동 pull |
| Pull on startup | ON | 실행 시 pull |
| Pull before push | ON | push 전 pull (충돌 예방) |
| Commit message | `vault backup: {{date}}` | |

### Claude 데스크톱 연결
1. Claude 데스크톱 앱 → **Add folder**
2. 위 경로 선택
3. 이후 Claude가 이 폴더의 파일을 직접 읽고 쓸 수 있음

---

## 2. macOS 설정 (신규 기기)

### 2-1. git 준비
```bash
git --version          # 없으면 Xcode Command Line Tools 설치 안내가 뜸
xcode-select --install # (필요 시)

git config --global user.name  "본인이름"
git config --global user.email "master@corerounder.com"
git config --global credential.helper osxkeychain   # 인증정보 키체인 저장
```

### 2-2. 리포 클론
```bash
mkdir -p ~/Documents/GitHub
cd ~/Documents/GitHub
git clone https://github.com/COREMAN-SH/COREHEDGE-FUND.git CoreHedgeFund
```
> 폴더명을 `CoreHedgeFund`로 맞추면 Windows와 경로 구조가 같아져 헷갈리지 않는다.

**인증:** private 리포이므로 clone 시 아이디/비밀번호를 묻는다. 비밀번호 자리에 **GitHub Personal Access Token(PAT)** 을 넣는다.
- GitHub → Settings → Developer settings → Personal access tokens → **Fine-grained tokens**
- Repository access: `COREHEDGE-FUND` 만 선택
- Permissions: **Contents = Read and write**
- 생성된 토큰을 비밀번호 자리에 붙여넣기 → 키체인에 저장됨

### 2-3. Obsidian 설정
1. [obsidian.md](https://obsidian.md) 에서 macOS 버전 설치
2. 실행 → **Open folder as vault** → `~/Documents/GitHub/CoreHedgeFund` 선택
3. `.obsidian/` 폴더가 리포에 포함돼 있으므로 **플러그인·설정이 이미 따라온다**
4. Settings → Community plugins → **Restricted mode 해제** → `Git` 플러그인 **Enable**
5. Settings → Git 에서 위 1번 표의 값이 그대로 들어와 있는지 확인

### 2-4. Claude 데스크톱 연결
1. Claude 데스크톱 앱 설치 → 로그인
2. **Add folder** → `~/Documents/GitHub/CoreHedgeFund` 선택
3. 세션에서 폴더 접근 승인

### 2-5. 첫 동기화 확인
```bash
cd ~/Documents/GitHub/CoreHedgeFund
git pull
ls coins/major   # BTC-bitcoin.md, ETH-ethereum.md 가 보이면 정상
```

---

## 3. ChatGPT 연결 (읽기 전용)

ChatGPT는 **로컬 폴더에 접근하지 못한다.** GitHub 리포를 통해서만 이 볼트를 읽을 수 있다.

### 설정
1. ChatGPT → Settings → **Apps / Connectors**
2. **GitHub** 선택 → GitHub로 이동해 ChatGPT 앱 설치·승인
3. 접근 허용 리포지토리에서 `COREHEDGE-FUND` 선택

### 제약
- **읽기 전용이다.** 리포에 파일을 쓰거나 커밋할 수 없다. 쓰기가 필요하면 Codex를 써야 한다
- 인덱스를 만들어두는 게 아니라 요청 시점에 리포 내용을 조회하는 방식
- 사용 가능한 모드(일반 대화 / deep research / agent)가 **요금제마다 다르다** — 일반 대화에서는 안 보이고 deep research에서만 되는 경우가 있다

### 실무 결론
- **쓰기는 Claude**, **읽기·교차검증은 ChatGPT** 로 역할을 나누는 게 현실적
- ChatGPT에서 노트를 고쳐야 하면 → 결과를 복사해 Obsidian에 붙여넣거나 Claude에 전달

---

## 4. 모바일 (iOS — iPhone / iPad)

### 4-1. 읽기만 하면 되는 경우
GitHub 앱 또는 모바일 브라우저에서 리포를 열면 마크다운이 그대로 렌더링된다. **설정 불필요.**

### 4-2. Obsidian 앱에서 보고 편집하려는 경우

iOS에서는 obsidian-git 플러그인이 불안정하다. **Working Copy(iOS git 클라이언트) + Obsidian** 조합이 사실상 표준이다.

> ⚠️ Working Copy는 **Pro 일회성 결제**가 필요하다(push 기능). Apple ID가 같으면 다른 기기에서 구입한 것을 복원할 수 있다.

**절차**

1. **Obsidian iOS 설치** → 볼트를 `On My iPhone`(또는 `On My iPad`) 저장소에 새로 만든다. 이름: `CoreHedgeFund`
   - iCloud가 아니라 **로컬 저장소**여야 한다. Working Copy가 접근할 수 있어야 하기 때문
2. **Working Copy 설치** (App Store) → Pro 구매/복원
3. Working Copy → **Repositories → + → Clone repository**
   - URL: `https://github.com/COREMAN-SH/COREHEDGE-FUND.git`
   - 인증: GitHub 로그인 또는 **PAT**(2-2에서 만든 토큰 재사용 가능)
4. clone된 리포를 열고 → **공유 아이콘(↑)** → **`Link Repository to Folder`** (iPhone에서는 `Link Repository to Directory`)
5. 파일 브라우저에서 `On My iPhone` → `Obsidian` → `CoreHedgeFund` 선택 → **Done**
6. 이제 Working Copy 리포와 Obsidian 볼트가 같은 폴더를 가리킨다

**사용 흐름**
- 읽기 전: Working Copy에서 **Pull**
- 편집 후: Working Copy에서 **Commit → Push**
- Obsidian 안에서는 git 조작을 하지 않는다 (플러그인 불필요)

**자동화(선택)**: Apple 단축어(Shortcuts)가 Working Copy 액션을 지원한다. "앱 열 때 pull / 닫을 때 commit-push" 단축어를 만들어두면 수동 조작을 줄일 수 있다.

### 4-3. Android
obsidian-git 플러그인이 비교적 잘 동작한다.
1. Obsidian 앱 → 빈 볼트 생성
2. 설정 → 커뮤니티 플러그인 → **제한 모드 해제** → Browse → **`Git`**(제작자 Vinzent) 설치·활성화
3. 명령 팔레트 → `Git: Clone an existing remote repo` → URL 입력 → **PAT**로 인증

### 4-4. 모바일 git 공통 제약
- **SSH 인증 불가** — PAT(토큰) 방식만 가능
- **rebase 전략 미지원** — 모바일에서는 merge 전략으로 설정할 것. 데스크톱의 `pull --rebase`가 그대로 안 먹힌다
- 리포 크기 제약 — 파일 스캔이 느리다(3,000개 기준 3~4분). 이 볼트는 26개 파일이라 무관
- 큰 변경·충돌 해소는 데스크톱에서 처리할 것

### 4-5. 참고
`.obsidian/plugins/obsidian-git/`이 리포에 포함돼 있으므로, 볼트를 기기에 가져오기만 하면 플러그인 파일은 함께 따라온다. 안드로이드에서 처음 clone할 때만 별도 설치가 필요하다.

## 5. 운영 규칙 (중요)

### 5-1. git 명령은 사람이 직접 실행한다
Claude 세션은 **파일 삭제 권한이 없다.** Claude가 `git` 명령을 실행하면 `.git/index.lock`, `.git/HEAD.lock` 같은 잠금 파일이 남고, **이게 Obsidian Git까지 막는다.**

→ **Claude는 파일 읽기·쓰기만, git 명령(commit/pull/push)은 사람이 터미널에서.**
→ 평소에는 obsidian-git 자동 동기화에 맡기면 되므로 손댈 일이 거의 없다.

### 5-2. Obsidian이 켜져 있어야 자동 동기화가 돈다
obsidian-git은 Obsidian 앱 내부에서 도는 플러그인이다. 앱을 끄면 타이머도 멈춘다.
- Obsidian 실행 중 → 5분마다 자동 커밋·push
- Obsidian 종료 상태 → 파일은 디스크에만 쌓임, 다음 실행 시 한꺼번에 커밋됨 (**유실되지는 않는다**)

### 5-3. 수동 git 작업 시 Obsidian을 먼저 닫는다
플러그인이 백그라운드에서 git을 잡고 있으면 잠금이 충돌한다.

### 5-4. 여러 기기 사용 시
작업 시작 전 `git pull`, 끝나면 push. Obsidian을 켜두면 자동으로 처리된다.

---

## 6. 문제 해결

### "Another git process seems to be running" / `index.lock: File exists`
잠금 파일이 남은 것. Obsidian을 닫고:

**Windows (PowerShell)**
```powershell
cd $HOME\Documents\GitHub\CoreHedgeFund
Get-ChildItem .git -Filter "*.lock" -Recurse | Remove-Item -Force
```

**macOS / Linux**
```bash
cd ~/Documents/GitHub/CoreHedgeFund
find .git -name "*.lock" -delete
```

### `! [rejected] main -> main (non-fast-forward)`
로컬이 원격보다 뒤처진 상태. 순서대로:
```bash
git add -A
git commit -m "local changes before sync"
git pull --rebase
git push
```

### rebase 중 충돌
```bash
# 어느 쪽을 남길지 결정 후
git add <파일>          # 또는 git rm <파일>
git -c core.editor=true rebase --continue
```
`.obsidian/` 안의 파일이 충돌하면 내용을 볼 필요 없다 — 화면 배치 상태 파일이므로 아무 쪽이나 선택.

### 줄바꿈 때문에 파일 전체가 변경된 것처럼 보임
`.gitattributes`가 이미 `eol=lf`로 통일해두었다. 그래도 발생하면:
```bash
git config core.autocrlf input   # macOS/Linux
git config core.autocrlf true    # Windows
```

### Claude가 "폴더에 접근할 수 없다"고 할 때
- 해당 기기의 Claude 데스크톱 앱이 실행 중이고 온라인인지 확인
- 세션마다 폴더 접근 승인이 필요할 수 있음 → 승인 프롬프트 확인

---

## 7. 추적 제외 파일

`.gitignore`로 아래를 제외했다 — 기기마다 달라지는 상태 파일이라 동기화하면 매번 충돌한다.
```
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.obsidian/graph.json
```

---

## 참고 링크
- [Connecting GitHub to ChatGPT — OpenAI Help Center](https://help.openai.com/en/articles/11145903-connecting-github-to-chatgpt)
- [obsidian-git (Vinzent03)](https://github.com/Vinzent03/obsidian-git)
- [Obsidian 다운로드](https://obsidian.md)
