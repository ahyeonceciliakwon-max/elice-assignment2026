# UI Audit 분석
---

## 1. UI 요소 목록 정리

| 구분 | UI 요소 | 실제 표기 / data-name | 비고 |
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

## 3. 컴포넌트 그룹핑 시각화 (Mermaid)
graph TD
    A["1번 화면 - 학습 과목 목록"]

    A --> B["Header"]
    A --> C["Main"]

    subgraph HEADER["Header"]
        B
        B1["Left"]
        B2["Right"]
        B11["Icon Button (bars)"]
        B12["Elice Logo"]
        B13["Org"]
        B131["LXP"]
        B132["Chip/Filled: Enterprise"]
        B133["chevron-down"]
        B21["TextField"]
        B22["Actions"]
        B23["Avatar"]
        B211["search icon"]
        B212["검색"]
        B221["bell"]
        B222["message-lines"]
    end

    subgraph MAIN["Main"]
        C
        C1["Navigation Rail"]
        C2["Side Navigation"]
        C3["Main Content"]
    end

    subgraph NAVIGATION["Navigation"]
        C11["기관 홈"]
        C12["탐색"]
        C13["내 클래스"]
        C14["대시보드"]
        C15["더 보기"]
        C21["Info: 파이썬 입문 클래스"]
        C22["List"]
        C221["클래스 홈"]
        C222["학습 과목"]
        C223["수업 일정"]
        C224["게시판"]
    end

    subgraph CONTENT["Content"]
        C31["학습 과목 목록 헤더"]
        C32["List"]
        D1["과목 카드 1"]
        D2["Divider"]
        D3["과목 카드 2"]
        D4["Divider"]
        D5["과목 카드 3"]
        D11["Image"]
        D12["Content"]
        D13["Button/Contained"]
        D14["Icon Button"]
        D121["도레미 파이썬 1"]
        D122["파이썬 • 입문 • 8-16시간"]
        D123["Linear Progress/Determinate"]
        D1231["ProgressContainer"]
        D1232["25%"]
        D12311["01"]
        D12312["02"]
        D12313["03"]
        D12314["04"]
        D31["Image"]
        D32["Content"]
        D33["Icon Button"]
        D321["도레미 파이썬 2"]
        D322["파이썬 • 입문 • 8-16시간"]
        D51["Image"]
        D52["Content"]
        D53["Icon Button"]
        D521["파이썬 기초 문제집"]
        D522["파이썬 • 입문 • 8-16시간"]
    end

    B --> B1
    B --> B2

    B1 --> B11
    B1 --> B12
    B1 --> B13
    B13 --> B131
    B13 --> B132
    B13 --> B133

    B2 --> B21
    B2 --> B22
    B2 --> B23
    B21 --> B211
    B21 --> B212
    B22 --> B221
    B22 --> B222

    C --> C1
    C --> C2
    C --> C3

    C1 --> C11
    C1 --> C12
    C1 --> C13
    C1 --> C14
    C1 --> C15

    C2 --> C21
    C2 --> C22
    C22 --> C221
    C22 --> C222
    C22 --> C223
    C22 --> C224

    C3 --> C31
    C3 --> C32

    C32 --> D1
    C32 --> D2
    C32 --> D3
    C32 --> D4
    C32 --> D5

    D1 --> D11
    D1 --> D12
    D1 --> D13
    D1 --> D14

    D12 --> D121
    D12 --> D122
    D12 --> D123
    D123 --> D1231
    D123 --> D1232
    D1231 --> D12311
    D1231 --> D12312
    D1231 --> D12313
    D1231 --> D12314

    D3 --> D31
    D3 --> D32
    D3 --> D33
    D32 --> D321
    D32 --> D322

    D5 --> D51
    D5 --> D52
    D5 --> D53
    D52 --> D521
    D52 --> D522

    classDef root fill:#f5f5f5,stroke:#999,stroke-width:1px,color:#111;
    classDef header fill:#E8F0FE,stroke:#7BAAF7,stroke-width:1.5px,color:#111;
    classDef main fill:#F3E8FF,stroke:#B388EB,stroke-width:1.5px,color:#111;
    classDef navigation fill:#E8F5E9,stroke:#81C784,stroke-width:1.5px,color:#111;
    classDef content fill:#FFF3E0,stroke:#FFB74D,stroke-width:1.5px,color:#111;

    class A root;

    class B,B1,B2,B11,B12,B13,B131,B132,B133,B21,B22,B23,B211,B212,B221,B222 header;
    class C,C1,C2,C3 main;
    class C11,C12,C13,C14,C15,C21,C22,C221,C222,C223,C224 navigation;
    class C31,C32,D1,D2,D3,D4,D5,D11,D12,D13,D14,D121,D122,D123,D1231,D1232,D12311,D12312,D12313,D12314,D31,D32,D33,D321,D322,D51,D52,D53,D521,D522 content;
