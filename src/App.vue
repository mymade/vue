<template>
  <div class="wrap">
      <div class="black-bg" v-if="detail == true">
        <div class="white-bg">
        <h4>상세페이지임</h4>
        <p>상세페이지 내용임</p>
        <button @click="detail = false">닫기</button>
      </div>
      </div>

    <nav id="menu">
    <ul>
      <li v-for="(v,i) in menus" :key="i"><a href="#">{{v}}</a></li>
    </ul>
    </nav>
    <div class="box-wrap">
      <div class="item-box">
        <h4>{{원룸들[0].title}}</h4>
        <div class="price">{{원룸들[0].price}}원</div>
        <div class="roomimg">
          <img :src="원룸들[0].image" alt="역삼동 원룸 이미지">
        </div>
        <div class="detail-btn">
          <button @click="detail = true">상세페이지 보기</button>
        </div>
        <div class="btn-box">
          <button @click="신고수[0]++">허위매물신고</button>
          <span>신고수 : {{신고수[0]}}</span>
        </div>
      </div>
      <div class="item-box">
        <h4>{{name[1]}}</h4>
        <div class="price">{{price[1]}}만원</div>
        <div class="roomimg">
          <img src="./assets/room1.jpg" alt="천호동 원룸 이미지">
        </div>
        <div class="btn-box">
          <button @click="신고수[1]++">허위매물신고</button>
          <span>신고수 : {{신고수[1]}}</span>
        </div>
      </div>
      <div class="item-box">
        <h4>{{name[2]}}</h4>
        <div class="price">{{price[2]}}만원</div>
        <div class="roomimg">
          <img src="./assets/room2.jpg" alt="마포구 원룸 이미지">
        </div>
        <div class="btn-box">
          <button @click="신고수[2]++">허위매물신고</button>
          <span>신고수 : {{신고수[2]}}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import oneroom from './db/data.js'
export default {
  name: 'App',
  data(){
    return{
      // all:{
      // clsname:["r-cls1","r-cls2","r-cls3"],
      // menus : ["HOME ", "ABOUT", "SHOP"],
      // name : ["역삼동 원룸","천호동 원룸","마포구 원룸"],
      // price:[50, 60, 70]
      // }
      clsname:["r-cls1","r-cls2","r-cls3"],
      menus : ["HOME ", "ABOUT", "SHOP"],
      name : ["역삼동 원룸","천호동 원룸","마포구 원룸"],
      price:[50, 60, 70],
      신고수: [0,0,0],
      detail:false,
      원룸들 : oneroom
    }
  },
  components: {
  }
}

</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100..900&display=swap');

body{
  font-family: "Noto Sans KR" !important;
  margin: 0;
  width: 100%;
  box-sizing: border-box;
}
ul,li{
  list-style: none;
}
div{
  box-sizing: border-box;
}
a{
  text-decoration: none;
  color: black;
}
.wrap{
  width: 100%;
  height: 100%;
  margin: 0 auto;
  position: relative;
}

.detail-btn button{
  border: none;
  padding: 20px 40px;
  border-radius: 20px;
  font-size: 14pt;
  font-weight: bold;
  cursor: pointer;
  margin-top: 20px;
  transition: 0.3s;
}

.detail-btn button:hover{
  background-color: rgb(255, 180, 19);
  transform: scale(1.05);
}

.black-bg{
  background-color: rgba(0, 0, 0, 0.658);
  position: fixed;
  width: 100%;
  height: 100%;
  padding: 20px;
  z-index: 9999;

}

.white-bg{
  background-color: white;
  border-radius: 8px;
  padding: 20px;
  width: 100%;
  text-align: center;
}

.white-bg h4{
  font-size: 15pt;
  font-weight: bold;
  margin-bottom: 14px;
}

.white-bg button{
  border: none;
  margin-top: 20px;
  padding: 8px 16px;
  background-color: rgb(218, 218, 218);
  color: white;
  border-radius: 4px;
  cursor: pointer;
  transition: 0.3s;
}

.white-bg button:hover{
  background-color: rgb(255, 180, 19);
}

#menu{
  background-color:rgb(255, 180, 19);
  height: 60px;
  border-radius: 4px;
}
#menu li{
  margin-right: 30px;
}
#menu li a{
  color: white;
}
#menu ul{
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.box-wrap{
  margin: 0 auto;
  margin-top: 60px;
}
.box-wrap div{
  text-align: center;
}
.item-box{
  width: 100%;
  /* width: 600px; */
  margin:0 auto;
  padding-top: 60px;
}
.item-box h4{
  font-size: 16pt;
  font-weight: bold;
  margin-bottom: 15px;
}

.item-box .price{
  font-size: 14pt;
}

.item-box .roomimg{
  margin-top: 30px;
  width: 100%;
  border-radius: 20px;
  overflow: hidden;
}

.item-box .roomimg img{
  width: 100%;
}

.btn-box{
  padding: 10px 0;
  background-color: rgb(218, 218, 218);
  width: 300px;
  margin: 0 auto;
  margin-top: 20px;
  border-radius: 6px;
}
.btn-box button{
  margin-right: 20px;
}
/* .box-wrap{
  display:flex;
  justify-content: center;
  margin-top: 30px;
}
.box-wrap > div{
  margin-right: 30px;
} */
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
