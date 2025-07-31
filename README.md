# 앙상블 방식을 통한 YOLOv8 + PeopleNet + TrafficNet으로 사람/차량 탐지

## 앙상블이란?
앙상블 방식(Ensemble Method)은 말 그대로 여러 모델의 예측 결과를 결합해서 더 나은 성능을 내는 방법

## 앙상블이 필요한 이유
✅ 앙상블이 필요한 이유
<br>단일 모델은 다음과 같은 문제가 있을 수 있어요:

어떤 상황에서는 잘 작동하지만, 다른 조건에서는 약함

노이즈나 조명 같은 환경 변화에 민감함

한 모델이 놓친 객체를 다른 모델은 잘 잡을 수도 있음

그래서 YOLO, PeopleNet, TrafficNet 같은 특화된 모델을 동시에 활용해서 약점을 보완하는 거예요.
# 앙상블 방식을 통한 detect 코드 단계
## 1. 필수 라이브러리 설치

먼저 필요한 라이브러리를 설치해야 합니다. Colab에서 아래 명령어를 실행하여 `ultralytics`, `onnxruntime`, `ensemble-boxes` 등을 설치합니다.

## 2.이미지 업로드 및 로딩

Colab에서 이미지를 업로드하고, 해당 이미지를 로딩하는 코드를 작성합니다.

## 3. YOLOv8으로 사람/차량 감지

YOLOv8을 사용하여 사람과 차량을 탐지하는 코드를 작성합니다. 여기서는 yolov8n.pt 모델을 사용하고, 필요에 따라 다른 버전(yolov8s.pt, yolov8m.pt 등)을 사용할 수 있습니다.

## 4. PeopleNet / TrafficNet (가짜 추론 결과로 예시)

PeopleNet과 TrafficNet은 실제 ONNX 모델로 추론할 수 있습니다. 여기서는 예시로 가짜 추론 결과를 사용합니다. 실제 ONNX 모델이 있다면 이 부분을 수정하여 사용할 수 있습니다.

## 5. 앙상블 (Weighted Box Fusion)
여러 모델의 탐지 결과를 통합하여 최종 결과를 얻는 앙상블 기법인 Weighted Box Fusion(WBF)을 사용합니다. 

## 6. 전체 실행 & 시각화
각 모델을 실행하고, 최종 결과를 앙상블하여 시각화한다.

## 7. 결과 이미지
<img width="827" height="453" alt="화면 캡처 2025-07-31 114532" src="https://github.com/user-attachments/assets/9a897bec-d7da-4c6d-9d9d-3b46b56edbe3" />
YOLO v8을 사용했다 보니 detect의 정확성이 조금 떨어진 모습이 보인 아쉬움이 있다.
