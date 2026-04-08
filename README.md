# 🌞 햇살장터 | 전통시장 온라인 플랫폼

> 전통시장의 불편함을 해소하고, 상인과 소비자를 잇는 온라인 장터 서비스

---

## 🖥️ 프로젝트 소개

**햇살장터**는 전통시장 상인과 소비자를 온라인으로 연결하는 플랫폼입니다.
카드 결제 불가, 가격 불투명, 배달 서비스 부재 등 전통시장이 안고 있는 구조적 문제를 온라인 플랫폼으로 해결하고, 전통시장의 활성화를 목표로 기획되었습니다.

---

## 💡 기획 배경

![기획배경](https://github.com/user-attachments/assets/cc9c0495-1042-403a-94cb-f80695b060e7)

---

## ✨ 기대 효과

![기대효과](https://github.com/user-attachments/assets/303dcf3f-04ff-43e9-94e3-c11a34d1eb9d)

---

## 🕰️ 개발 기간

**2025.01.05 ~ 2025.03.03** (약 2달)

---

## 🧑‍🤝‍🧑 팀원 구성

| 이름 | 담당 기능 |
|------|----------|
| **김민중**(팀장) | 일반회원 회원가입 / 로그인, 판매자 회원가입 / 로그인, 마이페이지 |
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

![ERD](https://github.com/user-attachments/assets/50a4a914-6e34-40f7-8ae3-66d6e6dd2357)

---

## 🔥 트러블슈팅
 
### 1. 무한 스크롤 — 바닥 도달 시 중복 요청 발생
 
**문제**
스크롤이 바닥에 도달할 때마다 연속으로 스크롤 이벤트가 발생하면서, 짧은 시간 안에 동일한 API 요청이 여러 번 전송되는 문제가 발생했습니다.
 
**원인**
스크롤 이벤트는 바닥에 닿는 순간 수십 번씩 연속으로 발생하는데, 이전 요청이 완료되기 전에 새로운 요청이 계속 쌓이면서 중복 데이터가 로드되었습니다.
 
**해결**
`setTimeout`을 활용해 스크롤 이벤트 발생 후 일정 시간 동안 추가 요청이 전송되지 않도록 제한하여 중복 요청 문제를 해결했습니다.
 
---
 
### 2. 가게 검색 시 일부 가게가 조회되지 않음
 
**문제**
가게 목록 검색 시, 프로필 사진이 등록되지 않은 가게가 검색 결과에서 누락되는 문제가 발생했습니다.
 
**원인**
`tbl_file_store`, `tbl_file` 테이블을 `JOIN`으로 연결하면, 파일 데이터가 없는 가게는 JOIN 조건을 만족하지 못해 결과에서 아예 제외되었습니다.
 
**Before**
```sql
from tbl_store s
join tbl_category c on s.store_category_id = c.id
join tbl_file_store fs on s.id = fs.store_id
join tbl_file f on f.id = fs.id
```
 
**해결**
`JOIN` → `LEFT JOIN`으로 변경하여 프로필 사진이 없는 가게도 결과에 포함되도록 수정했습니다. 파일 데이터가 없는 경우 파일 관련 컬럼은 `null`로 반환됩니다.
 
**After**
```sql
from tbl_store s
join tbl_category c on s.store_category_id = c.id
left join tbl_file_store fs on s.id = fs.store_id
left join tbl_file f on f.id = fs.id
```

---

## 💬 회고
 
### 📋 기획
첫 프로젝트라 어떤 것을 어떻게 기획해야 할지 몰랐고, 백엔드 개발을 위한 API 경로 설계나 예외 처리에 대한 충분한 논의 없이 개발에 들어가다 보니 실제 구현 단계에서 많은 혼선이 발생했습니다. 이 경험을 통해 **기획은 아무리 해도 모자라지 않을 만큼 중요하다**는 것을 깨달았습니다. 기획이 어느 정도 갖춰져 있으면 개발 중 변경사항이 생겨도 유연하게 대처할 수 있다는 것을 배웠습니다.
 
### 🤝 협업
개발하는 동안에는 협업이 잘 되고 있다고 생각했지만, 막상 발표 때 되짚어보니 팀원들끼리 서로의 진행 상황을 자주 공유하지 않았고, 그로 인해 문제가 발생해도 빠르게 캐치하지 못했습니다. 결국 발표 당일까지 구현하지 못한 기능들이 많아 발표 내용에서 빼야 하는 상황이 발생했습니다. **팀원과의 잦은 소통을 통해 진행 상황을 빠르게 공유하고 동기화하는 것이 얼마나 중요한지** 뼈저리게 배웠습니다.
 
### 👍 좋았던 점
혼자 개발할 때는 모든 기능을 혼자 구현해야 했지만, 팀 단위로 프로젝트를 진행하면 기능을 나눠 훨씬 빠르게 개발할 수 있다는 것을 직접 경험했습니다. 협업의 중요성과 팀 프로젝트의 장점을 몸소 느낄 수 있었던 값진 경험이었습니다.
 
### 👎 아쉬웠던 점
기획과 협업, 두 가지가 가장 아쉬움으로 남았습니다. 기획이 좀 더 꼼꼼하고 구체적이었다면 개발 과정이 훨씬 수월했을 것이라는 생각이 머릿속을 떠나지 않았습니다. 협업 측면에서도 내가 먼저 더 자주 소통했더라면 하는 아쉬움이 남았고, **나 혼자 열심히 한다고 프로젝트가 완성되는 것이 아니라는 것**을 이번 프로젝트를 통해 깊이 느꼈습니다.
