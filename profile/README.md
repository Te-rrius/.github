# 🎾 테리우스 (Terrius)

> **당신의 모든 랠리를 데이터로 기록합니다.**
>
> _"인생네컷처럼 기록하고, 프로 선수처럼 분석받는다."_

코트에 설치된 카메라로 촬영된 테니스 경기 영상을 **하이라이트 클립**으로 남기는 것을 넘어,
**자세 분석 · 경기 분석 데이터 리포트**까지 제공하는 테니스 성장 리포트 서비스입니다.

---

## 🗂️ 레포지토리

| 레포                                                | 설명              | 기술 스택                           |
| --------------------------------------------------- | ----------------- | ----------------------------------- |
| [Terrius-FE](https://github.com/terrius/Terrius-FE) | 모바일 앱         | Expo · React Native · TypeScript    |
| [Terrius-BE](https://github.com/terrius/Terrius-BE) | 백엔드 API 서버   | Spring Boot · Java 21               |
| [Terrius-AI](https://github.com/terrius/Terrius-AI) | AI 영상 분석 서버 | FastAPI · Python · YOLO · MediaPipe |

---

## ✨ 서비스 소개

사용자가 경기 영상에 리포트를 신청하면 AI 분석 파이프라인이 실행됩니다.
결과는 다음 3단위의 분석 데이터로 앱에서 시각화됩니다.

| 단위                      | 내용                                                                          |
| ------------------------- | ----------------------------------------------------------------------------- |
| 🎯 **경기(Match)**        | 최고 타구 속도, 평균/최대/최소 랠리 횟수, 총 샷 수, 퍼스트/세컨드 서브 성공률 |
| 🎾 **샷(Shot)**           | 샷 종류(서브·포핸드·백핸드·발리·스매시) 자동 태깅, 방향 및 코트 내 착지점     |
| 👤 **자세(Biomechanics)** | 샷별 어깨/척추/허리 회전각, 개선 포인트, 점수                                 |

자세 교정이 필요한 구간의 **하이라이트 영상**도 함께 제공합니다.

---

## 🏗️ 시스템 아키텍처

```
📱 Expo App (iOS / Android)
    │  카카오 로그인 · JWT
    │  경기 영상 재생 · 리포트 시각화
    ▼
🎾 Terrius Backend (Spring Boot)
    │  인증 · 도메인 데이터 · 앱 API
    │
    ├─▶ 🗄️ MySQL         (도메인 데이터)
    ├─▶ 🪣 AWS S3         (영상 · 리포트)
    │
    └─▶ 🤖 Terrius AI (FastAPI)
            │  영상 분석 파이프라인
            │
            ├─▶ 🟡 TrackNetV3       (공 추적)
            ├─▶ 🧍 Ultralytics YOLO (선수 추적)
            ├─▶ 👤 MediaPipe         (자세 분석)
            └─▶ 🎬 하이라이트 클립 생성 · S3 업로드
```

---

## 🚀 기술 스택

### 📱 Frontend

<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" /> <img src="https://img.shields.io/badge/React%20Native-61DAFB?style=flat-square&logo=react&logoColor=black" /> <img src="https://img.shields.io/badge/Expo-000020?style=flat-square&logo=expo&logoColor=white" />
<img src="https://img.shields.io/badge/Expo%20Router-000020?style=flat-square&logo=expo&logoColor=white" /> <img src="https://img.shields.io/badge/TanStack%20Query-FF4154?style=flat-square&logo=reactquery&logoColor=white" /> <img src="https://img.shields.io/badge/Zustand-443E38?style=flat-square&logo=zustand&logoColor=white" /> <img src="https://img.shields.io/badge/Axios-5A29E4?style=flat-square&logo=axios&logoColor=white" /> <img src="https://img.shields.io/badge/Kakao%20Login-FFCD00?style=flat-square&logo=kakao&logoColor=black" />

### 🎾 Backend

<img src="https://img.shields.io/badge/Java%2021-007396?style=flat-square&logo=openjdk&logoColor=white" /> <img src="https://img.shields.io/badge/Spring%20Boot%204.0.3-6DB33F?style=flat-square&logo=springboot&logoColor=white" /> <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white" /> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" /> <img src="https://img.shields.io/badge/AWS%20S3-569A31?style=flat-square&logo=amazons3&logoColor=white" /> <img src="https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white" />

### 🤖 AI

<img src="https://img.shields.io/badge/Python%203.10+-3776AB?style=flat-square&logo=python&logoColor=white" /> <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" /> <img src="https://img.shields.io/badge/Ultralytics%20YOLO-111F68?style=flat-square&logo=yolo&logoColor=white" /> <img src="https://img.shields.io/badge/MediaPipe-0097A7?style=flat-square&logo=google&logoColor=white" /> <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white" /> <img src="https://img.shields.io/badge/TrackNetV3-111111?style=flat-square" />

---

## 👥 팀 구성

<table>
  <tr>
    <td align="center" width="180">
      <a href="https://github.com/a-neey">
        <img src="https://github.com/a-neey.png" width="120" height="120" style="border-radius:50%" /><br/>
        <b>김예나</b>
      </a>
    </td>
    <td align="center" width="180">
      <a href="https://github.com/Jun279">
        <img src="https://github.com/Jun279.png" width="120" height="120" style="border-radius:50%" /><br/>
        <b>박제준</b>
      </a>
    </td>
    <td align="center" width="180">
      <a href="https://github.com/ThreeeJ">
        <img src="https://github.com/ThreeeJ.png" width="120" height="120" style="border-radius:50%" /><br/>
        <b>정종진</b>
      </a>
    </td>
    <td align="center" width="180">
      <a href="https://github.com/oroi2009">
        <img src="https://github.com/oroi2009.png" width="120" height="120" style="border-radius:50%" /><br/>
        <b>천성진</b>
      </a>
    </td>
  </tr>
  <tr>
    <td align="center">Frontend</td>
    <td align="center">AI</td>
    <td align="center">Backend · AI</td>
    <td align="center">Backend</td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/a-neey">@a-neey</a></td>
    <td align="center"><a href="https://github.com/Jun279">@Jun279</a></td>
    <td align="center"><a href="https://github.com/ThreeeJ">@ThreeeJ</a></td>
    <td align="center"><a href="https://github.com/oroi2009">@oroi2009</a></td>
  </tr>
</table>
