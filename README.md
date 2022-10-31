# 🔥2022 HUFS AI IDEA FESTIVAL🔥

## 프로젝트 주제 : AI-embedded 기술이 적용된 로우코드 플랫폼<br><br><br>

## 목차
* [1. 팀 구성](#chpater_1)
* [2. 프로젝트 연구목적](#chpater_2)
* [3. 프로젝트 설계](#chpater_3)
* [4. 프로젝트 연구결과](#chpater_4)
* [5. 프로젝트 기대효과](#chpater_5)
* [6. 추가 자료](#chpater_6)
* [7. 참고 자료](#chpater_7)<br><br><br>



## 팀 구성 <a id="chpater_1"></a>

* 팀명 : 로꼬로코(Loco Low-code)
> 팀장 정보통신공학과 18학번 김정헌  
> 팀원 정보통신공학과 18학번 김수연  
> 팀원 정보통신공학과 20학번 노현아  
> 팀원 정보통신공학과 18학번 한성관

<br><br>
## 프로젝트 연구목적 <a id="chpater_2"></a>
#### 인공지능(Artificial intelligence)는 현재 많은 대학교 및 교육기관에서 학습하고 연구되는 분야이다. 하지만 AI 분야 자체의 난이도가 낮지 않고 현장에서 사용되는 대부분의 기술들은 AI와 타 분야의 기술을 접목시킨 융합적 요소가 내포되어 있기 때문에 적용 분야에 대한 전반적인 지식을 가지고 있지 않다면 이를 활용하는데 어려움이 존재한다. 일례로 임베디드 아이디어 부문에서도 보드가 없다면 좋은 아이디어가 있더라도 구현이 어렵다는 문제가 존재하고 보드가 있더라도 이를 사용하기 위한 코딩 지식이 없다면 프로그램 구현에 어려움을 겪을 것이다.
#### 우리 로꼬로코(Loco Low-code)팀은 이러한 어려움을 해결하기 위해서 노코드 로우코드 플랫폼을 개발하여 비전공생들이 AI/임베디드 기술을 쉽게 접하고 활용할 수 있도록 돕고자 한다. 또한 전공생들에게는 프로젝트 진행 시 복잡한 프로그램 구현 이전에 현실화 가능성 등을 판단할 수 있는 이용할 수 있도록 하여 최종적으로는 해당 플랫폼을 통해 효율적인 코딩을 가능하게 하는 것이 이번 프로젝트의 연구 목적이다.<br><br><br>





## 프로젝트 설계 <a id="chpater_3"></a>
### I. AI Part
### II. Embedded Board Part
### III. Front-End Part
### IV. implementationv
<br><br>
> I. AI Part
  1) ONNX Structural Studies  
  : ONNX(Open Neural Network Exchange)란 DNN 표준 파일을 의미한다. 이 파일은 Tensorflow, pytorch 등의 여러 프레임워크에서 import, export 할 수 있다. 즉 여러 프레임워크에서 호환이 가능한 네트워크 파일이라는 특징이 있다. 사용자는 네트워크에 대한 깊은 이해를 요구받지 않는다. Input과 Output 형태만 잘 이해하면 누구든 쉽게 DNN을 다룰 수 있다. 따라서 우리 팀은 학생들이 ONNX를 활용하여 아이디어를 구현 가능하게 도울 계획이다.  

  2) Create "Executable AI-Network File" via ONNX  
  : ONNX는 네트워크 파일이기 때문에 ONNX만을 활용해서는 아이디어를 구현할 수 없다. 즉 ONNX 파일을 Parsing하여 그래프의 구조, 각 노드의 weight, bias등 data를 저장한 실행파일로 바꿔주는 Tool이 필요하다. 우리 팀은 이 Tool로 “ekut-es/pico-cnn” 프레임워크를 선택하였다. 이 프레임워크는 임베디드 시스템을 위한 경량 Neural Network 프레임워크이다. 이 프레임워크를 활용하면 선택한 ONNX를 Parsing하여 최종적으로 실행 파일을 생성한다. 사용자는 이 실행파일을 통해 적절한 input을 넣으면 생성되는 결과물을 갖고 아이디어를 구현 할 수 있게 된다.  

  3) pico-cnn framework 실행 순서  
   ¹ "onnx_to_pico_cnn.py" 코드를 활용해 선택한 onnx에 대한 network directory를 생성  
   ² 생성된 directory에서 네트워크 실행파일 생성  
   ³ 선택 네트워크가 ImageNet network라면 input으로 image를 넣어 예측 결과를 받는다.  
 <br><br>
 
 > II. Embedded Board Part  

 : 기존의 “노코드 로우코드 플랫폼“들은 프론트엔드 중심으로 구현되어있다. 따라서 우리의 로우코드 플랫폼에서의 프론트엔드 파트는 기존의 플랫폼의 방식을 차용하고자 한다. 기존의 노코드 플랫폼들은 ”드래그 앤 드랍“ function을 통해 작동된다. 유저들이 원하는 기능을 선택하고 적용하는 방식이다. '로우코드(Low-code)' 플랫폼은 데브옵스 툴체인과 통합돼 애플리케이션 딜리버리, 현대화, 자동화 등을 가속한다. 또한 팀이 다양한 애플리케이션을 제공, 지원, 확장할 수 있도록 하는데 이는 고객 경험 개선, 워크플로우 간소화, 데이터 통합 자동화, 데이터 시각화 지원 등 디지털 트랜스포메이션 과정에서도 사용된다. 애플리케이션 기획부터 개발, 모니터링까지 소프트웨어 개발 주기 전반에 걸쳐 다양한 기능을 제공한다.
  우리는 기존의 노코드 로우코드 플랫폼에 대해서 조사를 진행하였다. 각 플랫폼을 조사함으로써 우리에게 필요한 기능들이 무엇이고 어떻게 구현되는지를 조사하기 위함이다. 우리가 조사한 플랫폼으론 애피언, 멘딕스. 부미 플로우, 카스피오, 리툴이 있다. 우리가 조사한 노코드 로우코드 플랫폼 표는 별첨자료로 첨부하였다.
<br><br>
 
 > III. Front-End Part

: 기존의 “노코드 로우코드 플랫폼“들은 프론트엔드 중심으로 구현되어있다. 따라서 우리의 로우코드 플랫폼에서의 프론트엔드 파트는 기존의 플랫폼의 방식을 차용하고자 한다. 기존의 노코드 플랫폼들은 ”드래그 앤 드랍“ function을 통해 작동된다. 유저들이 원하는 기능을 선택하고 적용하는 방식이다. '로우코드(Low-code)' 플랫폼은 데브옵스 툴체인과 통합돼 애플리케이션 딜리버리, 현대화, 자동화 등을 가속한다. 또한 팀이 다양한 애플리케이션을 제공, 지원, 확장할 수 있도록 하는데 이는 고객 경험 개선, 워크플로우 간소화, 데이터 통합 자동화, 데이터 시각화 지원 등 디지털 트랜스포메이션 과정에서도 사용된다. 애플리케이션 기획부터 개발, 모니터링까지 소프트웨어 개발 주기 전반에 걸쳐 다양한 기능을 제공한다.
  우리는 기존의 노코드 로우코드 플랫폼에 대해서 조사를 진행하였다. 각 플랫폼을 조사함으로써 우리에게 필요한 기능들이 무엇이고 어떻게 구현되는지를 조사하기 위함이다. 우리가 조사한 플랫폼으론 애피언, 멘딕스. 부미 플로우, 카스피오, 리툴이 있다. 우리가 조사한 노코드 로우코드 플랫폼 표는 별첨자료로 첨부하였다.
<br><br>

> IV. implementation  
1) ONNX Parisng을 통한 네트워크 실행 파일 저장
2) 임베디드 장치 옵션을 노코드 로우코드로 구현
3) 임베디드 장치 input과 output 변수를 플랫폼의 input output 변수와의 연결 구현
4) 네트워크 실행파일 input과 output 변수를 플랫폼의 input output 변수와의 연결 구현
5) 임베디드-AI네트워크 연결을 front-end 파트에서 format화<br><br><br>
<br><br>

