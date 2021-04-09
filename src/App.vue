<!-- html 영역 -->
<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <!--html 속성 또한 데이터바인딩이 가능하다. style 앞에 ':'을 사용해 준다.-->
    <h3 :style="스타일">원룸샵</h3>
    <h4>{{product[0]}}</h4>    
    <p>{{price1}} 만원</p>
  </div>
  <div>
    <h4>{{product[1]}}</h4>    
    <p>{{price2}} 만원</p>
  </div>
  <div>
    <h4>{{product[2]}}</h4>    
    <p>{{price3}} 만원</p>
  </div>
</template>
<!-- 자바 스크립트 공간 -->
<script>

export default {
  name: 'App',
  data(){
    return{
      /*데이터 보관함:데이터는 object로 받아주자*/
      price1 : 150, price2 : 45, price3 : 65,
      스타일 : 'color:red',
      product : ['역삼동 원룸','천호동 원룸','마포구 원룸'],
    }
  },
  components: {
  }
}
</script>
<!-- CSS 영역 -->
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