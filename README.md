<p>
  <img src="assets/profile-hero.svg" width="100%" alt="Subin. 자율주행을 만들고, 시스템을 연결합니다. 2026 Team K.A.I. 자율주행 PM · 건국대학교 스마트운행체공학과">
</p>

<p align="center">
  <a href="#team-kai"><b>경력</b></a> &nbsp;&nbsp; / &nbsp;&nbsp;
  <a href="#awards"><b>수상</b></a> &nbsp;&nbsp; / &nbsp;&nbsp;
  <a href="#projects"><b>Team K.A.I. 프로젝트</b></a> &nbsp;&nbsp; / &nbsp;&nbsp;
  <a href="#experience"><b>활동</b></a>
</p>

<br>

제 프로젝트의 중심은 **Team K.A.I. 자율주행 차량 개발**입니다. 2026년에는 **자율주행 PM**으로 시스템 통합과 개발을 진행하고 있으며, 2025·2024년에는 제어파트에서 활동했습니다. **차량 제어·임베디드·ROS 2 통합·SITL/HIL 검증**을 연결합니다.

<a id="team-kai"></a>

## 01 / Team K.A.I.

| 연도 | 역할 | 활동 |
| :--- | :--- | :--- |
| **2026** | **자율주행 PM** | 자율주행 프로젝트 관리 · 차량 제어 및 시스템 통합 |
| **2025** | **제어파트 · 회장단 총무** | ROS 2 차량 제어 · 팀 운영 · 창작 모빌리티 경진대회 |
| **2024** | **제어파트 파트원** | 자작자율차 개발 · 전국 대학생 창작 모빌리티 경진대회 참가 |

<a id="projects"></a>

## 02 / Team K.A.I. Projects

### 2026 · KAIEV26 — 자율주행 차량 제어와 통합 검증

**Team K.A.I. 자율주행 PM · 현재 진행 중**

자작자율차의 **구동·조향·제동을 ROS 2와 임베디드 제어기로 연결**하는 팀 프로젝트입니다. 차량을 움직이는 하위 제어부터 시스템 식별, 제어기 비교, 시뮬레이션과 HIL 시험, 상태 관측까지 하나의 개발 흐름으로 구성합니다.

> **2026 대회가 진행 중이므로 프로젝트 저장소와 소스코드는 비공개입니다. 이곳에는 프로젝트 개요만 소개합니다.**

- **차량 제어·펌웨어** — STM32 기반 구동·브레이크 제어와 micro-ROS·CAN 통신, 조향 액추에이터 및 차량 상태 통합
- **모델 기반 제어** — 주행 기록에서 모델을 식별하고, 조향·종방향 MPC와 기존 제어기의 응답을 비교하는 개발·분석
- **SITL / HIL** — Gazebo와 STM 시험 보드, CAN 에뮬레이션을 연결해 입력·상태·명령 경로를 시험하는 환경
- **시험·운용 도구** — 시나리오 러너, 파라미터 튜닝, MCAP 기록·분석, Vehicle Console 관측 및 HIL 인터페이스

`ROS 2 Humble` `C / C++` `Python` `STM32` `micro-ROS` `CAN` `MPC` `Gazebo` `SITL / HIL`

