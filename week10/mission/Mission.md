1. GitHub Actions와 AWS EC2를 이용하여 직접 CI/CD 배포 해보기!
    - 완료
2. EC2를 이용해 배포한 현재 상태에서 Google 로그인이 동작하지 않는 이유를 확인하고 수정해보기.
    - 동작하지 않는 이유
        
        ![image.png](attachment:536edfe1-6fc7-4173-82c1-252d41183a48:image.png)
        
        - 다만, 현재 서버는 내가 지정한 퍼블릭IP에서 진행 중이니 동작 X
    - 수정 방안 1)
        
        ![image.png](attachment:eb5532d1-cc43-4cf6-bf2e-3bba7163bcfe:image.png)
        
        - google 설정 상 불가능
    - 수정 방안 2)
        - 퍼블릭 IP를 도메인을 통해 감싸서 진행
        - 유료…..