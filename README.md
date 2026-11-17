# 지미니스 토스 미니앱 포트폴리오

지미니스가 만든 토스 미니앱을 소개하는 GitHub Pages 페이지예요.

- 페이지: https://seungjinhan.github.io/portfolio_app/
- 디자인: [TypeUI Doodle](https://www.typeui.sh/design-skills/doodle) 손그림 스타일을 참고했어요.

## 파일

| 파일 | 내용 |
|---|---|
| `index.html` | 페이지 전체. 앱 카드도 여기 있어요 |
| `style.css` | 스타일 |
| `assets/icons/` | 앱 아이콘 (240×240, 각 앱 폴더의 콘솔 로고에서 줄였어요) |

## 앱을 추가할 때

1. 앱 아이콘을 `assets/icons/{appName}.png`로 넣어요. (`sips -Z 240 파일.png`)
2. `index.html`의 `.cards`에 카드 하나를 복사해 이름, 카테고리, 설명, 링크를 바꿔요.
   링크는 `https://tossminiapp.com/d/{appName}`이에요. 앱이 출시돼야 열려요.
3. 첫 화면의 `.board-grid`에 타일을 하나 더하고, 숫자(`출시한 앱 · 9`, 통계)를 고쳐요.

출시 전 앱은 `#soon`(준비 중인 앱) 섹션에 `card soon` 카드로 넣고, 버튼 대신 `준비 중` 도장을 달아요.
출시되면 카드를 `#apps`로 옮기고 `soon` 클래스와 도장을 버튼으로 바꿔요.
지금 준비 중인 앱: 캠핑카라이프(`camping-car-life`), 생활 리듬(`life-rhythm`).

## 로컬에서 보기

```bash
python3 -m http.server 5199
```
