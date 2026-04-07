# 🌞 햇살장터 | 전통시장 온라인 플랫폼

> 전통시장의 불편함을 해소하고, 상인과 소비자를 잇는 온라인 장터 서비스

---

## 📋 목차

1. [프로젝트 소개](#-프로젝트-소개)
2. [기획 배경](#-기획-배경)
3. [기대 효과](#-기대-효과)
4. [개발 기간](#-개발-기간)
5. [팀원 구성](#-팀원-구성)
6. [기술 스택](#-기술-스택)
7. [주요 기능](#-주요-기능)
8. [프로젝트 구조](#-프로젝트-구조)
9. [ERD](#-erd)
10. [트러블슈팅](#-트러블슈팅)
11. [회고](#-회고)

---

## 🖥️ 프로젝트 소개

**햇살장터**는 전통시장 상인과 소비자를 온라인으로 연결하는 플랫폼입니다.
카드 결제 불가, 가격 불투명, 배달 서비스 부재 등 전통시장이 안고 있는 구조적 문제를 온라인 플랫폼으로 해결하고, 전통시장의 활성화를 목표로 기획되었습니다.

---

## 💡 기획 배경

현대 소비자들이 전통시장을 기피하는 주요 원인은 다음과 같습니다.

- **결제 불편** : 카드 결제가 되지 않는 점포가 다수
- **배달 플랫폼 경쟁** : 배달 앱 이용 증가로 인한 방문 고객 감소
- **가격 불투명** : 불명확한 가격 표시로 인한 소비자 신뢰 저하
- **부정적 이미지** : 위생·시설 관련 부정적 뉴스 누적

이러한 문제를 해결하기 위해, 전통시장을 온라인화하여 소비자 접근성을 높이고 상인에게는 안정적인 판매 채널을 제공하는 서비스를 기획하였습니다.

---

## ✨ 기대 효과

| 대상 | 기대 효과 |
|------|----------|
| **소비자** | 카드 결제, 배달 서비스 등 편리한 쇼핑 환경 제공 |
| **상인** | 온라인 판로 확보, 가격 투명성 확보로 신뢰도 향상 |
| **전통시장** | 플랫폼을 통한 신규 고객 유입 및 시장 활성화 |

---

## 🕰️ 개발 기간

**2025.01.05 ~ 2025.03.03** (약 2달)

---

## 🧑‍🤝‍🧑 팀원 구성

| 이름 | 담당 기능 |
|------|----------|
| **김민중** | 일반회원 회원가입 / 로그인, 판매자 회원가입 / 로그인, 마이페이지 |
| **이정식** | 가게 페이지(상품 조회·상세·수정, 가게 등록·목록·상세·수정), 장바구니, 결제 |
| **오하은** | 관리자 페이지(회원·가게·상품·신고 관리) |

---

## ⚙️ 기술 스택

### Backend
![Java](https://img.shields.io/badge/Java_17-007396?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot_3.5-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![MyBatis](https://img.shields.io/badge/MyBatis-000000?style=flat-square)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)

### Frontend
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-005F0F?style=flat-square&logo=thymeleaf&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

### Tools & Libraries
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white)
![Lombok](https://img.shields.io/badge/Lombok-CA0000?style=flat-square)
![Thumbnailator](https://img.shields.io/badge/Thumbnailator-0.4.8-blue?style=flat-square)
![Gson](https://img.shields.io/badge/Gson-2.8.6-blue?style=flat-square)

---

## 📌 주요 기능

### 👤 회원 기능
- 일반회원 / 판매자 회원 구분 회원가입 및 로그인
- 마이페이지 — 프로필 편집, 주문 내역 대시보드, 리뷰 작성

### 🏪 가게 & 상품
- 가게 등록, 목록 조회, 상세 페이지
- 상품 등록, 조회, 수정
- 이미지 업로드 (Thumbnailator 썸네일 처리)

### 🛒 장바구니 & 결제
- 상품 장바구니 담기 / 조회 / 삭제
- 결제 처리

### 🔧 관리자
- 회원 관리 (조회 / 수정)
- 가게 관리 (조회 / 수정)
- 상품 관리 (조회 / 수정)
- 신고 내역 관리

---

## 📐 ERD

> 이미지 추가 예정

---

## 🔥 트러블슈팅

> 개발 중 겪었던 문제와 해결 과정을 기록합니다.

---

## 💬 회고

> 프로젝트를 마치며 느낀 점, 배운 점, 개선하고 싶은 점을 기록합니다.
