# AGI Triage Lab 다이어그램

이 디렉토리는 AGI Triage Lab의 아키텍처와 개념을 시각화하는 D2 다이어그램을 포함합니다.

## D2 소개

[D2](https://d2lang.com/)는 텍스트 기반의 다이어그램 언어입니다.

## 다이어그램 목록

| 파일 | 설명 |
|------|------|
| `agi-triage-architecture.d2` | AGI Triage 핵심 아키텍처 |

## D2 설치 및 사용

### 설치

```bash
# macOS
brew install d2

# Linux (deb)
curl -fsSL https://d2lang.com/install.sh | sh

# Windows
choco install d2
```

### SVG로 변환

```bash
d2 agi-triage-architecture.d2 agi-triage-architecture.svg
```

### 라이브 프리뷰

```bash
d2 --watch agi-triage-architecture.d2 agi-triage-architecture.svg
```

## 다이어그램 기여

새로운 다이어그램을 추가하려면:

1. `.d2` 파일을 이 디렉토리에 추가
2. 대응하는 `.svg` 파일 생성
3. 이 README에 다이어그램 정보 추가
4. PR 제출
