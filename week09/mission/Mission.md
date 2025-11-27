## 해야할 미션

1. 기존에 사용자의 정보를 하드 코딩 부분 수정
2. 자기 자신의 정보를 수정하는 API 제작
3. 기존 API에 JWT 인증 적용

---

## 1. 사용자 정보 하드코딩 부분 수정

### 기존

- `Bearer access-token-for-user-{id}` 로 access-token 설정 중
- 해당 access-token에 대해 id를 가져오는 로직 보유 중

### 수정

- access-token을 자체적인 토큰 방식말고 jwt를 사용하여 sign진행

### 결과

- isLogin 미들웨어 추가

![image.png](attachment:938376c8-0120-4f2a-b5d9-06f3f9252bd9:image.png)

- 작성자에 대한 올바른 응답

![image.png](attachment:ebf6299d-47db-482e-959f-00c0bdae9209:image.png)

---

## 2. 자기 자신의 정보 수정 API 제작

### 추가

- Method: `POST`
- EndPoint: `/mypage/edit`
- Request Body
    
    ```json
    {
    	"name": "string",
    	"gender": 0     // 0이면 남자, 1이면 여자
    	"birth": "2025-11-25",
    	"address": "string",
    	"subaddr": "string"
    }
    ```
    
- Response Body
    
    ```json
    {
    	"success": true,
    	"code": 200,
    	"message": "사용자 정보가 수정되었습니다",
    	"data": {
    		"userId": 1
    	}
    }
    ```
    

### 결과

![image.png](attachment:e3e8bcb5-ecbb-4473-b9ef-43d9ce3c1671:image.png)

---

## 3. 기존 API들에 JWT 인증 적용

### 기존

- `Bearer access-token-for-user-{id}` 로 access-token 설정 중

### 수정

- access-token을 자체적인 토큰 방식말고 jwt를 사용하여 인증받을 수 있도록 수정

### 결과

- isLogin 미들웨어를 통해 인증

![image.png](attachment:52265ba8-e3f0-443e-b7d3-c4d581bc008f:image.png)