<script >
import Card from "./Card.vue"
import {store} from '../store.js'
   export default{
        name:"AppMain",
        components:{
            Card
        },
        data() {
            return {
                store
            };
        }
   };
</script>

<template>
  <main>
    <select class="category" id="category" v-model="store.searchStatus" @change="$emit('search')">
                <option value="choice">Select Category</option>
                <option value="alive">Alive</option>
                <option value="dead">Dead</option>
                <option value="unknown">Unknown</option>
            </select>
        <section class="card">

            <div class="result">
                    Find {{ store.characterList.length }} characters
            </div>

            <Card v-for="character in store.characterList" :key="character.id" :info="character"/>
        </section>
        
  </main>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as*;
    .card{
        margin: auto;
        width: 100%;
        background: $bg-dark-blue;
        display: flex;
        justify-content:center;
        flex-wrap: wrap;
        text-align: center;
        margin: 10px;
    }
    .result{
        width: 88%;
        padding: 5px;
        color: $bg-dark-blue;
        margin: 10px;
        font-weight: bolder;
        background-color: $main-color;
    }
    .category{
        color: $bg-dark-blue;

    }
</style>