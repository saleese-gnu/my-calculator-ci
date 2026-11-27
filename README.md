# 계산기 (my-calculator-ci)

CMake 로 빌드하고 googletest 로 테스트하는 작은 C++ 예제다. 강의 자료 「3-2. CI/CD」의 사전 준비 예제(`sum.h`, `sum.cpp`, `main.cpp`, `sum_test.cpp`, `CMakeLists.txt`)와 같다.

## 빌드와 실행

```bash
cmake -S . -B build          # 구성 (처음 한 번은 googletest 를 내려받는다)
cmake --build build          # 빌드
./build/mainApp              # 실행 → 2 + 3 = 5
```

## 테스트

```bash
./build/testRunner
```

## 파일

| 파일 | 역할 |
| --- | --- |
| `sum.h` / `sum.cpp` | 두 정수의 합 `sum(a, b)` (테스트 대상) |
| `main.cpp` | 실행 프로그램 `mainApp` |
| `sum_test.cpp` | googletest 단위 테스트 `testRunner` |
| `CMakeLists.txt` | 빌드 설정 (googletest 자동 내려받기) |
| `sonar-project.properties` | SonarQube Cloud 분석 설정 (GUIDE 7단계에서 값 수정) |
| `.gitignore` | `build/` 등 빌드 결과는 커밋하지 않음 |
