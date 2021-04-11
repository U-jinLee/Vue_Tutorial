<!-- html 영역 -->
<template>
<!-- 모달창 부분 -->
  <!--2. 데이터에 따라 UI가 어떻게 보일지 작성-->
  <div class="black_bg" v-if="modalOpenState === 1">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="modalOpenState =0">닫기</button>
    </div>
  </div>
  <div class="menu">
    <!-- <a>Home</a> <a>Product</a> <a>About</a> -->

    <!--'in 숫자'부분에 숫자에 지정된 배열 데이터 입력 시 배열의 길이만큼 숫자가 지정됨-->
    <!--{{menuvar[0]}}을 입력했을 시 앞글자만 따와서 화면에 출력-->
    <!--key=a 태그를 각각 생성하기 위한 요소-->
    <!--(a,i)로 입력 시 a의 경우 담긴 문자, i는 숫자로써의 역할을 함-->
    <a v-for="(a,i) in menu" :key="i">{{a}}</a>
  </div>

    <h3 :style="스타일">강다방</h3>
  <div v-for="(a,i) in oneRoomData" :key="i">
    <!--html 속성 또한 데이터바인딩이 가능하다. style 앞에 ':'을 사용해 준다.-->
    <!--"'./assets/room'+1+'.jpg/'"-->
    <img :src="oneRoomData[i].image" class="room_img">
    <h4 @click="modalOpenState = 1">{{oneRoomData[i].title}}</h4>    
    <p> {{oneRoomData[i].price}}</p>
    <!-- <button v-on:click="a.reportCount+=1">허위매물 신고</button><span>신고: {{a.reportCount}}</span> -->
  </div>
  <!-- <div>
    <h4>{{product[1]}}</h4>    
    <p>{{price2}} 만원</p>
  </div>
  <div>
    <h4>{{product[2]}}</h4>    
    <p>{{price3}} 만원</p>
  </div> -->
</template>
<!-- 자바 스크립트 공간 -->
<script>
/*작명 이름은 상관이 없음 */
// import apple from './assets/oneRoom.js';
// import {apple, apple2} from './assets/oneRoom.js';
import homeData from './assets/oneRoom.js';

export default {
  name: 'App',
  // data() = state 
  data(){
    return{
      oneRoomData : homeData,
      /*1.UI의 현재 상태를 데이터로 저장 */
      modalOpenState : 0,
      /*데이터 보관함:데이터는 object로 받아주자*/
      roomNum : ["0", "1", "2"],
      price1 : [150, 45, 65],
      스타일 : 'color:black',
      /*data 또다른 활용방법 */
      product : [
        {name:'역삼동 원룸',price: 150, reportCount :0},
        {name:'마포구 원룸',price: 45, reportCount :0},
        {name:'신림동 원룸',price: 65, reportCount :0},
        ],
      menu:['Home','About','Product','You','Me'],
    }
  },
  //함수를 만드는 공간
  methods: {
    // increase() {
    //   this.product.reportCount+=1;
    // }
  },
  components: {
  }
}
</script>
<!-- CSS 영역 -->
<style>
body {
  margin: 0;
}
div{
  box-sizing: border-box;
}

.black_bg{
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
.room_img{
  width: 50%;
  margin-top: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
}
</style>