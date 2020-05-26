<template>
  <div id="app">
    <ul>
      <li v-for="(item,index) in listData" :key="index">
        <div>{{item.title}}</div>
        <HelloWorld @event="lieva" :star="item.star" :id="item.id"/>
      </li>
    </ul>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",
  data() {
    return {
      listData: [
        { title: 1111111111, id: 1, star: 3 },
        { title: 2222222222, id: 2, star: 5 }
      ]
    };
  },

  methods: {
    lieva(data) {
      console.log("data", data);
      this.listData.forEach(element => {
        if (element.id === data.id) {
          element.star = data.star;
        }
      });
      console.log("this.listData", this.listData);
    }
  },

  components: {
    HelloWorld
  }
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
</style>
