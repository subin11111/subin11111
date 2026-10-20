# Projects / Subin

[← 프로필로 돌아가기](README.md)

차량 제어, 자율주행 통합, 로봇 시뮬레이션과 공간 지도, 웹 서비스 프로젝트를 정리했습니다. 연계 저장소는 하나의 프로젝트 아래 묶었습니다.

<a id="team-control"></a>

## 1. Team K.A.I. 차량 제어와 시스템 통합

**활동:** 2026 자율주행 PM · 2025 제어파트·총무 · 2024 제어파트 파트원

### 2026 — 임베디드 제어·검증 환경 확장

아래는 PM으로 참여하는 팀 시스템의 개발 내용입니다. 구성요소의 개발·시험 단계는 각각 다릅니다.

| 영역 | 프로젝트 내용 |
| --- | --- |
| 구동·제동 펌웨어 | STM32 기반 차량 입력, 구동 모터, 브레이크와 비상정지 처리 |
| ROS 2 연결 | micro-ROS와 CAN을 통한 호스트·제어기 연동, 차량 상태 통합 |
| 제어 실험 | 종방향 속도·전류 제어, 조향 제어, 식별 기반 MPC와 로그 분석 |
| SITL / HIL | Gazebo 차량 모델과 시뮬레이션, STM 시험 보드와 CAN 에뮬레이션 |
| Vehicle Console | 차량 상태 관측과 HIL 시험을 위한 Web Console |
| 시험·튜닝 도구 | 시나리오 실행, 파라미터 관리, MCAP 기록·분석과 진단 |
| 계기판·계측 | UNO R4 계기판, RP2350·INA228 기반 배터리 계측 |

**인지·판단 협업 요약:** 인지는 주변 환경 정보를 만들고, 판단은 주행 행동과 경로로 연결합니다.

**기술:** ROS 2 Humble, C/C++, Python, STM32, micro-ROS, CAN, Gazebo, HIL, MPC

