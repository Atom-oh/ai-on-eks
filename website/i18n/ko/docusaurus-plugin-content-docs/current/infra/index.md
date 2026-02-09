---
sidebar_position: 0
sidebar_label: 소개
---

# 소개

AIoEKS 기반 인프라는 `infra/base` 디렉토리에 있습니다. 이 디렉토리에는 실험, AI/ML 학습, LLM 추론, 모델 추적 등을 지원하는 환경을 구성할 수 있는 기본 인프라와 모든 모듈이 포함되어 있습니다.

디렉토리에는 원하는 모듈을 활성화하거나 비활성화하는 데 사용되는 모든 매개변수가 포함된 `variables.tf`가 있습니다 (기본값은 `false`로 설정). 이를 통해 Karpenter와 GPU 및 AWS Neuron `NodePool`을 갖춘 기본 환경을 배포하여 가속기 사용 및 추가 커스터마이징이 가능합니다.

참조 구현인 `jark-stack`은 실험을 위한 JupyterHub, [Ray Clusters](https://docs.ray.io/en/latest/cluster/getting-started.html)를 사용한 학습 및 추론을 위한 KubeRay 오퍼레이터, 워크플로우 자동화를 위한 Argo Workflows, 스토리지 컨트롤러 및 볼륨을 활성화하여 빠른 AI/ML 개발을 지원하는 환경을 배포합니다.

다른 블루프린트는 동일한 기반 인프라를 사용하며 블루프린트의 필요에 따라 다른 컴포넌트를 선택적으로 활성화합니다.

## 리소스

각 스택은 `base` 스택의 컴포넌트를 상속합니다. 이러한 컴포넌트에는 다음이 포함됩니다:

- 2개 가용 영역에 서브넷이 있는 VPC
- 최소 인프라를 실행하기 위한 2개 노드를 가진 1개 코어 노드그룹이 있는 EKS 클러스터
- CPU, GPU, AWS Neuron NodePool을 갖춘 Karpenter 오토스케일링
- GPU/Neuron 디바이스 드라이버
- GPU/Neuron 모니터링 에이전트
