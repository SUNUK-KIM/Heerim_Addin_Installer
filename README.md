# 🏢 Heerim Addin Manager & Installer

![Heerim Banner](https://img.shields.io/badge/Platform-Revit%202023--2026-brightgreen)
![.NET Version](https://img.shields.io/badge/.NET-4.8%20%7C%208.0-blue)
![Status](https://img.shields.io/badge/Status-Live-success)

> **"원클릭으로 끝내는 희림 건축 통합 애드인 환경"**  
> 본 프로젝트는 희림 종합건축사사무소의 표준 레빗 애드인과 추가 도구들을 통합 관리하고 자동 배포하기 위한 스마트 인스톨러입니다.

---

## ✨ 핵심 기능 (Key Features)

### 🚀 스마트 원클릭 설치 (Smart One-Click Install)
- **자동 버전 감지**: PC에 설치된 Revit 2023부터 2026까지의 모든 버전을 지능적으로 스캔합니다.
- **일괄 배포**: 복잡한 체크박스 선택 없이, 단 한 번의 클릭으로 사용 중인 모든 레빗 환경에 `.addin` 매니페스트를 자동 생성 및 연결합니다.

### 🔄 GitHub 통합 매니저 (Live Description Sync)
- **실시간 소통**: GitHub 릴리스 섹션의 설명글(`Body`)을 실시간으로 파싱하여 인스톨러 화면에 표시합니다. 별도의 업데이트 없이도 최신 기능 설명을 사용자에게 전달합니다.
- **동적 자산 관리**: 최신 엔진(Core)과 개별 플러그인 자산을 GitHub API를 통해 안전하고 빠르게 다운로드합니다.

### 📂 계층형 플러그인 아키텍처 (Hierarchical Architecture)
- **버전별 자동 분류**: 설치 단계에서 플랫폼(.NET 4.8 / 8.0)에 맞춰 플러그인들을 계층형 폴더로 자동 정렬합니다.
- **동적 로딩**: 독립적으로 개발된 DLL들을 메인 로더가 재귀적으로 탐색하여 지능적으로 리본 탭에 구성합니다.

---

## 🛠️ 설치 및 사용 방법 (How to Use)

1. **다운로드**: [Releases](https://github.com/SUNUK-KIM/Heerim_Addin_Installer/releases) 페이지에서 최신 `Heerim_Installer.exe`를 다운로드합니다.
2. **실행**: 인스톨러를 실행하면 현재 설치된 레빗 버전이 자동으로 감지됩니다.
3. **설치**: `[설치]` 버튼을 클릭하면 엔진과 기본 플러그인이 즉시 배포됩니다.
4. **기능 추가**: `Revit Addins` 탭에서 **Excel Manager**, **DivideSheet** 등 필요한 기능을 추가로 다운로드할 수 있습니다.

---

## 🏗️ 폴더 구조 표준 (Standards)

인스톨러는 희림 전사 표준 경로인 `C:\ProgramData\HeerimTools`를 기준으로 동작합니다.

```text
C:\ProgramData\HeerimTools
├── 📂 Engine            # Revit 버전별 메인 로더 (2024, 2026)
└── 📂 Plugins           # 계층형 플러그인 저장소
    ├── 📂 net48         # Revit 2023, 2024용 플러그인
    │   └── 📂 DivideSheet
    └── 📂 net8.0        # Revit 2025, 2026용 플러그인
        └── 📂 ExcelManager
```

---

## 🧑‍💻 개발자 가이드 (For Developers)

새로운 기능을 추가하고 싶다면 다음 규칙을 준수하여 GitHub에 릴리스해 주세요:
- **DLL 명명**: `Heerim_` 접두어를 사용해야 자동 로더가 인식합니다. (예: `Heerim_MyTool.dll`)
- **릴리스 설명**: GitHub 릴리스의 'Description'에 한글 설명을 적어주시면 인스톨러에 즉시 반영됩니다.

---

## 📄 License
Copyright © 2026 HEERIM ARCHITECTS & PLANNERS. All rights reserved.
