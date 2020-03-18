<template>
  <v-app-bar app dark>
    <div class="d-flex align-center">
      <v-btn outline depressed href="#" dark>Covid-19 Ethiopia</v-btn>
    </div>

    <v-spacer></v-spacer>
    <div class="hidden-sm-and-down">
      <v-dialog v-model="dialog" width="500">
        <template v-slot:activator="{ on }">
          <v-btn dark outline depressed v-on="on">
            <v-tooltip bottom>
              <template v-slot:activator="{ on: tooltip }">
                <v-btn outline depressed dark v-on="{ ...tooltip, ...menu }">
                  <span class="hidden-md-and-down">Contribute</span>
                  <v-icon>mdi-account-group</v-icon>
                </v-btn>
              </template>
              <span>How To Contribute</span>
            </v-tooltip>
          </v-btn>
        </template>

        <v-card>
          <v-card-title class="headline grey lighten-2" primary-title>Want to Contribute</v-card-title>

          <v-card-text
            class="mt-3"
          >To contribute, use the button below where you will find more information on the ways you can help out!</v-card-text>

          <v-divider></v-divider>

          <v-card-actions>
            <v-spacer></v-spacer>

            <v-btn
              color="primary"
              text
              flat
              outlined
              href="https://github.com/nabiloo19/Covid19-Ethiopia-Links"
              target="_blank"
              @click="dialog = false"
            >Contribute</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>

      <v-menu bottom origin="center center" transition="scale-transition">
        <template v-slot:activator="{ on: menu }">
          <v-tooltip bottom>
            <template v-slot:activator="{ on: tooltip }">
              <v-btn outline depressed dark v-on="{ ...tooltip, ...menu }">
                <span class="mr-2 hidden-md-and-down">Important Links</span>
                <v-icon>mdi-link</v-icon>
              </v-btn>
            </template>
            <span>Important Links</span>
          </v-tooltip>
        </template>
        <v-list rounded>
          <v-subheader>Important Links</v-subheader>
          <v-list-item-group>
            <!-- WHO -->

            <v-list-item
              href="https://www.who.int/emergencies/diseases/novel-coronavirus-2019"
              target="_blank"
            >
              <v-list-item-icon>
                <v-icon>mdi-link</v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>WHO</v-list-item-title>
              </v-list-item-content>
            </v-list-item>

            <!-- COVID DATA -->

           <v-list-item href="https://covid-19.alibabacloud.com/" target="_blank">
              <v-list-item-icon>
                <v-icon>mdi-link</v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>Hand Book</v-list-item-title>
              </v-list-item-content>
            </v-list-item>

            <!-- Ethio Stats -->
            <v-list-item href="https://www.worldofmeters.com/state/ethiopia" target="_blank">
              <v-list-item-icon>
                <v-icon>mdi-link</v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>Ethiopia Stats</v-list-item-title>
              </v-list-item-content>
            </v-list-item>

            <!-- TODO -->
            <!-- 
             <v-list-item
              href="https://www.who.int/emergencies/diseases/novel-coronavirus-2019"
              target="_blank"
            >
              <v-list-item-icon>
                <v-icon>mdi-link</v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>WHO</v-list-item-title>
              </v-list-item-content>
            </v-list-item>-->
          </v-list-item-group>
        </v-list>
      </v-menu>
    </div>
  </v-app-bar>
</template>

<script>
export default {
  name: "Toolbar",

  data: () => ({
    items: [
      {
        title: "WHO",
        icon: mdi - link,
        link: "https://www.who.int/emergencies/diseases/novel-coronavirus-2019"
      },
      {
        title: "Covid Data",
        icon: mdi - link,
        link: "https://ourworldindata.org/coronavirus"
      }
    ],
    dialog: false
  })
};
</script>
