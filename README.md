# mySBApp

Spring Boot 애플리케이션을 위한 Gradle 빌드 스켈레톤입니다. 현재 저장소에는 애플리케이션 소스와 테스트가 포함되어 있지 않습니다.

## 요구 사항

- Java 17
- 별도의 Gradle 설치는 필요하지 않습니다.

## 검증

```powershell
.\gradlew.bat clean test jar cyclonedxBom spotbugsMain spotbugsTest
```

현재 소스 세트가 비어 있으므로 `test`, `spotbugsMain`, `spotbugsTest`는 `NO-SOURCE`로 완료됩니다. 실행 가능한 메인 클래스가 없어 `bootJar`는 비활성화되어 있으며, 일반 JAR만 생성합니다.

## 외부 서비스

OAuth2 공급자와 MariaDB를 사용하는 통합 테스트는 이 저장소에 포함하지 않습니다. 해당 기능을 구현할 때는 자격 증명을 환경 변수 또는 로컬 전용 설정으로 주입하고, 실제 외부 서비스 검증은 기본 빌드와 분리된 명시적 프로필에서 실행해야 합니다. 비밀값과 `.env` 파일은 커밋하지 않습니다.
