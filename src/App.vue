<template>
  <v-app>
    <Toolbar />
    <v-content>
      <keep-alive>
        <MainPage />
      </keep-alive>
      <BottomNav />
      <!-- <Content /> -->
    </v-content>
  </v-app>
</template>

<script>
// import Content from "./components/Content";
import MainPage from "./components/MainPage";
import Toolbar from "./components/Toolbar";
import BottomNav from "./components/BottomNav";

export default {
  name: "App",

  components: {
    // Content,
    MainPage,
    Toolbar,
    BottomNav
  },

  data: () => ({})
};
</script>
