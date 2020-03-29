<template>
  <div>
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

    <v-dialog v-model="dialog" width="500">
      <template v-slot:activator="{ on }">
        <v-btn outline depressed v-on="on">
          <v-tooltip bottom>
            <template v-slot:activator="{ on: tooltip }">
              <v-btn outline depressed v-on="{ ...tooltip, ...menu }">
                <span class="hidden-md-and-down">{{$t('nav.contribute')}}</span>
                <v-icon class="ml-3">mdi-account-group</v-icon>
              </v-btn>
            </template>
            <span>{{$t('nav.contributeHeader')}}</span>
          </v-tooltip>
        </v-btn>
      </template>

      <v-card>
        <v-card-title class="headline grey lighten-2" primary-title>{{$t('nav.contributeHeader')}}</v-card-title>

        <v-card-text class="mt-3">{{$t('nav.contributeTxt')}}</v-card-text>

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
        <v-tooltip bottom>
          <template v-slot:activator="{ on: tooltip }">
            <v-btn outline depressed v-on="{ ...tooltip, ...menu }">
              <span class="mr-2 hidden-md-and-down">{{$t('nav.importantLinks')}}</span>
              <v-icon>mdi-link</v-icon>
            </v-btn>
          </template>
          <span>{{$t('nav.importantLinks')}}</span>
        </v-tooltip>
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
              <v-list-item-title>Resources and Handbook</v-list-item-title>
            </v-list-item-content>
          </v-list-item>

          <!-- Ethio Stats -->
          <v-list-item href="https://www.google.com/covid19/" target="_blank">
            <v-list-item-icon>
              <v-icon>mdi-link</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title>Google Covid Page</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
            
            <!-- COVID-19 Info -->
            <v-list-item href="https://www.youtube.com/watch?v=BtN-goy9VOY" target="_blank">
              <v-list-item-icon>
                <v-icon>mdi-file-video</v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>What is COVID-19?</v-list-item-title>
              </v-list-item-content>
            </v-list-item>

            <!-- Multi-Lang Covid Info -->
            <v-list-item href="https://t.me/covid19ethio" target="_blank">
              <v-list-item-icon>
                <v-icon>mdi-telegram</v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>Multi-Lang COVID-19 Info</v-list-item-title>
              </v-list-item-content>
            </v-list-item>

            <!-- Ethio News -->
            <v-list-item href="https://t.me/tikvahethiopia" target="_blank">
              <v-list-item-icon>
                <v-icon>mdi-telegram</v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>Ethiopia News Amharic</v-list-item-title>
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
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({})
};
</script>
