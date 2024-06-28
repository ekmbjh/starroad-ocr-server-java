# 서비스 내용 
소비자를 위한 OCR 영수증 기반의 오프라인 종합 쇼핑몰 리뷰 서비스입니다. 우리만의 ‘Reward’를 제공하여 소비자에게 리뷰 작성을 독려하고, 이를 통해 축적된 리뷰 데이터를 총 관리자가 분석할 수 있도록 합니다. 이로써 소비자와 쇼핑몰 간의 신뢰도를 높일 수 있습니다.

---

# 프로젝트 목적 
- **방문객의 소비패턴 파악**
- **방문객들을의 소비활동에 도움을 주는 리뷰커뮤니티 구성 및 독자적 리워드 구현**
- **가공가능한 리뷰데이터 수집**
- **새로운 방식의 복합쇼핑몰 APP 구현**

---
# 프로젝트수상내역

<details>
  <summary>상장 및 사진</summary>
 
![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2F37538f2e-39f1-41bd-bb70-9ff4d076e3a4%2FUntitled.jpeg?table=block&id=43afec34-c15d-4a2e-81bd-8184f304196b&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)

![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2Febff8e1d-6b6c-4d36-9370-f62c953537a9%2FKakaoTalk_20240608_174034719_04.jpg?table=block&id=d30157bc-ce1a-4b82-a61f-5158ebfb740b&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)

</details>

---

# 팀구성 

| 이름 |                                                                      업무 |
| --- | --- |
| 이한강  | 리워드페이지 기능 담당, CI/CD환경 배포,Front-end 개발환경 구성  |
| 양성준  | 관리자페이지 기능 담당, NCP환경구성, ERD설계, Back-end 개발환경 구성  |
| 최문석  | 매장안내,매장리뷰페이지기능 담당, 기획안작성, 최종 발표담당  |
| 백정훈  | 리뷰, 리뷰커뮤니티페이지기능 담당, 이용약관 관련 자료조사, 리뷰API 분석 |
| 이수연  | 마이페이지 기능 담당, 타당성 검증 자료 조사, 주요 문서 작성  |
<br>

---

# 프로젝트 GitFlow 브랜치 전략 가이드

 우리 프로젝트에서 GitFlow 브랜치 전략을 어떻게 구현하고 사용해야 하는지에 대한 상세한 지침을 제공합니다. 모든 팀원은 이 가이드를 따라 일관된 브랜치 관리와 협업을 수행.

<details>
  <summary>주요 가이드라인</summary>
  <ul>
    <li>모든 커밋메시지 앞에는 issue 넘버를 붙인다</li>
    <li>tag에 붙이는 버전은 1.0.0으로 통일한다 (추후 수정 필요하면 공지할 예정)</li>
    <li>커밋메세지는 영어로 통일</li>
  </ul>
</details>

<details>
  <summary>브랜치 구조 및 용도</summary>
  <h4>1. main</h4>
  <p>목적: 안정적인 릴리즈 버전 유지.</p>
  <p>사용: 릴리즈된 버전의 코드 저장소. 최종 사용자에게 배포되는 코드.</p>
  
  <h4>2. develop</h4>
  <p>목적: 다음 릴리즈 준비를 위한 개발 진행.</p>
  <p>사용: 모든 개발이 이루어지는 기본 브랜치. 이곳에서 분기된 feature 브랜치가 병합되고, 준비된 코드는 release 브랜치로 이동.</p>
  
  <h4>3. feature</h4>
  <p>목적: 새 기능 개발, 기존 기능의 개선 및 버그 수정.</p>
  <p>사용: develop 브랜치에서 분기하여 사용. 각 기능 또는 버그 수정에 대해 별도의 브랜치를 생성.</p>
  
  <h4>4. release</h4>
  <p>목적: 다음 버전 릴리즈 준비.</p>
  <p>사용: 릴리즈를 앞두고 최종 테스트와 버그 수정을 위해 사용. develop 브랜치에서 분기하며, 완료 후 main으로 병합 및 태그 지정.</p>
  
  <h4>5. hotfix</h4>
  <p>목적: 릴리즈된 버전에서 발견된 긴급한 문제 해결.</p>
  <p>사용: main 브랜치에서 직접 분기하여 긴급 수정 후 main과 develop에 병합.</p>
</details>

<details>
  <summary>상세 작업 절차</summary>
  
  <h4>새 기능 개발</h4>
  <ol>
    <li>브랜치 생성:
      <pre>
      <code>
      git checkout develop
      git pull origin develop
      git checkout -b feature/기능명
      </code>
      </pre>
    </li>
    <li>개발 작업 수행 후 커밋:
      <pre>
      <code>
      git add .
      git commit -m "새 기능: 기능명에 대한 설명"
      </code>
      </pre>
    </li>
    <li>개발 브랜치로 병합 요청 (Pull Request):
      <ul>
        <li>develop 브랜치로 Pull Request 생성.</li>
        <li>동료의 코드 리뷰 후 병합 승인.</li>
      </ul>
    </li>
  </ol>
  
  <h4>릴리즈 준비</h4>
  <ol>
    <li>릴리즈 브랜치 생성 및 준비:
      <pre>
      <code>
      git checkout develop
      git pull origin develop
      git checkout -b release/버전
      </code>
      </pre>
    </li>
    <li>릴리즈 최종 확인 및 버그 수정:
      <ul>
        <li>모든 팀원이 테스트 참여.</li>
        <li>필요한 모든 수정 사항 커밋.</li>
      </ul>
    </li>
    <li>릴리즈 완료:
      <pre>
      <code>
      git checkout main
      git merge release/버전
      git tag -a v버전 -m "릴리즈 버전 메시지"
      git push origin main --tags
      git checkout develop
      git merge release/버전
      git push origin develop
      </code>
      </pre>
    </li>
  </ol>

  <h4>긴급 수정 (Hotfix)</h4>
  <ol>
    <li>Hotfix 브랜치 생성:
      <pre>
      <code>
      git checkout main
      git pull origin main
      git checkout -b hotfix/버그명
      </code>
      </pre>
    </li>
    <li>버그 수정 및 커밋:
      <pre>
      <code>
      git add .
      git commit -m "긴급 수정: 버그명에 대한 설명"
      </code>
      </pre>
    </li>
    <li>병합 및 배포:
      <pre>
      <code>
      git checkout main
      git merge hotfix/버그명
      git tag -a v버전 -m "Hotfix 버전 메시지"
      git push origin main --tags
      git checkout develop
      git merge hotfix/버그명
      git push origin develop
      </code>
      </pre>
    </li>
  </ol>
