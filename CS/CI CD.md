지속적인 통합 (Continuous Integration), 지속적인 서비스 제공(Continuous Delivery), 지속적인 배포(Continuous Deployment)로 구성

- CI는 테스트 자동화(테스트와 배포 전까지의 개발 단계), CD는 배포의 자동화

### 목적

: 배포 주기 단축 및 불편함을 최소화
즉, 애플리케이션 개발 단계를 **자동화**해 서비스 품질 향상과 동시에 보다 **짧은 주기**로 통합 및 배포하는 것이 가능

### CI(Continuous Integration), 지속적 통합

: **새로운 코드 변경 사항**을 정기적으로 빌드 및 테스트를 거쳐 공유 리포지토리에 **통합**하여 개발을 진행하면서도 품질을 관리할 수 있도록 하는 것. 즉, 버전 관리를 통한 **코드 병합, 테스트, 오류 보고**를 자동화해 공유 저장소에 병합시키는 프로세스

**버그**를 빠르게 찾아 해결, 소프트웨어 품질 개선, 새로운 업데이트 테스트와 출시 시간 단축 / 개발자 팀 사이에 충돌없이 동일한 앱을 동시에 작업 가능

#### 순서

1. 개발자가 구현한 코드를 기존 코드와 병합
2. 자동화된 빌드와 테스트가 트리거되어 실행, 병합된 코드가 올바르게 동작하고 빌드되는지 검증
3. 검증 결과 문제가 있다면 수정하고 다시 1로 돌아감. 문제가 없다면 **배포**를 진행

#### 기능 플래그

:기능 토글, 기능 스위치, 기능 통제 / 사용시 코드 액세스 통제가능, 코드 자체를 업데이트하지 않고도 소프트웨어의 특정 기능을 활성화하거나 비활성화할 수 있음, 트렁크 기반 개발방식으로 CI/CD를 수행하려는 경우 유용 - 새 기능을 사용자에게 즉시 제공하지 않아도 마스터로 병합 및 마스터에서 배포 가능

#### 안정적인 자동화된 테스트

:자동화된 테스트를 기반으로 하여 개발자가 개발 프로세스의 속도를 늦추지 않고 더 빠르게 더 정기적으로 코드를 변경해 품질을 높일 수 있음

#### 오류 수정의 우선순위 지정

: 오류 수정은 예방이 아닌 대응이기 때문에 시간이 부족한 경우가 많음. 자동화된 CI도구를 사용하면 오류를 더 빨리 파악하고 우선순위가 더 높은 수정사항을 자동으로 지정해 가장 중요한 문제를 더 빨리 해결할 수 있음

### CD(Continuous Deployment), 지속적 배포

- 지속적인 서비스 제공(Continuous Delivery)

  - CI과정을 거친 소스코드를 레포지토리에 자동으로 반영
  - 바로 프로덕션 단계로 배포하는 지속적인 배포 단계로 확장이 가능하지만 **따로 테스트 환경**에 배포하여 추가적인 여러 사용자 차원에서 테스트를 검증할 수 있는 단계
  - 개발 팀이 수동으로 배포를 트리거할 때까지 기다려야 한다는 점을 제외하면 지속적 배포와 유사
  - 수동 검토와 배포시간 고려해야 함

- 지속적인 배포(Continuous Deployment)
  - 모든 테스트를 거친 코드를 레포지토리에 자동으로 반영하는 지속적인 서비스 제공 단계의 확장된 형태
  - 애플리케이션 프로덕션 단계로 자동으로 배포하는 작업을 자동화하여 개발자가 변경 사항을 적용한 후 짧은 시간 이내에 사용자는 새로운 버전의 애플리케이션을 사용 가능

---

- 소프트웨어가 항상 신뢰 가능한 수준에서 배포될 수 있도록 관리하자는 개념으로 지속적 제공(Continuous Delivery)으로 사용되기도 함

- CD는 개발자의 변경 사항을 리포지토리에서 고객의 프로덕션 환경까지 자동으로 배포하는 것을 의미
- 성공적으로 병합된 내역을 저장소 뿐만 아니라 사용자가 사용할 수 있는 배포환경까지 릴리즈하는 것을 의미

- CD는 CI를 통해서 새로운 소스코드의 빌드와 테스트 병합까지 성공적으로 **된 후에 진행**되어야 함
