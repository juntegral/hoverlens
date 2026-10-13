<p align="center">
  <img src="docs/images/icon.png" width="112" alt="HoverLens 아이콘">
</p>

<h1 align="center">HoverLens</h1>

<p align="center">
  화면의 글 위에 포인터를 두고 단축키를 누르면, 답과 해설이 포인터 옆에 뜹니다.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/macOS-15%2B-000000?logo=apple&logoColor=white" alt="macOS 15+">
  <img src="https://img.shields.io/badge/Homebrew-cask-FBB040?logo=homebrew&logoColor=white" alt="Homebrew cask">
  <a href="https://buymeacoffee.com/juntegral"><img src="https://img.shields.io/badge/Buy%20me%20a%20coffee-FFDD00?logo=buymeacoffee&logoColor=black" alt="Buy me a coffee"></a>
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/images/panel-dark.png">
    <img src="docs/images/panel-light.png" width="620" alt="문제 위에서 단축키를 누르면 답과 해설이 패널에 뜬다">
  </picture>
</p>

HoverLens는 메뉴 막대에 사는 macOS 앱으로, 읽고 공부하는 일을 돕습니다. 막힌 문제의 풀이를 확인하고, 문장을 번역하고, 용어를 설명합니다. 창을 바꾸거나 글을 복사해 붙여 넣을 필요 없이, 보고 있던 자리에서 단축키만 누르면 됩니다.

## 하는 일

- **문제를 통째로 읽습니다.** 문제와 보기가 여러 줄에 흩어져 있어도 포인터 둘레를 함께 읽어, 가리킨 문제 하나를 풉니다. 보기에 번호가 없으면 순서대로 번호를 매겨 답합니다.
- **답과 해설을 함께 보여 줍니다.** 첫 줄에 답을, 그 아래에 보기마다 왜 맞고 틀린지를 한 줄씩 적습니다. 답만 보고 넘어가지 않도록 해설이 늘 따라옵니다.
- **동작을 직접 만듭니다.** 지시문과 단축키, 읽는 범위, 생각하는 정도를 동작마다 정합니다. 번역, 설명, 풀이, 코드가 기본으로 들어 있습니다.
- **코드는 바로 붙여 넣습니다.** 코드 동작은 답을 받는 대로 클립보드에 넣어 둡니다.
- **쓰던 도구로 답합니다.** Claude Code나 Codex에 로그인해 두었다면 그대로 쓰고, Anthropic·OpenAI API 키로도 됩니다.
- **글자가 없는 곳도 읽습니다.** 이미지나 글을 내어 주지 않는 앱에서는 화면의 텍스트를 인식합니다.

## 기본 동작

| 동작 | 하는 일 | 단축키 | 읽는 범위 |
|---|---|---|---|
| 번역 | 가리킨 문장을 답변 언어로 옮깁니다 | ⌃⌥⇧ (누르고 있기) | 문장 |
| 설명 | 뜻과 핵심 용어를 세 문장 안으로 풉니다 | 직접 지정 | 문장 |
| 풀이 | 문제의 답과 보기별 해설을 씁니다 | ⌃⌥⌘ (누르고 있기) | 주변까지 |
| 코드 | 문제를 푸는 코드만 쓰고 클립보드에 넣습니다 | 직접 지정 | 주변까지 |

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/images/actions-dark.png">
    <img src="docs/images/actions-light.png" width="760" alt="동작 설정 화면">
  </picture>
</p>

## 설치

