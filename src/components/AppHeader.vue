<script>
    export default{
        name: "AppHeader"
    }
</script>

<template>
 <header>
    <h1>Rick and Morty Api</h1>
 </header>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as*;

header{
    height: 100px;
    display: flex;
    padding: 10px;
}   
    h1{
    color:$main-color;
    margin: 0 auto;
    text-align: center;
    font-size: 80px;

    }
</style>