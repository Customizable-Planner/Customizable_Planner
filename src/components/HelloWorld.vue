<template>
  <div id='main_board'>
    <v-app>
      <v-app-bar app color="green" dark flat>
        <v-btn icon @click.stop="bDrawer = !bDrawer">
            <v-icon>mdi-menu</v-icon>
        </v-btn>
        <v-toolbar-title>Customizable Planner</v-toolbar-title>
      </v-app-bar>
      <v-navigation-drawer absolute temporary v-model="bDrawer">
        <v-toolbar flat height="70px">
          <v-list>
            <v-list-item>
              <v-list-item-content>
                <v-list-item-title class="title">홍길동</v-list-item-title>
                <v-list-item-subtitle v-text="age"></v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-toolbar>
        <v-divider></v-divider>

        <v-list class="pt-3">
          <v-list-item v-for="item in aMenu_items" :key="item.title" :href="item.link" >
            <v-list-item-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
      <v-content>
        <v-container>
          <v-layout justify-center>
            <v-card>
              <v-flex>
                <v-toolbar dense flat>
                  <v-toolbar-title>Add your own planner!</v-toolbar-title>
                  <v-spacer>
                  </v-spacer>
                  <v-btn icon>
                    <v-icon>mdi-plus</v-icon>
                  </v-btn>
                </v-toolbar>
              </v-flex>
            </v-card>
          </v-layout>
        </v-container>
      </v-content>
    </v-app>
  </div>
</template>

<script>
export default {
  data () {
    return {
      age: 24,
      bDrawer: false,
      aMenu_items: [{
        title: 'Check list',
        icon: 'mdi-coffee',
        link: '#'
      },
      {
        title: 'Time table',
        icon: 'mdi-apple',
        link: '#'
      },
      {
        title: 'Memo',
        icon: 'mdi-facebook',
        link: '#'
      }
      ]
    }
  }

}
</script>
