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
        <section class="card">
            <Card v-for="character in store.characterList" :info="character"/>
        </section>
  </main>
</template>

<style lang="scss" scoped>
    .card{
        margin: auto;
        width:100%;
        background: yellow;
        display: flex;
        justify-content:center;
        flex-wrap: wrap;
        text-align: center;
        margin: 10px;
    }
</style>