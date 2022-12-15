<script >
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store.js';
export default{
  data() {
    return {
      store,
    }
  },
  methods:{
    getCharacter(){
      axios
      .get(store.apiUrl)
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
    AppMain,
    
    
  },
  mounted() {
        this.getCharacter();
      }
}
</script>

<template>
  
  <AppHeader />
  <AppMain/>
</template>


<style lang="scss">

</style>