macOS 15 이상에서 [Homebrew](https://brew.sh)로 설치합니다.

```sh
brew install --cask juntegral/tap/hoverlens
```

탭을 한 번 추가해 두면 이름만으로 설치하고 올릴 수 있습니다.

```sh
brew tap juntegral/tap
brew install --cask hoverlens
brew upgrade --cask hoverlens
```

아직 Apple의 공증을 받지 않은 빌드입니다. 설치할 때 격리 표시를 풀어 두므로 바로 열 수 있지만, macOS가 "확인되지 않은 개발자"라고 알리면 시스템 설정 → 개인정보 보호 및 보안에서 "그래도 열기"를 누르세요.

처음 열면 권한 안내가 뜹니다.

| 권한 | 필요 | 쓰는 곳 |
|---|---|---|
| 손쉬운 사용 | 필수 | 포인터 아래의 글과 선택한 글 읽기 |
| 화면 기록 | 선택 | 이미지와, 글을 내어 주지 않는 앱에서 텍스트 인식 |

입력 모니터링 권한은 쓰지 않습니다. 보조 키가 눌렸는지만 보고, 키가 들어간 단축키는 시스템 핫키로 등록합니다.

## 쓰는 법

**누르고 있기.** 보조 키만으로 된 단축키(⌃⌥⌘ 등)는 누르고 있는 동안 패널이 보이고 손을 떼면 닫힙니다. 포인터를 패널 위로 옮긴 뒤 떼면 패널이 남습니다.

**한 번 누르기.** 키가 들어간 단축키(⌃⌥1 등)는 한 번 누르면 패널이 남습니다. Esc나 패널 바깥을 누르면 닫힙니다.

**범위를 직접 정하기.** 글을 드래그로 선택하고 단축키를 누르면 선택한 글만 읽습니다.

패널에서는 Tab으로 다음 동작으로 바꿔 다시 묻고, 남아 있는 패널에서는 ⌘C로 답을 복사합니다. 메뉴 막대 미리보기를 켜 두면 방금 받은 답이 아이콘 옆에 잠깐 보입니다. 풀이의 답은 `2,3`처럼 값만 보입니다.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/images/popover-dark.png">
    <img src="docs/images/popover-light.png" width="360" alt="메뉴 막대 팝오버">
  </picture>
</p>

## 올바르게 쓰기

HoverLens는 공부하고 글을 이해하는 데 쓰라고 만든 도구입니다. 시험이나 평가처럼 외부의 도움이 허용되지 않는 자리에서 쓰지 않는 것, 학교와 기관의 규정을 지키는 것은 쓰는 사람의 책임입니다. 모델의 답은 틀릴 수 있으니 해설을 읽고 스스로 확인하세요.

## 답을 받는 곳

메뉴 막대 아이콘 → HoverLens 열기 → 모델에서 고릅니다.

| 서비스 | 필요한 것 | 고를 수 있는 모델 |
|---|---|---|
| Claude Code | 설치와 로그인 (`claude auth login`) | Haiku 5.5, Sonnet 5.5, Opus 5.5, Fable 5.1 |
| Codex | 설치와 로그인 (`codex login`) | gpt-6.1-sol, gpt-6-luna |
| Anthropic | API 키 | Haiku 5.5, Sonnet 5.5, Opus 5.5, Fable 5.1 |
| OpenAI | API 키 | gpt-6-luna, gpt-6-sol, gpt-6.1-sol, gpt-6-astra |

목록에 없는 모델은 "직접 입력"으로 이름을 적습니다. 얼마나 오래 생각할지는 동작마다 빠르게·보통·깊게 가운데 고릅니다.

## 읽는 것과 보내는 것

- 단축키를 눌렀을 때만 화면의 글을 읽습니다. 평소에는 아무것도 읽지 않습니다.
- 암호 입력란은 읽지 않고, 제외한 앱에서는 동작하지 않습니다.
- 보내는 것은 읽은 글(최대 1,000자), 그 글이 있던 앱의 이름, 동작의 지시문입니다. 주변까지 읽는 동작은 가리킨 창 안에서 포인터 둘레의 글을 최대 3,000자까지 함께 보냅니다. 고른 서비스 한 곳에만 보냅니다.
- Claude Code와 Codex는 도구와 사용자 설정을 끈 채로 실행하고, 그래도 도구를 쓰려 하면 조회를 멈춥니다.
- API 키는 키체인에만 저장합니다. Claude Code와 Codex의 로그인 정보는 읽지 않습니다.
- 조회 기록은 `~/Library/Application Support/HoverLens/`에 저장하며, 끄거나 지울 수 있습니다.
- 패널과 창은 보통의 창입니다. 화면 공유나 녹화에 그대로 보입니다.

## 의견 보내기

써 보고 느낀 점, 잘 안 되는 점, 있었으면 하는 기능을 알려 주세요.

- [사용 후기와 질문](https://github.com/juntegral/hoverlens/discussions)
- [문제 신고와 제안](https://github.com/juntegral/hoverlens/issues/new/choose)

화면의 글이나 답을 붙여 넣을 때는 개인 정보가 들어 있지 않은지 확인해 주세요.

## 후원

HoverLens가 도움이 됐다면 [커피 한 잔](https://buymeacoffee.com/juntegral)으로 응원해 주세요.
