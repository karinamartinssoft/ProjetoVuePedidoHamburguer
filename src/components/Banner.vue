<template>
    <div id="main-banner">
        <h1>
            Crie seu Hamburguer!
        </h1>
     </div>

</template>

<script>
export default {
    name: "Banner"
}
</script>

<style scoped>
#main-banner {
    background-image: url('/img/burguer_back.jpg');
    background-position: 0 -550px;
    background-size: cover;
    height: 500px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
}

#main-banner h1{
    color: #FFF;
    text-align: center;
    font-size: 60px;
    background-color: #b68e0980;
    padding: 20px 40px;
}
</style>