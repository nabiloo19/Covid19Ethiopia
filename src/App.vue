<template>
  <v-app>
    <Toolbar />

    <v-content>
      <keep-alive>
        <MainPage />
      </keep-alive>
      <BottomNav />
    </v-content>
  </v-app>
</template>

<script>
import MainPage from "./components/MainPage";
import Toolbar from "./components/Toolbar";
import BottomNav from "./components/BottomNav";

export default {
  name: "App",

  components: {
    MainPage,
    Toolbar,
    BottomNav
  },

  data: () => ({
    
  })
};
</script>
