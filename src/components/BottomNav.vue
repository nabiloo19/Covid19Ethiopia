<template>
  <v-container>
    <!-- Bottom Navigation -->

    <v-bottom-navigation v-model="bottomNav" fixed grow color="#fff" class="hidden-sm-and-up" dark>
      <v-dialog v-model="dialog" width="500">
        <template v-slot:activator="{ on }">
          <v-btn class="mt-3" outline depressed dark v-on="{...on, ...menu }">
            <span class="mt-2 mb-5">{{$t('nav.contribute')}}</span>
            <v-icon>mdi-account-group</v-icon>
          </v-btn>
        </template>

        <v-card>
          <v-card-title class="headline grey lighten-2" primary-title>{{$t('nav.contributeHeader')}}</v-card-title>

          <v-card-text
            class="mt-3"
          >{{$t('nav.contributeTxt')}}</v-card-text>

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
            >{{$t('nav.contributeButton')}}</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>

      <v-menu bottom origin="center center" transition="scale-transition">
        <template v-slot:activator="{ on: menu }">
          <v-btn class="mt-3" v-on="{ ...menu }">
            <span class="mt-2 mb-5">{{$t('nav.importantLinks')}}</span>
            <v-icon>mdi-link</v-icon>
          </v-btn>
        </template>
        <v-list rounded>
          <v-subheader>{{$t('nav.importantLinks')}}</v-subheader>
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
    </v-bottom-navigation>
  </v-container>
</template>

<script>
</script>
