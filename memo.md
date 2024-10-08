<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="utf-8">
    <title>div shadow</title>
  </head>
  <body>
    <div class='box'></div>
  </body>
</html>



.box {
  padding : 30px;
  border : 1px solid black;
  border-radius : 5px;
  background : skyblue;
  box-shadow : 5px 5px;
  margin-left : auto;
  margin-right : auto;
}




span 태그는 display : inline 이라는 스타일 속성을 내포하고 있으며,

display : inline을 가지고 있는 요소는 폭, 높이 등을 단독으로 결정할 수 없습니다

폭, 높이를 주고싶으면 얘를 감싸고 있는 <p>에 주십시오



css파일 사용할 때 
<link href="님들의css파일경로~~" rel="stylesheet">

.profile { font-size : 20px }  /*클래스*/
#special { font-size : 30px } /*아이디*/
p { font-size : 16px } /*태그*/

우선 순위는 '태그 안에 직접 style로' > 아이디 > 클래스 > 태그



일부 스타일은 inherit 됩니다.
다 inherit되는건 아니고 글자와 관련된 스타일들이 주로 inherit 됩니다.  



만들고 싶은 레이아웃 디자인 위에 네모박스를 먼저 그려보고 바깥 네모부터 <div> 써서 구현하면 됩니다.



퍼센트 단위를 쓰면 부모 태그의 몇 퍼센트를 차지하게끔 할지 지정해줄 수 있다. 



display가 block이면 가로행을 전부 차지한다는 뜻이다.



 float 속성으로 가로정렬할 땐

영상처럼 float 박스들을 싸매는 하나의 큰 div 박스를 만들고 폭을 지정해주는게 좋습니다.

그래야 모바일에서 안 흘러넘침

float를 쓰고 나면 항상 clear 속성이 필요합니다.
clear 속성을 사용하면 float 다음에 오는 박스들이 제자리를 찾게 됩니다.

float썼으면 까먹지 말고 항상 넣으시면 됩니다.

--> 박스 가로 배치할 때 float 쓰기




가로로 정렬할 때 float : left 이것만 쓸 수 있는 것은 아닙니다.

display : inline-block을 사용해봅시다.

display 속성만 inline-block으로 조정하면 가로로 배치가 가능합니다.

inline- block은 "내 폭과 높이만큼 자리차지하게 해주세요~" 라는 뜻

간편하지만 <태그> 사이에 스페이스바 공백이 있다면 그대로 보여주기 때문에

가로로 정렬하려면 태그 사이의 공백도 제거해줘야합니다.

이런게 귀찮습니다 float 쓰셈 




HTML태그에 클래스 두개 이상 붙이기
<div class="container text-center"> </div>
띄어쓰기를 하신 다음에 원하는 class를 집어넣으시면 됩니다. 


셀렉터 사용법 1. 공백

<ul class="navbar">
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ul>
.navbar li {
  display : inline-block;
}
위 처럼 공백을 이용해 안에 있는 li 태그인 모든 자손을 선택할 수 있습니다.

- 당연히 스페이스바 다음에 tag 셀렉터 말고 class 셀렉터 id 셀렉터 자유롭게 사용가능합니다. 

- .class .class .class 이런 식으로 무한히 연달아 사용가능합니다



셀렉터 사용법 2. 꺾쇠괄호 > 

<ul class="navbar">
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ul>
.navbar>li {
  display : inline-block;
}
기호를 이용해 .li-inline 바로 밑에있는 자식만 선택할 수 있습니다. 



셀렉터 사용법 3. 더욱 상세히 선택하고 싶다면 

<ul class="navbar">
  <li> <span>안녕</span> </li>
  <li></li>
  <li></li>
  <li></li>
</ul>
.navbar li>span {
  color : red;
}
셀렉터를 그냥 연달아 사용하시면 됩니다. 

위의 예제는

.navbar 안에 있는 모든 li, 그리고 그 안에 있는 모든 직계 자손 span 태그를 선택하고 있습니다. 



읽기만 해도 어떤 스타일을 주는지 알 수 있는 셀렉터가 좋은 셀렉터 사용법입니다. 

 

그리고 셀렉터 4~5개 연달아 작성하면 나중에 파일이 커지면 쓸데없는 버그의 원인일 수 있기 때문에 
셀렉터를 남발하는 것 보다는 하나의 새로운 클래스를 만드는게 훨씬 더 나을 수 있습니다.
재사용가능성, 확장성을 염두에 둔다면 저렇게 쓰면 안됩니다. 




배경관련 CSS 속성들 

.main-background {
  background-image : url(../img/shoes.jpg);
  background-size : cover;
  background-repeat : no-repeat;
  background-position : center;
  background-attachment : fixed;
}
background-size는 px, % 단위도 가능하고

cover는 배경으로 꽉채워주세요

contain은 배경이 짤리지 않게 꽉채워주세요 라는 뜻입니다.

background-attachment는 웹사이트가 스크롤될 때 배경이 신기하게 동작하게 만들고 싶으면 써보도록 합시다. 




배경 두개 겹치기 신공 

.main-background {
  background-image : url(../img/shoes.jpg), url(person.jpg);
}
콤마로 이미지 두개를 첨부하시면 됩니다.

투명도를 지원하는 png 이미지를 사용하면 더 재밌는 디자인을 만들 수 있겠군요




배경에 검은색 틴트 주기 
.main-background {
  background-image: linear-gradient( rgba(0,0,0,0.5), rgba(0,0,0,0.5) ), url(이미지경로~~) ;
 
}
linear-gradient 이건 색이 점진적으로 변하는 gradient를 줄 수 있는 키워드인데

여기에 투명도 0.5의 검은색을 입힌 후에 배경겹치기 스킬을 사용하면 됩니다.





주의해야할 margin 버그 

<div class="배경">
  <p>안에 글씨</p>
</div>
div 박스 안에 p 태그를 사용했습니다.

p 태그에 상단 margin을 주기 위해 margin-top을 주게 되면

div와 p가 동시에 margin-top이 생기게 됩니다. 뭔가 이상합니다.

이 현상은 margin collapse effect 라고 부르는 일종의 버그입니다.

원래 박스들의 테두리가 만나면 margin이 합쳐집니다. (박스가 내부에서 만나든 외부에서 만나든 상관없습니다.)

정확히 말하면

1. 마진을 하나로 합쳐주고

2. 혹여나 둘 다 마진이 있으면 둘 중에 더 큰 마진을 하나만 적용하게 됩니다.
 

그래서 두 박스의 테두리가 겹치지 않도록 해주시면 보다 더 정확한 마진 노가다를 하실 수 있습니다. 

강의 예제에선 부모 박스에 padding을 1px 이렇게 조금 주는 것으로 쉽게 해결 가능합니다.
