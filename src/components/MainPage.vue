<template>
  <v-container class="text-center">
    <div>
      <v-select
        v-model="$i18n.locale"
        :items="langs"
        :item-value="langs"
        label="Choose a Language"
        persistent-hint
        return-object
        single-line
        prepend-inner-icon="mdi-earth"
        filled
        outlined
      ></v-select>

      <!-- <select v-model="$i18n.locale">
        <option v-for="(lang, i) in langs" :key="`Lang${i}`" :value="lang">{{ lang }}</option>
      </select>-->
    </div>

    <v-btn
      class
      rounded
      outlined
      v-on:click="get_from_server"
      :loading="loading"
      color="#4285ef"
    >{{$t('refreshButton')}}</v-btn>

  <!-- <v-text-field v-model="name" type="text" rounded></v-text-field>

  <p>{{name}}</p> -->

    <v-divider class="mt-4"></v-divider>
    <div v-if="loading">
      <v-skeleton-loader
        boilerplate="false"
        type="article"
        tile="true"
        transition="scale-transition"
        class="mx-auto"
      ></v-skeleton-loader>
    </div>

    <div v-else transition="scale-transition">
      <p class="disp font-weight-bold mt-4 text-uppercase">
        #{{$t('lastUpdate')}}:
        <span class="disp font-weight-regular">{{dateNoww}} GMT+3</span>
      </p>

      <h1 class="disp mt-3">
        <v-avatar size="70" class="mr-4">
          <v-img src="@/assets/ethiopia.png"></v-img>
        </v-avatar>
        {{$t('country')}}
         <!-- {{res_data.country}} -->
      </h1>

      <p class="disp font-weight-bold mt-3">
        {{$t('totalCases')}} :
        <span class="disp font-weight-regular">{{res_data.total_case}}</span>
      </p>
      <p class="disp font-weight-bold">
        {{$t('newCases')}} :
        <span class="disp font-weight-regular">{{res_data.new_case}}</span>
      </p>
      <p class="disp font-weight-bold">
        {{$t('totalDeathCases')}} :
        <span class="disp font-weight-regular">{{res_data.total_death}}</span>
      </p>
      <p class="disp font-weight-bold">
        {{$t('newDeathCases')}} :
        <span class="disp font-weight-regular">{{res_data.new_death}}</span>
      </p>
      <p class="disp font-weight-bold">
        {{$t('totalRecoveredCases')}} :
        <span
          class="disp font-weight-regular"
        >{{res_data.total_recovered}}</span>
      </p>

      <p class="disp font-weight-bold">
        {{$t('newRecoveredCases')}} :
        <span
          class="disp font-weight-regular"
        >{{res_data.new_recovered}}</span>
      </p>

      
      <p class="disp font-weight-bold">
        {{$t('activeCases')}} :
        <span class="disp font-weight-regular">{{res_data.active_case}}</span>
      </p>
      <p class="disp font-weight-bold">
        {{$t('seriousCases')}} :
        <span class="disp font-weight-regular">{{res_data.serious_critical}}</span>
      </p>
      <p class="disp font-weight-bold">
        {{$t('totaltests')}} :
        <span class="disp font-weight-regular">{{res_data.total_test}}</span>
      </p>
      <p class="disp font-weight-bold">
        {{$t('totaltestspermillion')}} :
        <span class="disp font-weight-regular">{{res_data.total_test_1_m_pop}}</span>
      </p>
      <p class="disp font-weight-bold">
        {{$t('population')}} :
        <span class="disp font-weight-regular">{{res_data.population}}</span>
      </p>
      <v-divider></v-divider>
      <p class="disp font-weight-bold">
        <v-list rounded disabled>
          <v-list-item-group>
            <v-list-tile-title class="disp font-weight-thin">#{{$t('note')}}</v-list-tile-title>
            <v-list-item>
              <v-list-item-content>
                <p>*{{$t('noteTxt')}}</p>
              </v-list-item-content>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </p>

      
    </div>
  </v-container>
</template>

<script>
import axios from "axios";

export default {
  name: "MainPage",

  data: () => {
    return {
      langs: ["English", "Amharic"],

      res_data: {},
      // name: "",
      res_patients: {},
      loading: false,
      loadingPatient: false,
      timeStamp: "",
      dialog: false
    };
  },
  created() {
    this.get_from_server();
    this.get_patients();
  },
  methods: {
    async get_from_server() {
      this.loading = true;
      const res = await axios.get("https://covids.vercel.app/?country=ethiopia");

      this.dateNoww = new Date().toLocaleString();

      this.res_data = res.data;
      this.loading = false;
    },

    // async get_patients() {
    //   // this.loadingPatient = true;
    //   const res = await axios.get("https://api.pmo.gov.et/v1/patients/");
    //   console.log(res);

    //   // this.dateNoww = new Date().toLocaleString();

    //   this.res_patients = res.data;
    //   // this.loadingPatient = false;
    // },

    // async test() {
    //   var v = this;
    //   setInterval(async function() {
    //     this.loading = true;
    //     const res = await axios.get(
    //       "https://coronavirus-scrapy.herokuapp.com/"
    //     );

    //     this.dateNoww = new Date().toLocaleString();

    //     this.res_data = res.data;
    //     this.loading = false;
    //   }, 3000);
    // },

    callFunction() {
      var currentDate = new Date();

      var test1 = currentDate.toLocaleString();

      this.dateNoww = test1;
    }
  },
  mounted() {
    this.callFunction();
    //this.test();
  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Poppins&display=swap");

.disp {
  font-family: "Poppins", sans-serif;
}
</style>