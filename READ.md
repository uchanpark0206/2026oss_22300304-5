CRUD Service

구현한 서비스 주제

사용하는 데이터 Field
label,input,button,button[reset]

Create / Read / Update / Delete 구현 방법

create: form으로 만든 input에 내용을 넣고 추가 버튼을 누르면 새로운 tr이 생성되고 tr의 자손인 td을 생성하고 각각의 요소들을 생성된 td에 넣음 

read:화면 아래에 기본에 나와야 하는 내용을 표시하함. 추가에서 새롭게 tr과 td를 형성하여 버튼을 누르면 자동으로 보임

update:가장 어려웠던 부분(어려워서 가장 나중에 함)수정을 누르면 수정을 누른 테이블의 값들이 input에 들어가게 되고 input에서 수정을 누르면 교체함.이과정에서 수정과 추가를 구분하기 위해 변수newdata을 null로 설정하고 edit함수에 들어가면 수정버튼의 부모(tr)의 부모(table)이 저장이됨. add버튼이 눌릴고 만약 newdata가 비어있으면 그대로 추가 하게하고 만약에 newdata에 내용이 들어 있다면 그건 수정버튼을 들어갔다는 의미이니 교체해주고 다음번에도 추가인지 수정인지 알아얗니까 newdata를 다시 null로 설정해주는 코드를 통해 문제를 해결함

edit함수에 을 만들고 추가 버튼이 눌리고 만약에 eidt함수에 들어가면 edit함수에서 newdata에 값을 주었기 때문에 

delete:교수님과의 지난 수없에서 과일 없애는 것을 거의 그대로 반영함. id는 표에 따로 기제하지 않아서 변수count를 통해 수정함 



querySelector():보통 document.querySelector("#bt1")와 같은 형식으로 많이 사용. 활호안의 내용(html의 아이디)을 선택함
document>>js에서 받아 들이수 있게 변환함 




addEventListener(a,b)
a라는 이벤트가 발생하면,b를 수행하라는 의미>>if를 사용안해도 됨



createElement()새로운 요소를 만듦

appendChild() 자식 요소를 추가해주는 함수


Array 여러 요소들이 들어있는 데이터 덩어리


render():직접 만든 함수로 id를 삭제할때 기존에 내장된 테이블을 삭제하면 아래의 내용의들의 아이디가 그대로 변홛이 안되는 문제를 보안하기 위해 ,테이블안에 tr이라는 요소를 전부 찾아주는 table.querySelectorAll("tr")을 이용해서 번호를 전부 -1해줌 

 remove(e)삭제하는 기능(지난 수업식간의 과일을 응용함)

 해당 요소의 부모의부모를 타겟으로 .remove()를 통해 삭제함

 edit(e) 수정버튼이 눌린 상태인걸 컴퓨터가 인지학 위해 수정버튼의 부모의 부모인 테이블 전체를 newdata에 넣음

 .querySelectorAll 조건에 맞는 요소를 전부 찾는 함수

 .parentElement요소의 부모를 찾아줌
 
 .children요소의 자식을 찾아줌

 add.addEventListener("click", function (){})코드의 핵심. 추가 버튼이 눌리면 설정된 함수가 실해되도록 하는 함수


 사용한 AI 또는 검색 도구:재미나이, 클로드


어떤 문제를 해결하기 위해 사용했는지
1. 코드를 직접 짜보고 오류가 났을 때 오류를 밝히기 위해 가장 많이 씀
2. 도저히 로직이 생각이 안날떄 로직을 어떻게 구현해야 할까를 물어봄


실제 코드에 어떻게 적용했는지
코드에 적용사례
1. function render()>>기존 테이블에서 첫번 째 내용을 삭제 하면 뒤에 있는 2번 내용의 id가 그대로 2가 되었고 이를 해결하기 위한 로직을 ai에세 자문함
2. 수정과 삭제 버튼을 하나의 버튼으로 구현 하는 로직이 떠오르지 않아서 자문해서 조언을 바탕으로 직접 코딩함.

새롭게 이해한 내용
1. array를 선언할때는 대괄호를 써야함
2. 지역함수와 전역함수의 개념과 쓰임을 알게됨
3. .parentElement와 .children을 이해함
4. appendChild() 함수를 이해함
5. querySelectorAll()을 이해함
