<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h4 :style='스타일'>{{products[0]}}</h4>
    <p>{{price1}} 만원</p>
    <!-- 밑에 데이터 보관함인 return {} 내부에 작성했던 data 를 그대로 HTMl 에 꽂아넣는식으로 사용하고 싶다면
    {{}} 중괄호 두개 안에 내가 등록한 데이터의 이름만 넣어주면 그대로 사용 가능 -->
  </div>

  <div>
    <h4 :style='스타일'>{{products[1]}}</h4>
    <p>{{price2}} 만원</p>
  </div>
  
  <div>
    <h4 :style='스타일'>{{products[2]}}</h4>
    <p>가격은 아무거나</p>
  </div>
</template>




<script>

export default {
  name: 'App',

  data(){//Vue 에서는 data() 부분에서 HTML에 데이터를 꽂아넣을 수 있음 즉 data() 가 데이터 보관함
    return{//data 보관함
      price1:25,
      price2:34,
      name1:'휴아인',
      name2:'더존',
      스타일:'color:red',//스타일 : 'color:red' 와 같이 속성에 대한 부분도 데이터바인딩 할 수 있고, 위에서 사용할때는 :style='스타일'과 같이 사용하면 된다
      products : ['역삼동원룸','천호동원룸','마포구원룸'],
    }
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
  margin-top: 60px;
}
</style>

<!--template 안에 HTML 짜고, script 안에 JS 짜고, style 안에 CSS 짠다-->
