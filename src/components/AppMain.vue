<script >
import Card from "./Card.vue"
import {store} from '../store.js'
   export default{
    
        name:"AppMain",
        components:{
            Card,
        },
        data() {
            return {
                store,
            }
        },
   }
</script>

<template>
  <main>
        <section id="card-container">
            <div class="card" v-for="character in store.characterList" 
            :key="character.id">
            <Card :info="character"/>
            </div>
      
        </section>
  </main>
</template>

<style lang="scss" scoped>
    #card-container{
        margin: auto;
        width:100%;
        background: yellow;
        display: flex;
        justify-content:center;
        flex-wrap: wrap;
        .card{
            text-align: center;
            margin: 10px;
        }
    }
</style>