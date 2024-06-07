# Poppin' ArgoCD Repository

## Structure
이 레포는 _Poppin'_의 ArgoCD App 설정 및 Helm Chart가 포함되어 있어요.
크게 `apps`, `charts`, `misc`로 구성되어있어요.

### Apps
ArgoCD App을 포함하고 있어요. Helm Chart를 바탕으로 `spec.source.helm.valuesObject`을 통해 Chart의 Value를 반영하고 있어요.

가장 상단에는 각 종류 별 `app-of-apps`가 위치하고 있어요. 
이 파일들은 직접 CLI를 통해 클러스터 생성 시에 선언해주고 있어요.

내부에는 common, databases, endpoint, secrets, services 디렉토리에서 각각 내부 운영 툴, DB, Istio VS + GW, `ExternalSecrets`, 실제 서비스를 배포하고 있어요.

### Charts
Helm Chart를 전부 보관하고 있는 디렉토리에요. `bitnami`와 같은 오픈소스 helm chart도 많이 활용했지만 직접 구성한 `microservice` 같은 Chart도 있어요.

### Misc
ArgoCD App이 아니지만 운영상 필요했던 일회성 스크립트와 YAML이 존재해요.
