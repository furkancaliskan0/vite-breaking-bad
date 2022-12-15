<script >
   export default{
        name:"Card",
        props:["info"],
       
   }
</script>

<template>
    <section id="card">
            <img :src="info.image" alt="">
                <h4>{{info.name}}</h4>
                <h4>{{info.status}}</h4>
                <h4>{{info.species}}</h4>
    </section>
</template>

<style lang="scss" scoped>
        h4{
            margin: 15px 0;
            text-align: center;
        }

        img {
            border-radius: 50%;
        }

</style>