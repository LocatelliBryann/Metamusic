<template>
    <v-app style="background-color: white">
      <v-app-bar app color="rgb(173,200,230)" elevation="'" >
        <v-app-bar-nav-icon @click.stop="sidebar = !sidebar" color="black"></v-app-bar-nav-icon>
        <v-spacer></v-spacer>
        <v-icon color="black">mdi-account-box </v-icon>
      </v-app-bar>
      <v-navigation-drawer app v-model="sidebar" class="white">
        <v-list dense color="rgb(173,200,230)" dark>
          <v-list-item >           
            <v-list-item-action>
              <v-icon @click.stop="sidebar = !sidebar" color="black">mdi-chevron-left</v-icon>
            </v-list-item-action>
            <v-list-item-tittle>
            <h3 style="color:black"> Metamusic </h3>
          </v-list-item-tittle>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list>
          <v-list-item v-for="item of items" :key="item.title" link :to="item.to">
            <v-list-item-icon>
              <v-icon> {{item.icon}} </v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              {{item.title}}
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
      <v-main> 
        <router-view></router-view>
      </v-main>
      <v-footer app class="py-3 black "> <span class="overline" style="color: white"> MetaMusic &copy;2022 </span></v-footer>
      
    </v-app>
</template>

<script>
export default {
  data(){
    return{
      sidebar:true,
      items:[
        {title:"home", icon:"mdi-home", to:"/"},
        {title:"Artistas", icon:"mdi-account-group", to:"/artistas"},
        {title:"Perfil", icon:"mdi-human-greeting", to:"/perfil"},
        {title:"Sair", icon:"mdi-exit-to-app", to:"/login"},
      ]
    };
  },
};
</script>

<style scoped>

</style>