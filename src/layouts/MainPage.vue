<template>
  <div style="background-color:#f2f3f8">
    <Header />
    <SideMenu />
    <div id="main">
      <div class="container-fluid">
        <Carousel />
        <Titles />
        <Abrisham :info="info[1]" />
        <div v-for="(item,index) in items" :key="index">
          <Category :info="info[item]" />
        </div>
      </div>
      <Footer />
    </div>
    <go-top :size="40" :bottom="50" fg-color="#cfcedb" bg-color="#ffffff" weight="bold"></go-top>
  </div>
</template>

<script>
import axios from "axios";
import Titles from "../components/Titles.vue";
import Abrisham from "../components/Abrisham.vue";
import Category from "../components/Category.vue";
import Footer from "../components/Footer.vue";
import SideMenu from "../components/SideMenu.vue";
import Carousel from "../components/Carousel.vue";
import Header from "../components/Header.vue";
import GoTop from "@inotom/vue-go-top";

export default {
  name: "MainPage",
  components: {
    Titles,
    Abrisham,
    Category,
    Footer,
    SideMenu,
    Carousel,
    Header,
    GoTop,
  },
  props: {
    msg: String,
  },
  data() {
    return {
      info: null,
      items: [2, 3, 4, 5],
    };
  },
  mounted() {
    axios
      .get("https://alaatv.com/api/v2/home")
      .then((response) => (this.info = response.data.data));
  },
};
</script>

<style>
.sidenav {
  height: 100%;
  width: 0;
  position: fixed;
  z-index: 1;
  top: 0;
  right: 0;
  background-color: #ff9a17;
  overflow-x: hidden;
  transition: 0.5s;
  padding-top: 60px;
}

.sidenav a {
  padding: 8px 8px 8px 32px;
  text-decoration: none;
  font-size: 25px;
  color: #818181;
  display: block;
  transition: 0.3s;
}

.sidenav a:hover {
  color: #f1f1f1;
}

.sidenav .closebtn {
  position: absolute;
  top: 0;
  right: 25px;
  font-size: 36px;
  margin-left: 50px;
}

#main {
  transition: margin-left 0.5s;
  background-color: #f2f3f8;
}

@media screen and (max-height: 450px) {
  .sidenav {
    padding-top: 15px;
  }
  .sidenav a {
    font-size: 18px;
  }
}
</style>