## 프로젝트 연구결과 <a id="chpater_4"></a>
- Alexnet ONNX를 이용한 네트워크 디렉토리 생성 및 Alexnet 실행파일에 이미지를 입력한 결과를 텍스트 파일에 저장

<div align="center">
  <img src="https://user-images.githubusercontent.com/96826443/198873781-6bb3777e-26da-4e3b-b42d-144b7c83adf5.png" width="60%" height="60%"><br>   
  <img src="https://user-images.githubusercontent.com/96826443/198873784-1e746e25-8546-463d-bdb6-531f57192394.png" width="60%" height="60%">  
  <br>
  <center>다음과 같은 결과 값들을 적용 시킬 수 있는 Embedded Board는 추가 평가자료에 첨부하였다.<br> 우리가 고안한 플랫폼은 Embedded Board를 통해 I/O를 조작하고 Neural Network를
이용하여 값에 대한 연산을 진행한다.</center><br><br><br><br><br><br>
</div>


- 애플리케이션으로 구현되었을 때의 예상 도안
<div align="center">
  <img src="https://user-images.githubusercontent.com/96826443/198874409-fb04846c-ce2f-4e65-b0ba-253e93e0ebc1.png" width="60%" height="60%"><br>
  <center>처음 View에서는 단계별 접근을 지원<br>네트워크를 선택 -> 임베디드 보드 선택 -> 프론트 엔드 구현</center><br><br><br><br><br><br>
  
  <img src="https://user-images.githubusercontent.com/96826443/198874474-0bc218a5-772c-41b6-a52e-a2e654d1d4d4.png" width="60%" height="60%"><br>
  <center>네트워크 선택 - MNIST 혹은 ImageNet으로 학습된 네트워크 선택지가 주어진다. (용도에 맞는 네트워크 선택 지원)</center><br><br><br><br><br><br>
