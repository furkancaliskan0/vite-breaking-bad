<script >
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store.js';
export default{
  data() {
    return {
      store
    }
  },
  methods:{
    getCharacters(){

      let myUrl = store.apiUrl;
      
      if (store.searchStatus !== "") {
        myUrl += `?${store.apiStatus}=${store.searchStatus}`;
      }
      axios
      .get(myUrl)
      .then(res =>{
        store.characterList = res.data.results;
      })
      .catch(err =>{
        console.log("Errori",err);
      }
      )
     
    }
   
  },
  components: {
    AppHeader,
    AppMain
    
    
  },
  mounted() {
        this.getCharacters();
      }
}
</script>

<template>
  
  <AppHeader/>
    <AppMain @search="getCharacters"/>
 
</template>


<style lang="scss">
@use "./styles/partials/variables" as*;

body{
  background: $bg-dark-blue;
}

</style>