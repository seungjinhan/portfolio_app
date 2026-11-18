# 지미니스 토스 미니앱 포트폴리오

지미니스가 만든 토스 미니앱을 소개하는 GitHub Pages 페이지예요.

- 페이지: https://seungjinhan.github.io/portfolio_app/
- 디자인: [TypeUI Doodle](https://www.typeui.sh/design-skills/doodle) 손그림 스타일을 참고했어요.

## 파일

| 파일 | 내용 |
|---|---|
| `index.html` | 페이지 전체. 앱 카드도 여기 있어요 |
| `style.css` | 스타일 |
| `i18n.js` | 언어 설정과 번역 (한국어 밖 8개 언어) |
| `assets/icons/` | 앱 아이콘 (240×240, 각 앱 폴더의 콘솔 로고에서 줄였어요) |

## 앱을 추가할 때

1. 앱 아이콘을 `assets/icons/{appName}.png`로 넣어요. (`sips -Z 240 파일.png`)
2. `index.html`의 `#apps`에서 앱의 카테고리 묶음(`.cat-group`, 예: `#cat-edu`) 안 `.cards`에 카드 하나를 복사해 이름, 설명, 링크를 바꾸고, 묶음 제목의 숫자(`.cat-count`)를 고쳐요.
   카드 제목은 `h4`예요 (카테고리 제목이 `h3`). 링크는 `https://tossminiapp.com/d/{appName}`이에요. 앱이 출시돼야 열려요.
   한 줄 소개와 기능의 `data-i18n` 키도 `{appName}.t`, `{appName}.f1`~`f3`으로 바꿔요.
3. 새 카테고리면 `.cat-group`을 하나 더 만들고, 위쪽 통계의 카테고리 칩(`.cat-links`)과 숫자도 더해요. 카테고리 이름은 `cat…` 키로 번역해요.
4. 첫 화면의 `.board-grid`에 타일을 하나 더하고, 숫자(`출시한 앱 · 10`, 통계)를 고쳐요. 타일은 한 줄에 5개(휴대폰 4개)씩 놓이고 마지막 줄은 가운데로 모여요.
5. `i18n.js`의 8개 언어마다 새 키의 번역을 넣고, 숫자가 들어간 글(`desc`, `heroLead`, `boardPill`)도 고쳐요.
   번역이 빠진 키는 한국어로 나와요.

지금은 준비 중인 앱이 없어서 `#soon`(준비 중인 앱) 섹션을 뺐어요. 다시 넣을 때는 `#games`와 같은 모양의 `section-sub` 섹션에 `card soon` 카드를 두고, 버튼 대신 `<span class="stamp" data-i18n="soonStamp">준비 중</span>`을 달아요.
섹션 글 번역(`soonTag`, `soonTitle`, `soonLead`, `soonStamp`)과 스타일(`.card.soon`, `.stamp`)은 남겨 뒀어요. 출시되면 카드를 `#apps`의 카테고리 묶음으로 옮기고 도장을 버튼으로 바꿔요.

웹에서 해 볼 수 있는 게임은 `#games`(게임) 섹션에 넣고, `웹에서 해보기` 버튼(번역 키 `playWeb`)으로 웹 게임에 연결해요.

| 게임 | 웹 주소 |
|---|---|
| 미로찾기 (`maze-game`) | https://seungjinhan.github.io/maze-game/ |
| 생활 리듬 (`life-rhythm`) | https://seungjinhan.github.io/life-rhythm/ |

게임이 토스에 출시되면 카드를 `#apps`의 게임 카테고리 묶음(없으면 새로)으로 옮기고 버튼을 `토스에서 보기`로 바꿔요.

## 언어

오른쪽 위 버튼으로 한국어, English, 日本語, Tiếng Việt, ไทย, Español, 繁體中文, 简体中文, Bahasa Indonesia를 골라요.

- 한국어는 `index.html`에 쓰인 글 그대로예요. 다른 언어는 `i18n.js`의 `T`에서 `data-i18n`(내용) / `data-i18n-aria`(aria-label) 키로 바꿔 끼워요.
- 처음 열면 주소의 `?lang=`, 전에 고른 언어, 기기 언어 순으로 정해요. 지원하지 않는 기기 언어는 English로 보여요.
- 언어별 링크: `?lang=en`, `ja`, `vi`, `th`, `es`, `zh-Hant`, `zh-Hans`, `id`
- 앱 이름은 토스에 등록된 한국어 이름 그대로 둬요.
- 한글 손글씨(Gaegu)에 없는 글자는 Yomogi(일본어), LXGW WenKai TC(번체), ZCOOL KuaiLe(간체), Mali(베트남어·태국어)로 써요. 고른 언어 글꼴만 불러와요.
- 번역은 원어민 검수 전이에요.

## 로컬에서 보기

```bash
python3 -m http.server 5199
```
