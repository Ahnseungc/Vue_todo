<template>
  <div id="app">
    <div class="black-bg" v-if="modal === true">
      <div class="white-bg">
        <h4>상세페이지임</h4>
        <p>상세페이지 내용임</p>
      </div>
    </div>

    <div class="menu">
      <a v-for="a in menu" :key="a">{{ a }}</a>
    </div>
    <div>
      원룸샵
      <h4 @onclick="modal = true">{{ products.prod1.name }} 원룸</h4>
      <p>{{ products.prod1.price }} 만원</p>
      <button @click="increase">허위매물신고</button>
      <span>신고수 : {{ siren[0] }}</span>
    </div>
    <div>
      <h4>{{ products.prod2.name }} 원룸</h4>
      <p>{{ products.prod2.name }} 만원</p>
      <button @click="increase">허위매물신고</button>
      <span>신고수 : {{ siren[1] }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      modal: false,
      siren: [0, 0, 0],
      menu: ["Home", "Shop", "About"],
      products: {
        prod1: {
          name: "역삼동",
          price: 50,
        },
        prod2: {
          name: "천호동",
          price: 50,
        },
        prod3: {
          name: "마포구",
          price: 50,
        },
      },
    };
  },
  methods: {
    increase() {
      this.siren += 1;
    },
  },
  components: {},
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
