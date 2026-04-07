# Elice Design System

> 작성일: 2026. 04. 07

---

## 목차

1. [개요](#개요)
2. [컬러 토큰](#컬러-토큰)
3. [타이포그래피](#타이포그래피)
4. [스페이싱](#스페이싱)
5. [컴포넌트 색상](#컴포넌트-색상)
6. [설계 원칙 요약](#설계-원칙-요약)

---

## 개요

본 문서는 Elice 디자인 시스템의 핵심 토큰(색상, 타이포그래피, 스페이싱, 컴포넌트 색상)을 정리한 레퍼런스입니다.  
라이트/다크 모드를 모두 지원하며, **Elice 전용 폰트**와 **Pretendard** 두 가지 폰트 패밀리를 사용합니다.

---

## 컬러 토큰

모든 색상 토큰은 라이트(Light)와 다크(Dark) 두 가지 값을 가집니다.  
**Primary 컬러는 Violet 600 (#6700E6)** 을 기반으로 합니다.

### 전체 색상 팔레트

| 토큰 이름 | Light | Dark |
|-----------|-------|------|
| **Primary** | `#6700E6` (Violet 600) | `#6700E6` |
| Gray 50 | `#F2F0E8` | `#1A1A1A` |
| Gray 100 | `#D3D1C7` | `#2A2A2A` |
| Gray 400 | `#888780` | `#5F5E5A` |
| Gray 600 | `#5F5E5A` | `#888780` |
| Gray 800 | `#444441` | `#D3D1C7` |
| Gray 900 | `#1A1A1A` | `#F2F0E8` |
| Violet 50 | `#F0E5FF` | `#2E0066` |
| Violet 100 | `#D9BAFF` | `#4900A3` |
| Violet 200 | `#BE8FFB` | `#6700E6` |
| Violet 400 | `#9954F0` | `#9954F0` |
| Violet 600 | `#6700E6` | `#BE8FFB` |
| Violet 800 | `#4900A3` | `#D9BAFF` |
| Violet 900 | `#2E0066` | `#F0E5FF` |
| elice Violet | Violet 600 `#6700E6` | Violet 600 `#BE8FFB` |
| elice Black | `#000000` | `#FFFFFF` |
| elice White | `#FFFFFF` | `#000000` |

### 컬러 시스템 특징

- **Gray 계열**: 라이트 모드에서 밝은 값이 낮은 번호(Gray 50), 어두운 값이 높은 번호(Gray 900). 다크 모드에서 완전히 반전됩니다.
- **Violet 계열**: 라이트↔다크 모드에서 팔레트 내 값이 대칭적으로 반전됩니다.  
  예) Violet 200 Light(`#BE8FFB`) ↔ Violet 600 Dark(`#BE8FFB`)
- **Violet 400**: 라이트/다크 모두 `#9954F0` 으로 동일합니다 (중간값).
- **elice 브랜드 컬러**: elice Violet은 항상 Violet 600을 참조하며, elice Black/White도 다크 모드에서 반전됩니다.

---

## 타이포그래피

### 폰트 패밀리

| 그룹 | 폰트명 | 용도 |
|------|--------|------|
| elice 계열 | Elice DigitalBaeum | caption, label |
| elice 계열 | Elice DX Neolli | heading (h1/h2/h5), body |
| Pretendard 계열 | Pretendard | Placeholder |
| Pretendard 계열 | Pretendard Variable | Label, label s |

### 텍스트 스타일 상세

#### elice / heading

| 스타일 | 폰트 | 굵기 | 크기 | 행간 | 자간 |
|--------|------|------|------|------|------|
| h1 | Elice DX Neolli | Bold | 32px | 130% | 0% |
| h2 | Elice DX Neolli | Bold | 20px | 130% | 0% |
| h5 | Elice DX Neolli | Bold | 9px | 15px | -0.5px |

#### elice / body

| 스타일 | 폰트 | 굵기 | 크기 | 행간 | 자간 |
|--------|------|------|------|------|------|
| medium | Elice DX Neolli | Medium | 16px | 160% | 0% |

#### elice / 기타

| 스타일 | 폰트 | 굵기 | 크기 | 행간 | 자간 |
|--------|------|------|------|------|------|
| caption | Elice DigitalBaeum | Regular | 14px | 160% | 0% |
| label | Elice DigitalBaeum | Regular | 11px | 140% | 0% |

#### Pretendard

| 스타일 | 폰트 | 굵기 | 크기 | 행간 | 자간 |
|--------|------|------|------|------|------|
| Placeholder | Pretendard | Regular | 12px | Auto | 0% |
| Label | Pretendard Variable | Medium | 14px | 20px | 0px |
| label s | Pretendard Variable | Medium | 12px | 20px | 0px |

### 용도 가이드

- **h1** — 페이지 최상위 타이틀. 가장 크고 굵은 계층.
- **h2** — 섹션 제목.
- **h5** — 소형 레이블 타이틀. 자간 `-0.5px`로 밀도 높은 텍스트에 적합.
- **body/medium** — 일반 본문. 행간 160%으로 가독성 최적화.
- **caption** — 보조 설명 텍스트. Elice DigitalBaeum 사용.
- **label** — 작은 레이블. Elice DigitalBaeum 사용.
- **Label / label s** — UI 컴포넌트용 레이블. Pretendard Variable Medium.
- **Placeholder** — 입력 필드 플레이스홀더 전용. Pretendard Regular.

---

## 스페이싱

라이트/다크 모드 동일한 값을 사용합니다.

| 토큰 | 값 (px) | 비고 |
|------|---------|------|
| SM | 4 | 최소 여백 |
| S | 8 | |
| M | 12 | |
| L | 16 | |
| XL | 32 | 큰 섹션 간격 |
| Progress | 33.5 | 진행 표시 전용 특수 토큰 |

> **4px 기반 스케일**: SM(4) → S(8) → M(12) → L(16) → XL(32) 순으로 일관된 레이아웃 리듬을 제공합니다.

---

## 컴포넌트 색상

### Button / CTA

강조 액션 버튼. 브랜드 Primary 컬러(Violet 600)를 배경으로 사용합니다.

| 속성 | Light | Dark |
|------|-------|------|
| Base | Primary `#6700E6` | Primary `#6700E6` |
| Label | elice White `#FFFFFF` | elice White `#000000` |

### Button / Default

일반 버튼. 연한 Violet 200을 배경으로, Primary 컬러를 텍스트에 사용합니다.

| 속성 | Light | Dark |
|------|-------|------|
| Base | Violet 200 `#BE8FFB` | Violet 200 `#6700E6` |
| Label | Primary `#6700E6` | Primary `#6700E6` |

### Element (아이콘/UI 요소)

UI 내 아이콘 및 보조 요소에 사용합니다.

| 상태 | Light | Dark |
|------|-------|------|
| Default | Gray 800 `#444441` | Gray 800 `#D3D1C7` |
| Dimmed | Gray 400 `#888780` | Gray 400 `#5F5E5A` |

---

## 설계 원칙 요약

1. **다크/라이트 완전 지원**  
   모든 색상 토큰이 라이트·다크 쌍을 가집니다. Gray 계열과 Violet 계열은 다크 모드에서 값이 대칭 반전됩니다.

2. **Violet 브랜드 아이덴티티**  
   Primary 컬러는 Violet 600(#6700E6)이며, CTA 버튼 등 핵심 액션 요소에 일관되게 사용됩니다.

3. **이중 폰트 체계**  
   Elice 전용 폰트(DigitalBaeum, DX Neolli)는 제목/본문/캡션에, Pretendard 계열은 UI 컴포넌트 레이블과 입력 필드에 사용됩니다.

4. **4px 기반 스페이싱**  
   SM/S/M/L/XL이 4px 단위 배수로 구성되어 일관된 레이아웃 리듬을 제공합니다.

5. **컴포넌트 토큰화**  
   버튼(CTA/Default), 요소(Default/Dimmed) 등 컴포넌트별로 색상 토큰을 별도 정의하여 디자인 일관성을 유지합니다.
