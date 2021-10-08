<template>
  <div class="menu">
    <a v-for="(a,i) in 메뉴들" :key="i">{{a}}</a>
    <!-- 반복문 사용시에 v-for을 사용하는데 형태 -> v-for="작명 in 반복횟수" :key="작명" 꼴로 사용한다  -->
    <!-- 즉, 작명과 같이 이름을 작명하고 그에대한 key에 대해서도 작성할것 -->
    <!-- Vue 반복문의 특징 : array/object 를 v-for 다음 반복 횟수 즉 작명 in ??? 부분에 집어넣게 되면 array또는 object 안의 데이터 갯수만큼 반복 -->
    <!-- Vue 반복문의 특징 : v-for="작명" in "메뉴들" :key="작명" 과 같이 입력시에 반복문이 하나씩 돌때마다 메뉴들 안의 하나하나의 데이터로 작명이 바뀐다 -->
    <!-- 따라서 다음과 같이 작성했을때 반복문이 3번 돌면서 Home Shop About 를 순서대로 출력하게된다 -->
    <!-- 보통 Vue 반복문의 형태 : v-for"(a,i) in 메뉴들" :key="i" 로 사용하는데 이 때 왼쪽 변수는 array 내의 데이터(메뉴들의데이터), 오른쪽 변수는 1씩 증가하는 정수(원래 기존 i) -->
  </div>

  


<!-- 아래 와 같이 하드코딩 되어있던 div 3개를 v-for 사용해 하나로 축약
  <div v-for="(a,i) in products" :key="i">
    <h4>{{products[i]}}</h4> 처럼 사용해도 되고, a 라는것 자체가 products 의 데이터들을 가지고 있기 때문에 아래와 같이 사용해도 좋다
    <h4>{{a}}</h4>
    <p>50만원(가격 일단 고정)</p>
  </div> -->

  <div>
    <h4 :style='스타일'>{{products[0]}}</h4>
    <p>{{price1}} 만원</p>
    <!-- 밑에 데이터 보관함인 return {} 내부에 작성했던 data 를 그대로 HTMl 에 꽂아넣는식으로 사용하고 싶다면
    {{}} 중괄호 두개 안에 내가 등록한 데이터의 이름만 넣어주면 그대로 사용 가능 -->
    <p><button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{신고수[0]}}</span></p>
    <!-- <button @mouseover="increase">허위매물신고</button> <span>신고수 : {{신고수}}</span> -->
    <!-- 다양한 button event 사용이 가능하고 이벤트들은 @누르고 컨트롤 + spacebar 로 알 수 있음 -->
  </div>

  <!-- 기존 javascript 에서 사용되던 onclick 이 Vue 에서는 v-on:click"javascript~" 또는 @click"~" 의 형태로 사용되고 
  위와같이 신고수가 증가하는 button을 만들때 @click="신고수++"로 데이터바인딩 시킨 신고수를 1씩 증가시켜주는 형태로 짤 수 있다 -->

  <div>
    <h4 :style='스타일'>{{products[1]}}</h4>
    <p>{{price2}} 만원</p>
    <p><button @click="increase_2nd">허위매물신고</button> <span>신고수 : {{신고수[1]}}</span></p>
  </div>
  
  <div>
    <h4 :style='스타일'>{{products[2]}}</h4>
    <p>{{price3}} 만원</p>
    <p><button @click="신고수[2]++">허위매물신고</button> <span>신고수 : {{신고수[2]}}</span></p>
  </div>
</template>




<script>

export default {
  name: 'App',

  data(){//Vue 에서는 data() 부분에서 HTML에 데이터를 꽂아넣을 수 있음 즉 data() 가 데이터 보관함
    return{//data 보관함
      신고수:[0,0,0],
      price1:25,
      price2:34,
      price3:55,
      name1:'휴아인',
      name2:'더존',
      //스타일:'color:red',//스타일 : 'color:red' 와 같이 속성에 대한 부분도 데이터바인딩 할 수 있고, 위에서 사용할때는 :style='스타일'과 같이 사용하면 된다
      메뉴들 : ['Home','Shop','About'],
      products : ['역삼동원룸','천호동원룸','마포구원룸'],
    }
  },
  //Vue 에서 함수를 만들고 싶을때 methods : {} 안에 만듬
  //함수 만들때 주의사항 --> 함수 안에서 내가 만들어놓은 data 를 쓸 땐 this.데이터명 꼴로 생성
  methods : {
    increase_2nd()
    {
      this.신고수[1] ++;
    },
  },

  components: {
    
  }
}
</script>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu
{
  background:darkslateblue;
  padding:15px;
  border-radius:5px;
}

.menu a{
  color:white;
  padding:20px;
}
</style>


<!--template 안에 HTML 짜고, script 안에 JS 짜고, style 안에 CSS 짠다-->
