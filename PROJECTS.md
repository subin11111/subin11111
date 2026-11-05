# Projects / Subin

[← 프로필로 돌아가기](README.md)

차량 제어, 자율주행 통합, 로봇 시뮬레이션과 공간 지도, 웹 서비스 프로젝트를 정리했습니다. 연계 저장소는 하나의 프로젝트 아래 묶었습니다.

<a id="team-control"></a>

## 1. Team K.A.I. 차량 제어와 시스템 통합

**활동:** 2026 자율주행 PM · 2025 제어파트·총무 · 2024 제어파트 파트원

### 2026 — AI·S/W 모빌리티 경진대회 대상

**개인 역할: 자율주행 PM · 인지·판단·제어 전반 참여 · 인지·제어 중심 기여**

**팀 성과:** 2026 대학생 AI·S/W 모빌리티 경진대회 자작자율차 부문 **대상(국토교통부장관상) · 랩타임 1위**, 창작기술부문 **특별상 · 기술보고서 1위**.

| 영역 | 역할과 시스템 구성 |
| --- | --- |
| 프로젝트 관리 | 대회 요구사항과 개발 목표 정리, 파트별 일정·우선순위·이슈 조율 |
| 전체 통합 | 인지·판단·제어 인터페이스, 실차 시험·재검증과 현장 운용, 기술 문서 협업 관리 |
| 인지 · 주요 참여 | 카메라·LiDAR 도로·객체·신호 관측을 후단과 연결, GNSS·IMU·휠 속도 ESKF 위치 추정 |
| 판단 파트 협업 | 미션·경로·속도 계획과 Pure Pursuit·Stanley 경로 추종을 담당하는 판단 파트와 인터페이스 통합 |
| 제어 · 임베디드·RTOS | STM32 펌웨어, FreeRTOS의 입력·제어·통신·계측 태스크 분리와 실행 주기·우선순위 관리 |
| 제어 · 구동·회생제동 | 속도 오차를 모터 전류 명령으로 변환하는 PI 제어와 회생전류 제어, 구동·감속 응답 확인 |
| 제어 · 조향·제동·안전 | 조향 피드백·브레이크 구동, micro-ROS·CAN·UART 통신, 명령 유효성·통신 단절·E-stop 처리 |

팀 공동 시스템에서 PM으로 개발과 운영 전반에 관여했으며, 기술적으로는 인지와 임베디드 제어를 중심으로 참여했습니다. 판단 파트가 주행 행동·경로·목표 명령을 생성하고, 제어 파트가 RTOS 기반 펌웨어와 Host 제어 노드로 실제 차량을 구동하는 역할을 구분해 소개합니다. **원본 소스·모델·대회용 데이터·설정은 비공개**로 유지하고, 공개 저장소에는 최종 로직의 사용 목적과 시스템 흐름, 역할·수상 자료·주행 영상을 정리했습니다.

[2026 포트폴리오](https://github.com/subin11111/teamkai-2026-portfolio) · [PM 역할](https://github.com/subin11111/teamkai-2026-portfolio/blob/main/docs/ROLE.md) · [시스템 요약](https://github.com/subin11111/teamkai-2026-portfolio/blob/main/docs/SYSTEM.md) · [주행 영상](https://github.com/subin11111/teamkai-2026-portfolio#driving)

### 2025 — Team K.A.I. 전체 자율주행 시스템

**개인 역할: 제어파트 · 회장단 총무.** 팀의 인지·판단·제어와 통합 자료를 2025년 11월 3일 기준으로 정리한 프로젝트입니다.

| 영역 | 팀 프로젝트 내용 |
| --- | --- |
| 인지·위치 추정 | 카메라·LiDAR 콘 검출, 센서 보정·추적, RTK / INS 구성 |
| 3D 검출 실험 | OpenPCDet / VoxelNeXt 관련 구성 |
| 판단·추종 | 전역·로컬 경로, 콘 라벨링, 속도 계획, Pure Pursuit |
| 차량 제어 · 개인 참여 | Arduino Mega VCU, CAN 기반 모터·조향 통신, 시리얼 입력, 수동·자율 모드와 상태 피드백 |
| 통합·운용 | ROS 2 메시지·실행 구성, RViz·대시보드, 운용 문서 |

**결과:** 2025 대학생 창작 모빌리티 경진대회 자작자율차 부문 창작기술 우수상(1위), 자율주행성능 특별상

**전체 원본은 대회 준비를 위해 비공개입니다.** 7개 원본 저장소의 32개 브랜치 참조를 별도 보관했으며, 공개본에는 각 파트의 기본 개념을 선별·축약한 코드와 기술 설명을 담았습니다. 실차 입출력·모델·보정·위치·대회 튜닝값은 공개 예제에서 제외했습니다. 인지·판단은 팀 공동 작업으로 소개하며 개인 단독 구현으로 표기하지 않습니다.

[2025 공개 포트폴리오](https://github.com/subin11111/teamkai-2025-portfolio) · [선별 코드](https://github.com/subin11111/teamkai-2025-portfolio/tree/main/examples) · [기술과 역할](https://github.com/subin11111/teamkai-2025-portfolio/blob/main/SKILLS.md)

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

<a id="autonomous-platform"></a>

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
