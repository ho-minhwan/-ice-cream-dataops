# Cognite Data Fusion (CDF) Bootcamp

## 프로젝트 개요

본 저장소는 Cognite Data Fusion(CDF) Bootcamp 학습 및 실습을 위한 프로젝트입니다.

CDF Toolkit을 활용하여 다음 내용을 실습합니다.

- Data Foundation
- Data Integration
- Data Modeling
- Transformation
- Cognite Functions
- Data Workflow
- CI/CD Deployment

---

# 개발 환경

## Python

```bash
python --version
```

현재 사용 버전

```text
Python 3.11.16
```

## UV

```bash
uv --version
```

예시

```text
uv 0.12.13
```

---

# 가상환경 실행

## 활성화

```bash
.venv\Scripts\activate
```

정상 실행 시

```text
(bootcamp)
```

표시 확인

## 비활성화

```bash
deactivate
```

---

# 패키지 설치

## Toolkit 설치

```bash
uv add cognite-toolkit==0.6.53
```

## 의존성 동기화

```bash
uv sync
```

---

# CDF Toolkit

## 버전 확인

```bash
uv run cdf --version
```

## 인증 확인

```bash
uv run cdf auth verify
```

## 모듈 초기화

```bash
uv run cdf modules init
```

---

# 프로젝트 구조

```text
bootcamp
│
├── .venv
├── src
├── pyproject.toml
├── uv.lock
└── README.md
```

CDF 모듈 생성 후 예시

```text
modules
└── bootcamp
    ├── ice_cream_api
    └── use_cases
        └── oee
```

---

# 주요 개념

## Dataset

데이터 출처를 관리하는 논리적 그룹

예시

- Proarc
- IMIS
- SAP
- AVEVA

---

## RAW Database

원본 데이터 적재 영역

```text
Source System
      ↓
     RAW
      ↓
Transformation
      ↓
Data Model
```

---

## Transformation

RAW 데이터를 정제 및 가공하여 데이터 모델로 변환

---

## Function

파이썬 코드 기반 서버리스 실행 환경

예시

- 데이터 정제
- API 호출
- 스케줄 작업

---

## Module

CDF Toolkit 배포 단위

예시

```text
Proarc Module
 ├─ Dataset
 ├─ RAW
 ├─ Transformation
 ├─ Function
 └─ Extraction Pipeline
```

---

# 배포 흐름

```text
YAML 작성
    ↓
cdf build
    ↓
cdf deploy
    ↓
CDF 반영
```

---

# 자주 사용하는 명령어

## 현재 패키지 목록

```bash
uv pip list
```

## 의존성 트리

```bash
uv tree
```

## 패키지 추가

```bash
uv add <package-name>
```

예시

```bash
uv add pandas
```

## 패키지 제거

```bash
uv remove <package-name>
```

---

# Troubleshooting

## SSL 인증서 오류

```text
invalid peer certificate: UnknownIssuer
```

해결

```bash
set UV_SYSTEM_CERTS=true
```

또는

```bash
uv --system-certs python install 3.11
```

---

## protobuf 관련 오류

```text
ModuleNotFoundError: No module named 'google.protobuf'
```

확인

```bash
uv run python -c "import google.protobuf"
```

필요 시

```bash
uv sync --reinstall
```

---

# 참고 자료

- Cognite Academy
- Cognite Documentation
- CDF Toolkit Documentation
- GitHub Repository

---

# 실습 메모

## TODO

- [ ] Azure Service Principal 생성
- [ ] CDF 인증 설정
- [ ] Bootcamp Module 초기화
- [ ] Dataset 배포
- [ ] RAW Schema 생성
- [ ] Transformation 배포
- [ ] Function 배포
- [ ] Workflow 배포

---

작성자: 김민환