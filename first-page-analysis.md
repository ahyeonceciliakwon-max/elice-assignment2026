# UI Audit 분석
## 1. UI 요소 목록 정리

| 구분 | UI 요소 | 실제 표기 | 비고 |
|---|---|---|---|
| Screen | 전체 화면 | `1번 화면 - 학습 과목 목록` | 전체 페이지 컨테이너 |
| Header | 상단 헤더 | `Header` | sticky 헤더 |
| Header | 햄버거 아이콘 버튼 | `Icon Button` | 아이콘: `bars` |
| Brand | 로고 | `Elice Logo` | 엘리스 로고 |
| Selector | 조직 선택 버튼 | `Org` | `LXP`, `Enterprise`, chevron-down 포함 |
| Input | 검색 필드 | `TextField` | 내부 텍스트 `검색` |
| Action | 알림 아이콘 버튼 | `Icon Button` | 아이콘: `bell` |
| Action | 메시지 아이콘 버튼 | `Children` 내부 버튼 | 아이콘: `message-lines` |
| Avatar | 프로필 원형 영역 | 원형 도형 | 32x32 회색 원 |
| Navigation | 네비게이션 레일 | `Navigation Rail` | 아이콘 + 라벨 구조 |
| Navigation Item | 기관 홈 | `ListItem` | 아이콘: `home` |
| Navigation Item | 탐색 | `ListItem` | 아이콘: `compass` |
| Navigation Item | 내 클래스 | `ListItem` | 아이콘: `book-open-cover` |
| Navigation Item | 대시보드 | `ListItem` | 아이콘: `table-columns` |
| Navigation Item | 더 보기 | `ListItem` | 아이콘: `ellipsis` |
| Navigation | 사이드 네비게이션 | `Side Navigation` | 클래스 단위 메뉴 |
| Info | 클래스 정보 영역 | `Info` | 텍스트: `파이썬 입문 클래스` |
| Side Nav Item | 클래스 홈 | `ListItem` | 아이콘: `chalkboard-user` |
| Side Nav Item | 학습 과목 | `ListItem` | 아이콘: `list` |
| Side Nav Item | 수업 일정 | `ListItem` | 아이콘: `calendar` |
| Side Nav Item | 게시판 | `ListItem` | 아이콘: `chalkboard` |
| Section Header | 페이지 제목 | `학습 과목 목록 헤더` | 텍스트: `학습 과목 목록` |
| Card | 과목 카드 | `과목 카드` | 과목 썸네일 + 텍스트 + 액션 |
| Media | 썸네일 영역 | `Image` | 160x90 placeholder |
| Text | 과목명 텍스트 | `Text` | `도레미 파이썬 1/2`, `파이썬 기초 문제집` |
| Text | 메타 정보 텍스트 | `Text` | `파이썬 • 입문 • 8-16시간` |
| Progress | 진도 바 | `Linear Progress/Determinate` | `25%` 표시 포함 |
| Progress Segment | 진도 세그먼트 | `01`, `02`, `03`, `04` | `01`만 채워짐 |
| Button | 이어서 학습하기 버튼 | `Button/Contained` | 텍스트: `이어서 학습하기` |
| Action | 더보기 아이콘 버튼 | `Icon Button` | 아이콘: `ellipsis-vertical` |
| Divider | 구분선 | `Divider` | 카드 간 separator |
| Layout | 메인 영역 | `Main` | Navigation Rail + Side Navigation + 본문 |
| Layout | 카드 목록 | `List` | 카드 리스트 구조 |
| Layout | 박스 컨테이너 | `Box` | 제목 + 리스트 래핑 |

---

## 2. 컴포넌트 단위 목록

