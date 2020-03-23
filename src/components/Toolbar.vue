<template>
  <v-app-bar app dark>
    <div class="d-flex align-center">
      <v-btn outline depressed @click.native.stop="$vuetify.goTo('*', options)">{{$t('title')}}</v-btn>
    </div>

    <v-spacer></v-spacer>
    <div class="hidden-sm-and-down">
      <!-- <v-select
        v-model="$i18n.locale"
        :items="langs"
        item-text="state"
        :item-value="lang"
        label="Choose a Language"
        persistent-hint
        return-object
        single-line
        prepend-inner-icon="mdi-earth"
        color="#000"
        filled
        outlined
      ></v-select>-->

      <Content></Content>
    </div>
  </v-app-bar>
</template>

<script>
import Content from "./Content";

export default {
  name: "Toolbar",

  components: {
    Content
  },

  data: () => {
    return {
      langs: ["en", "am"],

      dialog: false,
      options: {
        duration: 750,
        offset: -10,
        easing: "easeInOutCubic"
      }
    };
  }
};
</script>