</details>

---


# 사용기술 

![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2F4e0a7cb9-abac-453c-b269-1a37db17aee4%2FUntitled.png?table=block&id=0946f46a-3bf7-45a9-8914-8af04b380b54&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)

---

# 자료조사 

![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2Fdf2d2dba-6e98-49f1-879b-7abc03b55b55%2FUntitled.png?table=block&id=5f6bab71-5641-48a1-acf8-ef1a21e08fac&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)
![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2F7ef98afc-ca8d-4663-a4c3-0b901283c855%2FUntitled.png?table=block&id=ca47a10a-94ad-4687-8850-39ec8eb64444&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)
![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2F4e86eacb-b74c-4e0f-bd23-13325c16702f%2FUntitled.png?table=block&id=de23fdbb-78b2-4128-80a5-56f66a04a3d3&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)
![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2Fa9f76acf-5f51-48e7-a801-0c4ff9780030%2FUntitled.png?table=block&id=175614b1-5466-4bcc-b84a-30b53cce9c6e&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)

---

# 아키텍쳐

![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2Fd536ccc6-3603-496e-a7eb-2cf3760583fa%2FUntitled.png?table=block&id=fa19f67d-0658-4de9-b133-39c03d4ca7c7&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)

---

# 와이어프레임

![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2F8e3fc1a9-317a-4486-bfbb-61e2c6900d68%2FUntitled.png?table=block&id=88dbd0d0-5d8e-4395-a209-09e5c5faacb1&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)

![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2F5956ddea-7e63-441d-8d53-f8cb9065d04c%2FUntitled.png?table=block&id=c1b483d8-acb0-4dea-9d67-35b55327f60e&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)

![image](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F9b24aa1b-e37f-4565-bd62-03cc8d1211e0%2Fb466d9b0-bb7f-4839-9e2d-6b126ea11606%2FUntitled.png?table=block&id=84c617b3-72d5-4336-ae08-876438b63396&spaceId=9b24aa1b-e37f-4565-bd62-03cc8d1211e0&width=2000&userId=024cbccc-ee2f-4121-8d15-2dd8d2dd8fee&cache=v2)

# 발표PPT
[PPT](https://docs.google.com/presentation/d/15jBGhfXzDKmBdaqsN46k2byoeTjkDXj_mHOzt9skdnc/edit#slide=id.p1)

---
# 시연영상 
[YouTube시연영상](https://www.youtube.com/watch?v=bi1SdyvLHHY)

---

# 회고

## 주제선정부터 개발까지
미리 정해져 있는 주제가 아닌 주제선정부터 회의를 통해 실현 가능성이 있는 사업성이 있는 프로젝트를 진행해보자는 말이 나왔었고 이렇게 작업을 하는게 처음이였다.
  그러다 보니 기획의 타당성을 놓칠수 없었다. 명확한 근거가 있었어야 했고 그 근거를 토대로 기능을 구현해야 했기 때문이다. 그리고 문서는 제2의 언어라고 느껴질 정도로 우리는 문서화를 신경써서 작업했다. 모든 팀원이 작업하는 내용을 문서화하며 서로 공유했고, 그러다 보니 시간을 절약할 수 있었다. 좋은 팀원들과 함께 했었기에 가능한 부분이라고 생각하고 감사하게 생각한다.
  그리고 한번도 적용해보지 않은 REST API 전송, Vue를 사용하였기에 axios를 활용한 비동기 처리로 데이터를 렌더링 하는 부분들이 처음엔 낯설었지만 코드를 구현하다보니 익숙해졌고, 예상치 못한 오류를 수정하면서 개발을 진행하는 과정이 나에게 흥미로웠다.

## 더 공부할 필요가 있는 부분 
배포부분에 있어 더 공부할 필요가 있다고 느껴졌다. 우리는 CI/CD를 통해서 배포했지만 아직 나에게 익숙하지않고 명확하게 어떤로직으로 구현되는지 확실히 내가 안다고 장담할 수 없었다. 
배포를 담당하는 팀원이 배포를 했기 때문에 설명을 듣고 이해하는 단계였다. 이것은 내가 안다고 할 수 없었고, 그렇기에 더 파고들어야 한다는 필요성을 느꼈다. 
그리고 프론트와 백을 직접 모두 구현을 하면서 느꼈던 건 개발자는 이분법적으로 백과 프론트를 나누는것이 아니라 둘 다 확실하게 로직을 알고 구현을 할 줄아는 개발자가 되는것이 더 차별성이 있고 좋은 개발자가 될 수 있는 밑거름이라는 생각이 들었다. 그래서 이제 리액트와 LLM, 파이썬언어에 좀 관심이 생겼다. 내가 모르는 부분들에 대한 호기심이 원래 많았고 잘하고 싶은 욕심이 있었기에 빨리 익혀서 구현을 하고 사용해보고 싶다. 






