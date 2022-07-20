# 윈도우 서버 장치 이름 변경 방법

---

윈도우 서버 1x대의 NIC 구성 정보 중 '이름'과 '장치 이름'이 상이하여 '장치 이름'을 '이름'과 동일하게 변경하는 작업이 있었다.

(실제 케이블은 '이름'과 매칭되어있는 것을 확인하여 장치 이름만 변경을 원함.)

해당 작업의 테스트를 진행해보겠다.

![%EC%BA%A1%EC%B2%98_7](https://user-images.githubusercontent.com/84123877/179883316-e8f8201e-1fac-4ecb-9a8c-82a20033172a.png)

해당 장치명 (Fortinet Virtual Ethernet Adapter (NDIS 6.30) 변경을 시작하겠다.

![%EC%BA%A1%EC%B2%98_1](https://user-images.githubusercontent.com/84123877/179883298-2a4d4cc8-d6b6-43bb-a26f-61ae5154cf86.png)

변경할 장치 우클릭 -> 속성 -> 자세히

속성을 드라이버 키로 맞춘 뒤, 아래의 값 코드를 복사한다.


![%EC%BA%A1%EC%B2%98_2](https://user-images.githubusercontent.com/84123877/179883303-084d38b6-12fa-4b30-878b-52a8b1fa8b74.png)

윈도우 + R (실행창) -> regedit을 입력하여 레지스트리 편집기를 실행한다.

![%EC%BA%A1%EC%B2%98_3](https://user-images.githubusercontent.com/84123877/179883305-43975618-216c-41cc-b077-13fb3e961929.png)

레지스트리 편집기에서 다음 경로로 이동한다.

```bash
HKEY_LOCAL_MACHINE > SYSTEM
```

해당 경로에서 Ctrl + F (찾기 창)을 실행한다.

찾을 내용에 복사해둔 장치 드라이버 코드값을 입력한다.

![%EC%BA%A1%EC%B2%98_4](https://user-images.githubusercontent.com/84123877/179883308-df43ea71-b4b0-44c9-b76a-4df58e374e45.png)

검색 후 장치를 찾을 수 있다.

해당 코드는 Driver에 데이터로 입력되어 있다.

FriendlyName을 더블클릭하여 데이터 값을 변경한다.

![%EC%BA%A1%EC%B2%98_5](https://user-images.githubusercontent.com/84123877/179883311-eaedf785-7cbd-42f2-9eba-280a315a85f4.png)

원하는 문구로 수정한다. 확인 -> 저장 후 변경을 확인해보겠다.

![%EC%BA%A1%EC%B2%98_6](https://user-images.githubusercontent.com/84123877/179883314-330bd140-8bf4-4af0-b943-f4b90145f321.png)

원하는 장치 명칭으로 정상 출력됨을 확인할 수 있습니다.

해당 작업 뿐만 아니라

장치를 추가, 장착을 진행할 때 과거에 장착하였던 이름으로 나타나거나 하는 등 실제로 이름 변경이 필요할 경우가 있는데 (레지스트리 오류일 가능성이 높다)
이처럼 수동으로 이름만 변경하는 작업을 알아두면 유용할 것이다.

---