[TeamKAI-DL](https://github.com/TeamKAI-DL) · 팀 내부 저장소는 접근 권한이 필요합니다.

### 2025 — ROS 2 통합 차량 제어

- Arduino Mega VCU와 ROS 2 노드를 연결한 구동·조향 통합 제어
- CAN 기반 모터 통신과 시리얼 입력 처리
- 수동·자율·비상정지 모드, 차량 상태와 속도 피드백
- 회장단 총무로 팀 운영에 참여

**기술:** C++, Python, Arduino, ROS 2, CAN, Serial

**결과:** 2025 대학생 창작 모빌리티 경진대회 자작자율차 부문 창작기술 우수상(1위), 자율주행성능 특별상

[공개 제어 저장소](https://github.com/subin11111/ros2-autonomous-control)

### 2024 — 자작자율차 제어파트

자율주행팀 제어파트 파트원으로 자작자율차 개발에 참여하고, 전국 대학생 창작 모빌리티 경진대회 자작자율차 부문에 참가했습니다.

<a id="kookmin-competition"></a>

## 2. 국민대학교 자율주행 경진대회 — Xycar 통합 주행

**2026 국민대학교 자율주행 경진대회 특별상 · Team K.A.I. 팀 프로젝트**

ROS 2 Humble 기반 Xycar에서 차선 주행과 대회 미션을 연결한 실차 통합 프로젝트입니다. 카메라·LiDAR의 환경 정보를 이용해 주행 후보를 만들고, 상황별 우선순위와 랩 정책에 따라 최종 명령을 선택합니다.

| 영역 | 프로젝트 내용 |
| --- | --- |
| 차선 주행 | 영상 기반 중앙선 경로와 Pure Pursuit·Stanley 혼합 제어 |
| 미션 통합 | 신호등 대응, 지름길 선택, 라바콘 주행, 차량 회피 간 우선순위 전환 |
| 랩 정책 | 3바퀴 주행에서 출발과 지름길 선택을 관리하는 상태·세션 처리 |
| 모터 출력 | 단일 출력 게이트를 통한 VESC 명령과 상태·fault 감시 |
| 기록·검증 | ROS bag 기록, 독립 빌드, 미션·랩 정책 단위 테스트 |

**기술:** ROS 2 Humble, Python, Xycar, Camera, LiDAR, Pure Pursuit, Stanley, VESC

**팀 검증 기록:** [원본 README](https://github.com/steveandy-sudo/kookmin_autonomous_competition_teamKAI#현재-검증-상태)에 2026-08-23 실차 통합 주행 3바퀴 완주와 관련 pytest 320개 통과가 기록되어 있습니다.

**저장소:** 공동 작업 이력과 원본 연결을 유지하기 위해 개인 계정에 포크했습니다.

[개인 계정의 대회 저장소](https://github.com/subin11111/kookmin_autonomous_competition_teamKAI) · [원본 팀 저장소](https://github.com/steveandy-sudo/kookmin_autonomous_competition_teamKAI)

## 3. Folded City — 실내외 지도와 경로 탐색

**질문:** 건물 앞에서 끝나는 지도를 목적지의 문 앞까지 이어갈 수 있을까?

iPhone의 RGB-D와 저장 포즈로 공간을 복원하고, 실외·로비·계단·2층 촬영본을 연결했습니다. 영상 특징 대응과 기하 검사, 포즈 그래프 최적화 후보를 비교하고, 층별 보행 격자에서 A* 경로를 계산해 실제 사진 길안내와 웹 지도에 연결했습니다.

- RGB-D 기록 복원, 전처리와 좌표계 정리
- SIFT/RootSIFT·LoFTR 대응 후보와 RANSAC·ICP 기반 검사
- 강건 최적화와 여러 촬영본의 연결 비교
- 층·계단을 포함한 보행 경로, 3D 지도와 사진 안내
- ROS 2 재생·RViz 관측과 웹 인터페이스

**기술:** Python, OpenCV, Open3D, NumPy, SciPy, PyTorch, ROS 2, Three.js

**활동 맥락:** 건국대학교 학술공모전 성(誠) 분야.

[공개 연구·코드](https://github.com/subin11111/folded-city-atlas-public) · [연구 이력](https://github.com/subin11111/folded-city-atlas-public/blob/main/README_HISTORY.md) · [웹 지도](https://folded-city-atlas.vercel.app/)

## 4. ASP — UAV·UGV 협업 시뮬레이션

PX4-Autopilot/ASP 제공 환경을 기반으로 UAV와 UGV가 같은 Gazebo 월드에서 동작하도록 연동했습니다. 시뮬레이터 구성과 ROS 2 미션 코드를 서로 다른 저장소에서 관리합니다.

| 저장소 | 맡는 부분 |
| --- | --- |
| [asp · jsb 브랜치](https://github.com/subin11111/asp/tree/jsb) | PX4 SITL·Gazebo 월드, 차량 모델·명령 토픽 정합 |
| [asp_ws](https://github.com/subin11111/asp_ws) | ROS 2 브리지, UAV·UGV 명령 분리, 키보드 제어, 미션·착륙 실험 |

- 카메라·LiDAR·TF 브리지와 RViz 연결
- UGV 주행과 UAV 비행 명령 경로 분리
- 협업 탐색 미션 전환과 ArUco 기반 착륙 정렬·하강 실험
- 시뮬레이션에서 명령·센서·상태 흐름 확인

**기술:** PX4, Gazebo, ROS 2, Python, C++, ArUco

작업 범위는 기존 PX4·ASP 환경을 바탕으로 저장소에 기록한 수정·확장과 연동 실험입니다.

## 5. Autonomous Driving Platform

차선 인식, 주행 명령 생성과 MCU 통신을 연결하는 ROS 2 기반 자율주행 통합 프로젝트입니다.

- YOLOPv2 기반 인식 패키지와 차선 처리 실험
- 주행 명령 생성 패키지와 차량 시리얼 브리지
- 인식 → 주행 명령 → MCU 경로를 연결하는 bringup
- 모의 시리얼 환경에서의 통합 점검

**기술:** ROS 2, Python, YOLOPv2, Serial

[저장소](https://github.com/subin11111/autonomous-driving-platform)

## 6. Life Map Diary

전국 읍면동별로 일상과 사진을 남기는 개인 기록 지도입니다. 기록이 쌓이는 지역을 색으로 표시하고, 지역별 타임라인과 통계를 제공합니다.

- 네이버 배경지도와 MapLibre 벡터 경계 오버레이
- PMTiles 기반 전국 읍면동 경계 렌더링
- 지도·기록·사진 관리와 공유
- Supabase 인증, 데이터베이스와 스토리지 연동

**기술:** Next.js, React, TypeScript, Tailwind CSS, Supabase, Naver Maps, MapLibre, PMTiles

[저장소](https://github.com/subin11111/travel-map-diary)

## 7. GOBBLEFIN

작은 물고기를 먹고 성장하는 실시간 경쟁형 웹 아케이드 게임입니다.

- Canvas 기반 게임 루프와 충돌 판정
- 닉네임 기반 멀티플레이와 경쟁자 AI
- 성장·대시·랭킹·코인과 물고기 디자인 상점
- 데스크톱 마우스와 모바일 터치 조작

**기술:** HTML Canvas, JavaScript, 실시간 게임 상태 처리

[저장소](https://github.com/subin11111/gobblefin) · [플레이](https://gobblefin-reef-arena.hazy-skink-6279.chatgpt.site)

## 8. Bike Anomaly — ADP LAB 동계 인턴

**2026 동계 인턴 · 건국대학교 ADP LAB · 문창주 교수님 연구실**

연구실 동계 인턴으로 진행한 이상 탐지·조기 경보 프로젝트입니다. 비지도 학습과 ML·DL 접근, 표 형식·시계열 입력, 데이터셋 구성과 평가 도구를 비교·정리했습니다.

**기술:** Python, 비지도 학습, 머신러닝, 딥러닝, 시계열 분석

**공개 범위:** 프로젝트 개요. 저장소와 데이터는 비공개입니다.