[프로젝트 개요와 제어 구성 ↗](PROJECTS.md#team-control)

<sub>팀 프로젝트의 개발 내용을 소개합니다. 각 구성요소의 구현·검증 단계는 서로 다릅니다. 인지·판단은 센서 정보와 주행 행동을 연결하는 협업 맥락으로만 요약합니다.</sub>

---

### 2026 · 국민대학교 자율주행 경진대회 — Xycar 통합 주행

**특별상 · Team K.A.I. 팀 프로젝트**

Xycar에서 **차선 추종·신호등·지름길·라바콘·차량 회피**를 연결한 실차 통합 주행 프로젝트입니다. Pure Pursuit·Stanley 기반 추종 제어, 미션 우선순위 전환과 랩 정책을 통합하고 최종 모터 명령을 하나의 출력 경로로 관리합니다.

- 카메라·LiDAR 정보를 이용한 차선·장애물·미션별 주행 후보 연결
- 신호등과 지름길 선택, 라바콘 주행 및 차량 회피 사이의 상태·우선순위 전환
- 모터 출력 게이트, VESC 상태 감시와 ROS bag 기반 주행 기록
- 팀 기록 기준 **2026-08-23 실차 3바퀴 완주**, 미션·랩 정책 테스트 및 독립 빌드 확인

`ROS 2 Humble` `Python` `Xycar` `Camera · LiDAR` `Pure Pursuit · Stanley` `VESC`

[공개 대회 코드 ↗](https://github.com/subin11111/kookmin_autonomous_competition_teamKAI) &nbsp;·&nbsp; [프로젝트 상세 ↗](PROJECTS.md#kookmin-competition)

<sub>공동 작업의 이력과 출처를 유지한 팀 저장소 포크입니다.</sub>

---

### 2025 · ROS 2 Autonomous Control — 자작자율차 구동·조향 통합 제어

**Team K.A.I. 제어파트 · 회장단 총무**

Arduino Mega VCU와 ROS 2를 연결해 **가속 입력부터 모터 명령·피드백까지의 차량 제어 경로**를 구성했습니다. C++ 모터·조향 노드와 Python 시리얼·모드 선택 노드를 함께 운용하는 구조입니다.

- **구동 제어** — 페달·차량 입력을 시리얼로 수신하고 수동/자율 RPM 명령을 선택해 CAN으로 전달
- **조향 제어** — 목표 조향각을 모터 위치 명령으로 변환하고 엔코더 피드백 수신
- **모드·비상정지** — AUTO / MANUAL / ESTOP 전환과 하드웨어·소프트웨어 정지 경로
- **관측·통합** — 실제 RPM과 조향 상태를 ROS 2 토픽으로 확인하고 통신·운용 절차 문서화

**팀 성과** · 2025 대학생 창작 모빌리티 경진대회 자작자율차 부문 **창작기술 우수상(1위) · 자율주행성능 특별상**

`ROS 2` `C++` `Python` `Arduino Mega` `CAN` `Serial` `VCU`

[공개 제어 코드 ↗](https://github.com/subin11111/ros2-autonomous-control) &nbsp;·&nbsp; [연도별 제어 프로젝트 ↗](PROJECTS.md#team-control)

<a id="awards"></a>

## 03 / Awards & Recognition

| 이력 연도 | 대회·프로그램 | 결과 |
| :--- | :--- | :--- |
| **2026** | [국민대학교 자율주행 경진대회](https://github.com/subin11111/kookmin_autonomous_competition_teamKAI) | **특별상** |
| **2025** | 대학생 창작 모빌리티 경진대회 · 자작자율차 부문 | **창작기술 우수상 · 1위** |
| **2025** | 대학생 창작 모빌리티 경진대회 · 자작자율차 부문 | **자율주행성능 특별상** |
| **2025** | 건국대학교 창의설계경진대회 | **장려상 · 공학교육혁신센터장상** |
| **2025** | 2024 건국대학교 꿈(KU:Maker) 메이커 아이디어 공모전 | **최우수상 · 1위** |
| **2025** | 현대모비스 우수 SW동아리 | **Team K.A.I. 선정** |
| **2025** | 건국대학교 창의융합 캡스톤디자인 | **팀 선정** |

<sub>팀 수상·선정에는 Team K.A.I. 구성원으로 참여했습니다. KU:Maker는 대회명에 포함된 2024와 별도로, 수상 이력을 2025에 기록했습니다.</sub>

<p align="center">
  <img src="assets/team-kai-awards-2025.png" width="100%" alt="2025 대학생 창작 모빌리티 경진대회에서 우수상과 특별상을 수상한 Team K.A.I. 팀원들과 차량">
  <br>
  <sub><b>2025 대학생 창작 모빌리티 경진대회</b> · Team K.A.I.<br>창작기술 우수상 · 자율주행성능 특별상</sub>
</p>

<a id="related-projects"></a>

## 04 / Robotics & Mapping

### Autonomous Driving Platform — 인식에서 MCU 명령까지

YOLOPv2 기반 차선 인식, 주행 명령 생성, MCU 시리얼 브리지를 연결한 ROS 2 통합 프로젝트입니다. 속도·조향각·주행 상태를 명령으로 전달하고, E-stop과 입력 timeout 시 정지 처리를 구성했습니다. 모의 시리얼 bringup으로 인식 → 판단·제어 → MCU 경로를 점검합니다.

`ROS 2` `Python` `YOLOPv2` `Serial` &nbsp;·&nbsp; [코드 ↗](https://github.com/subin11111/autonomous-driving-platform) &nbsp;·&nbsp; [상세 ↗](PROJECTS.md#autonomous-platform)

### UAV × UGV — 협업 시뮬레이션

PX4·Gazebo와 ROS 2를 연결해 지상 주행·비행·탐색·착륙 미션을 실험했습니다. UAV·UGV 명령 경로를 분리하고 센서·TF 브리지, ArUco 기반 착륙 정렬과 미션 전환을 구현했습니다. 제공된 PX4/ASP 환경을 바탕으로 수정·확장한 프로젝트입니다.

`PX4 SITL` `Gazebo` `ROS 2` `Python` `C++` &nbsp;·&nbsp; [ROS 2 코드 ↗](https://github.com/subin11111/asp_ws) &nbsp;·&nbsp; [시뮬레이터 ↗](https://github.com/subin11111/asp/tree/jsb)

### Folded City — 공간을 잇는 지도

iPhone RGB·LiDAR 깊이·ARKit 포즈에서 실내외 공간을 복원하고, 여러 촬영본의 연결과 보행 경로를 연구합니다. 건국대학교 제1학생회관의 실외 접근로·로비·계단·2층을 연결해 3D 지도와 사진 길안내로 구현했습니다.

`RGB-D SLAM` `OpenCV` `Open3D` `ROS 2` `Three.js` &nbsp;·&nbsp; [연구·코드 ↗](https://github.com/subin11111/folded-city-atlas-public) &nbsp;·&nbsp; [웹 지도 ↗](https://folded-city-atlas.vercel.app/)

<a id="research"></a>

## 05 / Research & Side Projects

### ADP LAB — 2026 동계 인턴

**건국대학교 문창주 교수님 연구실 · Bike Anomaly**

이상 탐지·조기 경보를 주제로 비지도 학습, ML·DL 및 표 형식·시계열 입력을 비교·정리한 연구실 인턴 프로젝트입니다. 저장소와 데이터는 비공개이며 프로젝트 개요를 소개합니다.

### Side Projects

| 프로젝트 | 내용 | 링크 |
| :--- | :--- | :--- |
| **Life Map Diary** | 전국 읍면동별 일상·사진 기록과 통계를 쌓는 개인 지도 서비스 | [코드](https://github.com/subin11111/travel-map-diary) |
| **GOBBLEFIN** | 물고기를 먹고 성장하는 Canvas 기반 실시간 경쟁 웹 아케이드 | [코드](https://github.com/subin11111/gobblefin) · [플레이](https://gobblefin-reef-arena.hazy-skink-6279.chatgpt.site) |

[전체 프로젝트와 기술 상세 보기 ↗](PROJECTS.md)

<a id="experience"></a>

## 06 / Experience & Activities

<details open>
<summary><b>2026 · Project management & autonomous systems</b></summary>

- 건국대학교 Team K.A.I. 자율주행 **PM**
- 건국대학교 **ADP LAB 동계 인턴** — 문창주 교수님 연구실 · Bike Anomaly 이상 탐지·조기 경보 프로젝트
- **[국민대학교 자율주행 경진대회 특별상](https://github.com/subin11111/kookmin_autonomous_competition_teamKAI)** — Xycar 통합 주행 팀 프로젝트
- 대학생 AI·SW 모빌리티 경진대회 자작자율차 부문 관련 활동
- **Folded City** — 건국대학교 학술공모전 성(誠) 분야, 실내외 지도·경로 탐색 연구

</details>

<details>
<summary><b>2025 · Vehicle control & team operations</b></summary>

- 건국대학교 Team K.A.I. 자율주행팀 **회장단 총무 · 제어파트**
- **현대모비스 우수 SW동아리 Team K.A.I. 선정**
- **2024 건국대학교 꿈(KU:Maker) 메이커 아이디어 공모전 최우수상 · 1위**
- 건국대학교 **창의융합 캡스톤디자인팀 선정**
- 건국대학교 **창의설계경진대회 장려상 · 공학교육혁신센터장상**
- KASE 대학생 e-스마트 모빌리티 경진대회 참가
- 대학생 창작 모빌리티 경진대회 자작자율차 부문 **창작기술 우수상 · 1위**
- 같은 대회 **자율주행성능 특별상**
- 건국대학교 학생복지위원회 **‘여정’ 대외협력국 국원**
- 학생복지위원회 **2025학년도 1학기 복지장학금 TF팀**

</details>

<details>
<summary><b>2024 · The beginning</b></summary>

- **건국대학교 스마트운행체공학과 정시 입학**
- 건국대학교 Team K.A.I. 자율주행팀 **제어파트 파트원**
- 전국 대학생 창작 모빌리티 경진대회 **자작자율차 부문 참가**
- 제8회 공군참모총장배 드론 종합경진대회 **드론클래쉬 기체제작 아이디어 발표회 참가**
- 같은 대회 **드론클래쉬 챔피언쉽 ROKAF 참가**
- KU융합과학기술원 제8대 학생회 **‘에이트’ 대외협력국 국원**
- KU융합과학기술원 체육대회 **‘KIT LAND’ 진행**
- KU융합과학기술원 축제 **‘KITEUK KITEUK’ 진행**

</details>

## 07 / Toolbox

| 분야 | 사용 기술 |
| :--- | :--- |
| **Control & Embedded** | C / C++ · Python · STM32 · Arduino · micro-ROS · CAN · UART |
| **Robotics & Simulation** | ROS 2 · Gazebo · PX4 · SITL / HIL · RViz · Foxglove |
| **Mapping & Vision** | RGB-D · OpenCV · Open3D · NumPy · SciPy · PyTorch |
| **Web & Visualization** | TypeScript · React · Next.js · Three.js · MapLibre · Supabase |

---

<p align="center">
  <sub><b>Build it. Connect it. Test it.</b><br>subin11111 · Konkuk University · Team K.A.I.</sub>
</p>