| 영역 | 컴포넌트 | 실제 data-name | 구성 요소 |
|---|---|---|---|
| Header | Header | `Header` | Left + Right |
| Header | Header / Left | `Left` | 햄버거 버튼 + 로고 + 조직 선택 |
| Header | Header / 조직 선택 | `Org` | 텍스트 + Chip/Filled + chevron-down |
| Header | Header / Search | `TextField` | search icon + 입력 텍스트 |
| Header | Header / Actions | `Children` | 알림 버튼 + 메시지 버튼 |
| Header | Header / Avatar | 원형 도형 | 프로필 placeholder |
| Main | 페이지 루트 | `1번 화면 - 학습 과목 목록` | Header + Main |
| Main | Main Layout | `Main` | Navigation Rail + Side Navigation + Container |
| Navigation | Navigation Rail | `Navigation Rail` | 기관 홈 / 탐색 / 내 클래스 / 대시보드 / 더 보기 |
| Navigation | Rail Item | `ListItem` | Icon + Label |
| Navigation | Side Navigation | `Side Navigation` | Info + List |
| Navigation | Side Navigation / Info | `Info` | 클래스명 텍스트 |
| Navigation | Side Navigation / List | `List` | 클래스 홈 / 학습 과목 / 수업 일정 / 게시판 |
| Content | Content Wrapper | `Box` | 페이지 헤더 + 카드 목록 |
| Content | 페이지 헤더 | `학습 과목 목록 헤더` | 타이틀 텍스트 |
| Content | 과목 카드 | `과목 카드` | Image + Content + (Button) + Icon Button |
| Content | 과목 카드 / Image | `Image` | 썸네일 |
| Content | 과목 카드 / Text | `Text` | 과목명 + 메타 정보 |
| Content | 과목 카드 / Progress | `Linear Progress/Determinate` | ProgressContainer + Typography |
| Content | 과목 카드 / ProgressContainer | `ProgressContainer` | 단계 요소 (`01`, `02`, `03`, `04`) |
| Content | 과목 카드 / CTA | `Button/Contained` | 버튼 |
| Content | 과목 카드 / More | `Icon Button` | 더보기 버튼 |
| Content | Divider | `Divider` | 구분선 |

---

## 3. 컴포넌트 구조 시각화

```mermaid
graph TD
    A["1번 화면 - 학습 과목 목록"]

    %% Layout
    A --> B["Header"]
    A --> C["Main"]

    %% Header
    B --> B1["Left"]
    B --> B2["Right"]

    B1 --> B11["Icon Button (bars)"]
    B1 --> B12["Elice Logo"]
    B1 --> B13["Org"]
    B13 --> B131["LXP"]
    B13 --> B132["Enterprise"]
    B13 --> B133["chevron-down"]

    B2 --> B21["Search Field"]
    B2 --> B22["Actions"]
    B2 --> B23["Avatar"]

    B21 --> B211["search icon"]
    B21 --> B212["검색"]
    B22 --> B221["bell"]
    B22 --> B222["message"]

    %% Main
    C --> C1["Navigation Rail"]
    C --> C2["Side Navigation"]
    C --> C3["Content"]

    %% Navigation Rail
    C1 --> C11["기관 홈"]
    C1 --> C12["탐색"]
    C1 --> C13["내 클래스"]
    C1 --> C14["대시보드"]
    C1 --> C15["더 보기"]

    %% Side Navigation
    C2 --> C21["클래스 정보"]
    C2 --> C22["Menu"]

    C22 --> C221["클래스 홈"]
    C22 --> C222["학습 과목"]
    C22 --> C223["수업 일정"]
    C22 --> C224["게시판"]

    %% Content
    C3 --> C31["학습 과목 목록"]
    C3 --> C32["과목 리스트"]

    %% Course Cards
    C32 --> D1["과목 카드"]
    C32 --> D2["Divider"]
    C32 --> D3["과목 카드"]
    C32 --> D4["Divider"]
    C32 --> D5["과목 카드"]

    %% Card 1
    D1 --> D11["Thumbnail"]
    D1 --> D12["정보 영역"]
    D1 --> D13["CTA Button"]
    D1 --> D14["More Button"]

    D12 --> D121["과목명"]
    D12 --> D122["메타 정보"]
    D12 --> D123["Progress"]

    D123 --> D1231["단계 (01~04)"]
    D123 --> D1232["진도율 (25%)"]

    %% Card 2,3
    D3 --> D31["Thumbnail"]
    D3 --> D32["정보 영역"]
    D3 --> D33["More Button"]

    D5 --> D51["Thumbnail"]
    D5 --> D52["정보 영역"]
    D5 --> D53["More Button"]

    %% 🎨 Color Definition
    classDef header fill:#E3F2FD,stroke:#64B5F6,color:#000;
    classDef main fill:#F3E5F5,stroke:#BA68C8,color:#000;
    classDef navigation fill:#E8F5E9,stroke:#81C784,color:#000;
    classDef content fill:#FFF3E0,stroke:#FFB74D,color:#000;

    %% Apply Colors
    class B,B1,B2,B11,B12,B13,B131,B132,B133,B21,B22,B23,B211,B212,B221,B222 header;
    class C main;
    class C1,C2,C11,C12,C13,C14,C15,C21,C22,C221,C222,C223,C224 navigation;
    class C3,C31,C32,D1,D2,D3,D4,D5,D11,D12,D13,D14,D121,D122,D123,D1231,D1232,D31,D32,D33,D51,D52,D53 content;
