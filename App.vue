<template>

  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="모달창열렸니=false">닫기</button>
    </div>
  </div>



  <div class="menu">
    <a v-for="(a,i) in 메뉴들" :key="i">{{a}}</a>
  </div>


  <div>
    <img src="./assets/room0.jpg" class="room-image">
        <h4 @click="모달창열렸니=true">{{products[0]}}</h4>
    <p>{{price1}} 만원</p>
    <p><button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{신고수[0]}}</span></p>
  </div>


  <div>
    <img src="./assets/room1.jpg" class="room-image">
    <h4>{{products[1]}}</h4>
    <p>{{price2}} 만원</p>
    <p><button @click="increase_2nd">허위매물신고</button> <span>신고수 : {{신고수[1]}}</span></p>
  </div>
  
  <div>
    <img src="./assets/room2.jpg" class="room-image">
    <h4>{{products[2]}}</h4>
    <p>{{price3}} 만원</p>
    <p><button @click="신고수[2]++">허위매물신고</button> <span>신고수 : {{신고수[2]}}</span></p>
  </div>
</template>




<script>

export default {
  name: 'App',

  data(){
    return{
      신고수:[0,0,0],
      price1:25,
      price2:34,
      price3:55,
      메뉴들 : ['Home','Shop','About'],
      products : ['역삼동원룸','천호동원룸','마포구원룸'],
      모달창열렸니 : false,
    }
  },
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

body
{
  margin:0
}
div
{
  box-sizing:border-box;
}

.black-bg
{
  width:50%; height:50%;
  background:rgba(0,0,0,0.5);
  position:fixed;padding:20px;
}

.white-bg
{
  width:50%;background:white;
  border-radius: 8px;
  padding:20px;
}


.room-image
{
  width:50%;
  margin-top:40px;
}

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

