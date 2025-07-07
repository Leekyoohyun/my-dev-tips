# 1. Minikube 사용 이유
로컬 개발·테스트 환경 제공

로컬 머신에서 실제 쿠버네티스 클러스터와 거의 동일한 환경을 빠르게 구성할 수 있습니다.

VM 또는 컨테이너 드라이버를 선택해 가볍게 실행 가능

학습 및 실습 최적화

복잡한 클라우드 셋업 없이도 kubectl 명령어, Deployment, Service, Ingress 등 주요 개념 실습 가능

한 대의 머신에서 여러 개의 가상 노드 구성도 지원

다양한 드라이버 지원

docker, hyperkit(macOS), virtualbox 등 여러 백엔드를 선택할 수 있어 환경 제약이 적습니다.

빠른 재시작 및 삭제

minikube stop / minikube delete로 클러스터를 즉시 중지·제거할 수 있어 실험·테스트 사이클이 짧아집니다.

Addon 확장성

minikube addons enable ingress/dashboard/metrics-server 등으로 추가 기능을 손쉽게 활성화 가능

# 2. Minikube 클러스터 실행 방법
클러스터 시작

minikube start
기본 드라이버(docker)가 설치되어 있으면 별도 옵션 없이 실행됩니다.

특정 드라이버 지정 시:

minikube start --driver=virtualbox
상태 확인

minikube status
kubectl get nodes

# 3. Minikube 클러스터 중지 및 삭제 방법
클러스터 중지

minikube stop
VM(또는 컨테이너) 상태를 보존한 채로 일시 중지합니다.

재시작 시 minikube start만 다시 실행하면 이전 상태가 복원됩니다.

클러스터 완전 삭제

minikube delete
생성된 가상 머신, 설정, 디스크 이미지를 모두 제거합니다.

완전 초기화 후 새로 시작해야 할 때 사용합니다.
