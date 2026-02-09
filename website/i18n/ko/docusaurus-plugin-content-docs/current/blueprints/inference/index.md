---
sidebar_label: 개요
sidebar_position: 1
---

# EKS에서의 추론

AI on EKS는 Amazon EKS에서 AI/ML 추론 워크로드를 배포하기 위한 포괄적인 솔루션을 제공하며, GPU와 AWS Neuron(Inferentia/Trainium) 하드웨어 구성을 모두 지원합니다.

## 빠른 시작 옵션

### 추론 차트 (권장)
미리 구성된 Helm 차트로 빠르게 시작하세요. 여러 모델과 배포 패턴을 지원합니다:

- **[추론 차트](./inference-charts.md)** - 인기 있는 모델을 위한 미리 구성된 값이 포함된 간소화된 Helm 기반 배포
- GPU와 Neuron 하드웨어 모두 지원
- VLLM 및 Ray-VLLM 프레임워크 포함
- Llama, DeepSeek, Mistral을 포함한 10개 이상의 인기 모델에 대해 미리 구성됨

## 하드웨어별 가이드

### GPU 배포
GPU 전용 추론 솔루션을 살펴보세요:

- [Ray와 vLLM을 사용한 DeepSeek-R1](./GPUs/ray-vllm-deepseek.md)
- [NVIDIA NIM과 Llama3](./GPUs/nvidia-nim-llama3.md)
- [NVIDIA NIM Operator](./GPUs/nvidia-nim-operator.md)
- [NVIDIA Triton Server와 vLLM](./GPUs/vLLM-NVIDIATritonServer.md)
- [Ray Serve와 vLLM](./GPUs/vLLM-rayserve.md)
- [GPU에서의 Stable Diffusion](./GPUs/stablediffusion-gpus.md)
- [AIBrix와 DeepSeek](./GPUs/aibrix-deepseek-distill.md)

### Neuron 배포 (AWS Inferentia)
비용 효율적인 추론을 위해 AWS Inferentia 칩을 활용하세요:

- [Inferentia2에서의 Llama2](./Neuron/llama2-inf2.md)
- [Inferentia2에서의 Llama3](./Neuron/llama3-inf2.md)
- [Inferentia2에서의 Mistral 7B](./Neuron/Mistral-7b-inf2.md)
- [Ray Serve 고가용성](./Neuron/rayserve-ha.md)
- [Inferentia2에서의 Ray와 vLLM](./Neuron/vllm-ray-inf2.md)
- [Inferentia2에서의 Stable Diffusion](./Neuron/stablediffusion-inf2.md)

## 아키텍처 개요

AI on EKS 추론 솔루션은 여러 배포 패턴을 지원합니다:

- vLLM을 사용한 **단일 노드 추론**
- Ray-vLLM을 사용한 **분산 추론**
- 로드 밸런싱이 포함된 **프로덕션 준비** 배포
- **자동 스케일링** 기능
- **관측성** 및 모니터링 통합

## 적합한 접근 방식 선택

| 사용 사례 | 권장 솔루션 | 장점 |
|----------|-------------|------|
| **빠른 프로토타이핑** | [추론 차트](./inference-charts.md) | 미리 구성됨, 빠른 배포 |
| **GPU** | [GPU 전용 가이드](/docs/category/gpu-inference-on-eks) | GPU 기반 추론 |
| **Neuron** | [Neuron 가이드](/docs/category/neuron-inference-on-eks) | Inferentia 기반 추론 |

## 다음 단계

1. 가장 빠른 배포 경로를 위해 **[추론 차트](./inference-charts.md)**로 시작하세요
2. 최적화된 구성을 위해 **하드웨어별 가이드**를 살펴보세요
3. 프로덕션 워크로드를 위한 **모니터링 및 관측성**을 설정하세요
