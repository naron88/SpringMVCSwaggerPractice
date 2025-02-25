
## 개요
사용자, 패널, 메세지를 통한 프로젝트입니다.

## 주요 엔드포인트  

### **1. 인증 (Auth API)**
| HTTP Method | URL | 설명 |
|------------|-----------------|------------------|
| `POST` | `/api/auth/login` | 로그인 |

#### **로그인 요청 예제**
```json
POST /api/auth/login
Content-Type: application/json

{
  "username": "testuser",
  "password": "testpassword"
}
```

#### **로그인 응답 예제**
```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "username": "testuser",
  "email": "test@example.com",
  "profileId": "d2f12d42-8b1c-4d2f-a6f7-d6f0941616df",
  "online": true
}
```

---

### **2. 유저 (User API)**
| HTTP Method | URL | 설명 |
|------------|-----------------|------------------|
| `GET` | `/api/users` | 전체 유저 목록 조회 |
| `POST` | `/api/users` | 유저 등록 |
| `PATCH` | `/api/users/{userId}` | 유저 정보 수정 |
| `DELETE` | `/api/users/{userId}` | 유저 삭제 |
| `PATCH` | `/api/users/{userId}/userStatus` | 유저 온라인 상태 업데이트 |

#### **유저 등록 요청 예제**
```json
POST /api/users
Content-Type: multipart/form-data

{
  "userCreateRequest": {
    "username": "newuser",
    "email": "newuser@example.com",
    "password": "securepassword"
  },
  "profile": "<파일 업로드>"
}
```

#### **유저 등록 응답 예제**
```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "username": "newuser",
  "email": "newuser@example.com",
  "profileId": "d2f12d42-8b1c-4d2f-a6f7-d6f0941616df",
  "online": false
}
```

---

### **3. 메시지 (Message API)**
| HTTP Method | URL | 설명 |
|------------|-----------------|------------------|
| `GET` | `/api/messages` | 특정 채널의 메시지 목록 조회 |
| `POST` | `/api/messages` | 메시지 생성 |
| `PATCH` | `/api/messages/{messageId}` | 메시지 수정 |
| `DELETE` | `/api/messages/{messageId}` | 메시지 삭제 |

#### **메시지 생성 요청 예제**
```json
POST /api/messages
Content-Type: multipart/form-data

{
  "messageCreateRequest": {
    "content": "새로운 메시지",
    "channelId": "123e4567-e89b-12d3-a456-426614174000",
    "authorId": "550e8400-e29b-41d4-a716-446655440000"
  },
  "attachments": ["<파일 업로드>"]
}
```

#### **메시지 생성 응답 예제**
```json
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "content": "새로운 메시지",
  "channelId": "123e4567-e89b-12d3-a456-426614174001",
  "authorId": "550e8400-e29b-41d4-a716-446655440000",
  "attachmentIds": ["abcdef12-3456-7890-abcd-ef1234567890"]
}
```

---

### **4. 채널 (Channel API)**
| HTTP Method | URL | 설명 |
|------------|-----------------|------------------|
| `POST` | `/api/channels/public` | 퍼블릭 채널 생성 |
| `POST` | `/api/channels/private` | 프라이빗 채널 생성 |
| `GET` | `/api/channels` | 유저가 참여 중인 채널 목록 조회 |
| `PATCH` | `/api/channels/{channelId}` | 채널 정보 수정 |
| `DELETE` | `/api/channels/{channelId}` | 채널 삭제 |

#### **퍼블릭 채널 생성 요청 예제**
```json
POST /api/channels/public
Content-Type: application/json

{
  "name": "General",
  "description": "공식 채널"
}
```

#### **퍼블릭 채널 생성 응답 예제**
```json
{
  "id": "550e8400-e29b-41d4-a716-446655440001",
  "type": "PUBLIC",
  "name": "General",
  "description": "공식 채널",
  "participantIds": []
}
```
