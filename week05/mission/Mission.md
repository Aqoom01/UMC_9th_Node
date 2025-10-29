## ✅ 1-1. 특정 지역에 가게 추가하기 API

### API 명세

### Method & EndPoint

`POST /mypage/addStore`

### Request Header

```json
Authorization: Bearer {access_token}
```

### Request Body

```json
{
	"store": {
		"name": "가게이름",
		"time": "월 12시-20시",
		"address": "서울특별시 노원구 광운로 20"
	},
	"region": 1
}
```

### Response Body

```sql
{
	"success": true
	"code": 200,
	"message": "가게 추가가 완료되었습니다.",
	"data": {
		"storeId": 1
	}
}
```

### 해결

### 서버 로그

![image.png](attachment:3373748b-6711-4aea-b7e2-2e87e30c2d86:image.png)

### DB 저장 결과

![image.png](attachment:d4a16c3d-5d75-406c-8daf-063be86aafe7:image.png)

### Postman 테스트 결과

![image.png](attachment:2b6a7d4c-b528-44fa-b603-7c2ad0da94d2:image.png)

## ✅ **1-2. 가게에 리뷰 추가하기 API**

- 리뷰를 추가하려는 가게가 존재하는지 검증이 필요합니다.

### API 명세

### Method & EndPoint

`POST /review/new`

### Request Header

```json
Authorization: Bearer {access_token}
```

### Request Body

```json
{
	"storeId": 2,
	"text": "string",
	"score": 4,
	"images": [
		"url1",
		"url2"
	]
}
```

### Response Body

```sql
{
	"success": true
	"code": 200,
	"message": "리뷰 작성이 완료되었습니다.",
	"data": {
		"reviewId": 1
	}
}
```

### 해결

### 서버 로그

![image.png](attachment:d23ef77f-8c07-483e-a924-cac617c2aac0:image.png)

### DB 저장 결과

![review 테이블](attachment:5ea0ca16-35b8-479d-b805-9efc97562817:image.png)

review 테이블

![picture 테이블](attachment:0d51efb2-95f9-462e-a001-f19fb17e22a0:image.png)

picture 테이블

![review와 picture 매핑테이블](attachment:f975b7bd-4eac-4a93-896d-a0eaebe3808d:image.png)

review와 picture 매핑테이블

### Postman 테스트 결과

![image.png](attachment:47ee43c9-3a47-48ef-acbd-8902935620b8:image.png)

## ✅ 1-3. 가게에 미션 추가하기 API

- 미션을 추가하려는 가게가 존재하는지 검증이 필요합니다
- 미션을 추가하는 주체가 가게의 주인이 맞는지 확인합니다

### API 명세

### Method & EndPoint

`POST /store/addMission`

### Request Header

```json
Authorization: Bearer {access_token}
```

### Request Body

```json
{
	"storeId": 2,
	"content": "string",
	"point": 100
}
```

### Response Body

```sql
{
	"success": true
	"code": 200,
	"message": "미션 추가가 완료되었습니다.",
	"data": {
		"missionId": 1
	}
}
```

### 해결

### 서버 로그

![image.png](attachment:68012772-8514-4096-880a-b3b0990694f4:image.png)

### DB 저장 결과

![image.png](attachment:00239bc2-3827-4d9f-8bab-c037c8008d80:image.png)

### Postman 테스트 결과

![image.png](attachment:dc2adb03-7f1c-4dda-b17b-939ad0f1946d:image.png)

## ✅ **1-4. 가게의 미션을 도전 중인 미션에 추가(미션 도전하기) API**

- 도전하려는 미션이 이미 도전 중이지는 않은지 검증이 필요합니다.
- 1-3번 API를 구현하지 않은 경우, 1-4번에서는 DB에 미션 정보를 수동으로 기입한 후 진행해야 합니다.

### API 명세

### Method & EndPoint

`POST /mission/challenge`

### Request Header

```json
Authorization: Bearer {access_token}
```

### Request Body

```json
{
	"missionId": 1
}
```

### Response Body

```sql
{
	"success": true
	"code": 200,
	"message": "미션 도전이 완료되었습니다.",
	"data": {
		"mappingId": 1
	}
}
```

### 해결

### 서버 로그

![image.png](attachment:e79da686-19c7-40f3-bb18-2b03ff158e8b:image.png)

### DB 저장 결과

![image.png](attachment:ac8df407-7544-4425-af6a-d21673829b0b:image.png)

### Postman 테스트 결과

![image.png](attachment:f25264c3-b699-435b-be2e-c75be9a220ed:image.png)