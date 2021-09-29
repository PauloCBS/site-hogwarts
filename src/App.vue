<template>
 <v-app>
   <AppTopBar/>
      <v-main>
       <Inicio/>
     </v-main>
    </v-app>
  </template>


<script>
import Inicio  from'./views/Inicio.vue'
import AppTopBar from'./components/shared/AppTopBar.vue'

export default {
   name: 'app',
   components:{
     Inicio,
     AppTopBar,
   }

}

</script>

