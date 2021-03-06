# Match-pet
애완동물 매칭 어플리케이션입니다. 매칭 어플을 생각하다가 애완동물샾이나 유기견 분양 등에도 사용할 수 있을 것 같았고 해외에서도 유사한 어플리케이션이 있는 것을 확인하고 저도 만들어봤습니다. 

- 배포 : https://match-pet.netlify.app/

## 기능
### 데이터 설정
Matching 페이지(기본경로 라우팅) 마운트 시 api를 통해 무료 이미지를 불러오고, 미리 만들어둔 파일에서 이름, 소개를 무작위로 가공해 유저객체를 만듭니다. 이 유저객체 배열을 redux-toolkit state에 저장하고 localStorage와 연계하여 다시 접속하거나 새로고침시에 이전 데이터를 그대로 활용할 수 있도록 했습니다.

### 매칭 하기
생성한 users데이터를 바탕으로 api로 받아온 이미지 src를 통해 이미지를 표시하고 이름과 소개가 나옵니다. 하단의 하트 또는 X표시 버튼으로 매칭 또는 거절 할 수 있습니다.

만약 모든 유저를 매칭 또는 거절 했다면 다시 데이터를 요청해 유저 목록을 추가합니다.
![matching](https://user-images.githubusercontent.com/56039591/172040074-837bba9b-67c2-4da4-bad8-637e9bfbf77c.gif)

### 매치 목록
매칭 하기 페이지에서 매치를 선택한 user들의 목록이 나옵니다. 

매치 취소를 누르면 매치 목록에서 사라집니다.
![matchList](https://user-images.githubusercontent.com/56039591/172040078-f06d5efa-503c-45f3-9855-01c242a40b77.gif)


### 거절 목록
매칭 하기 페이지에서 거절을 선택한 user들의 목록이 나옵니다. 

되돌리기 버튼을 누르면 거절 목록에서 사라지고 유저데이터에 추가되어서 매칭 하기에서 다시 볼 수 있습니다.
![rejectList](https://user-images.githubusercontent.com/56039591/172040086-5dafd842-dc50-4db3-86c0-c8942b2086d8.gif)

---
### 확인 모달
매칭을 취소하거나 거절한 대상을 다시 되돌리고 싶을 때 바로 확인을 거치는 부분을 모달로 구현하여 ConfirmModal을 추가하였습니다.
![modal](https://user-images.githubusercontent.com/56039591/173238899-748c96ad-0161-491c-93e0-3233e3e00364.gif)

## 후기

아쉬웠던 점: 매칭 기능은 생각했지만 막상 디자인이나 구현방식이 감을 잡기가 어려워서 시간을 너무 끌었던 것 같습니다. 좀 더 구현해보고싶었던 기능들이 있었는데 간단한 채팅 기능과 매치 또는 거절 선택 시 애니메이션, 그리고 드래그앤드롭으로 매칭 선택 등 디테일한 부분들이 더 많았지만 손대지 못한 것이 아쉽고 시간이 된다면 해당 기능들을 추가해보고싶습니다.
