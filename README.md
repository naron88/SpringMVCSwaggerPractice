[api-docs.json](https://github.com/user-attachments/files/18902245/api-docs.json)# Swagger로 API 문서 생성 및 간단한 배포

## 1. **개요**
**Spring Boot 기반의 REST API**를 개발하고,  
**Swagger를 활용하여 API 테스트**, 그리고 **Railway를 이용한 배포**까지 구현했습니다.

### **1.1 목표**
- **Spring Boot 3.x**로 API 서버 개발
- **Swagger**로 API 문서화 및 테스트
- **Railway**를 활용한 클라우드 배포
- **JSON File I/O**를 사용해 데이터베이스 활용
---

## 2. **API**
### 2.1 **API 목록**
| API URL | HTTP Method | 설명 |
|--------------|------------|---------------------|
| `/api/auth/login` | `POST` | 사용자 로그인 |
| `/api/users` | `POST` | 새로운 사용자 생성 |
| `/api/users/{id}` | `PATCH` | 사용자 정보 수정 |
| `/api/users/{id}` | `DELETE` | 사용자 삭제 |
| `/api/users` | `GET` | 전체 사용자 목록 조회 |
| `/api/users/{id}/userStatus` | `PATCH` | 사용자 온라인 상태 업데이트 |
| `/api/channels/public` | `POST` | Public 채널 생성 |
| `/api/channels/private` | `POST` | Private 채널 생성 |
| `/api/channels/{id}` | `PATCH` | 채널 정보 수정 |
| `/api/channels/{id}` | `DELETE` | 채널 삭제 |
| `/api/channels` | `GET` | 특정 사용자가 참여한 채널 목록 조회 |
| `/api/messages` | `POST` | 메시지 생성 |
| `/api/messages/{id}` | `PATCH` | 메시지 수정 |
| `/api/messages/{id}` | `DELETE` | 메시지 삭제 |
| `/api/messages` | `GET` | 특정 채널의 메시지 목록 조회 |
| `/api/binaryContents/{binaryContentId}` | `GET` | 특정 첨부 파일 조회 |
| `/api/binaryContents` | `GET` | 여러 첨부 파일 조회 |
| `/api/readStatuses` | `POST` | 메시지 읽음 상태 생성 |
| `/api/readStatuses/{id}` | `PATCH` | 읽음 상태 수정 |
| `/api/readStatuses` | `GET` | 특정 사용자의 읽음 상태 목록 조회 |

### 2.2 **API 상세 파일**

[api-docs.json](https://github.com/user-attachments/files/18902264/api-docs.json)


