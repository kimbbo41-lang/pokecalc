# 포켓칼크 (PokéCalc)

**포켓몬 챔피언스 기준 실수치 · 데미지 계산기** — 브라우저에서 바로 동작하는 단일 페이지 웹앱입니다.

데모: `https://<your-username>.github.io/<repo-name>/`

## 주요 기능

- **실수치 계산** — Lv50 · 개체값 31 고정 · 스탯포인트(SP, 0~32 / 총 66) 기반 (포켓몬 챔피언스 규칙)
- **데미지 계산** — 자속(STAB)·타입 상성·급소·더블 광역기·난수(85~100%)
- **포켓몬 도감** — 전국도감 + 메가진화(구세대 48종 + 레전드 Z-A 신규)
- **기술 데이터** — 위력·타입·물리/특수·우선도·연속타(고정/변동)·플래그(접촉/펀치/깨물기/파동/소리/폭탄/베기)
- **특성** — 적응력·천하장사·테크니션·틀깨기·색안경·내열·위협·천연·마중물 등 다수
- **도구** — 생명의구슬·구애세트·돌격조끼·진화의휘석·반감열매·기합의띠 등
- **날씨/필드** — 쾌청·비·모래바람·눈 / 일렉트릭·그래스·미스트·사이코 (비행/부유/풍선은 필드 미적용)
- **랭크 변화** — 공격/방어/스피드 랭크 (-6 ~ +6)
- **화상·남은 HP** — 화상 물리 ×0.5, 방어측 남은 HP 조절(확정/난수 타수 반영)
- **조건부 기술** — 객기·하이드로스팀·프리즈드라이·바디프레스·사이코쇼크 등 자동 보정 + 위력 수동보정
- **선공 판정** — 스피드·우선도·스카프·순풍·마비·트릭룸 반영
- **배틀 시뮬레이션** — 1:1 풀피 턴제 진행, 승자·턴 로그 표시

## 파일 구성

```
index.html      메인 페이지 (모든 UI/로직)
pokedex.js      포켓몬 종족값 데이터 (한글명)
pokedata.js     타입/상성/기술 데이터
.nojekyll       GitHub Pages가 파일을 그대로 서빙하도록 함
```

> 세 파일은 **같은 폴더**에 함께 있어야 합니다. (index.html이 pokedex.js / pokedata.js를 상대경로로 불러옵니다.)

## GitHub Pages 배포 방법

1. GitHub에서 새 저장소 생성 (예: `pokecalc`)
2. 이 폴더의 파일들을 저장소 루트에 올리기:
   ```bash
   git init
   git add .
   git commit -m "포켓칼크 배포"
   git branch -M main
   git remote add origin https://github.com/<username>/<repo>.git
   git push -u origin main
   ```
3. 저장소 **Settings → Pages → Build and deployment**에서
   - Source: **Deploy from a branch**
   - Branch: **main** / **/(root)** 선택 후 Save
4. 1~2분 뒤 `https://<username>.github.io/<repo>/` 에서 접속

## 데이터 출처 / 크레딧

- 종족값·타입·기술: [PokéAPI](https://pokeapi.co/)
- 한글 기술명: [PokeRogue 로케일](https://github.com/pagefaultgames/pokerogue-locales)
- 기술 플래그·연속타: [Pokémon Showdown](https://pokemonshowdown.com/)
- Z-A 메가 종족값: Serebii / Game8 / Exion Vault 교차 검증

## 면책

Pokémon 및 관련 명칭은 © Nintendo / Creatures Inc. / GAME FREAK Inc. 의 상표입니다.
본 프로젝트는 비영리 팬메이드 도구이며 공식과 무관합니다. 일부 신작(Z-A/DLC) 수치는 커뮤니티 자료 기반으로 실제와 다를 수 있습니다.

## 라이선스

코드: MIT License (LICENSE 참고). 데이터는 각 출처의 라이선스를 따릅니다.