</div>

<div align="center">
  <img src="https://user-images.githubusercontent.com/96826443/198874556-b9db6f9c-b554-4dd1-865c-31d2a343a3da.png" width="60%" height="60%"><br>
  <center>임베디드 보드 선택 - 성능 확인 옵션과 필요한 보드를 선택하기 위한 옵션 2가지 제공</center><br><br><br><br><br><br>
</div>

<div align="center">
  <img src="https://user-images.githubusercontent.com/96826443/198874592-bed891c2-2ed8-4402-a6d4-47792a8f709f.png" width="60%" height="60%"><br>
  <center>프론트 엔드 구현 - Input/Output 연결하여 프로젝트 구현을 지원한다.</center><br><br><br><br><br><br>
 </div>
 
 ## 프로젝트 기대효과 <a id="chpater_5"></a>
 
 #### 아이디어 구현에 있어서 가장 어려운 점은 실제로 구현할 수 있을까? 라는 두려움이 가장 크다고 생각한다. 하지만 우리가 고안한 플랫폼은 비전공생들이 쉽게 AI와 Embedded를 활용할 수 있기에 많은 아이디어를 실현화 시킬 수 있을 것 이라고 의심치 않는다. 전공생들만 임베디드와 AI를 다룰 뿐 아니라 비전공생들도 다룰 기회가 주어지게 된다면 여러 산업에 활용되리라 생각한다. 또한 전공생들은 본인의 아이디어를 구현하기 위해 어떤 보드를 활용해야 하는지, 혹은 이 보드를 활용한다면 어떤 아이디어가 구현 가능한지 실현시킬 수 있을지 알 수 있을 것이다. 즉 전공생들은 직접 보드를 통해 구현하기 전 아이디어를 검증 받거나 데모 버전을 만드는데 도움을 얻을 수 있다.
 노코드 로우코드 플랫폼은 현재 네이버, 구글 등 많은 대기업에서 눈여겨 보는 기술이다. 하지만 현재까진 프론트엔드 위주의 플랫폼으로 구현되고 있었다. 우리가 구상한 아이디어는 노코드 로우코드 플랫폼을 임베디드와 AI의 영역까지 확장시킬 수 있는 작은 도움이 될 수 있다고 기대한다.
 
 ## 추가 자료 <a id="chpater_6"></a>
 ## 참고 자료 <a id="chpater_7"></a>
