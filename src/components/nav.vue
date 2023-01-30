<template>
    <nav id="nav">
        <router-link to="/">Cliente</router-link> 
        <router-link to="/product">Produtos</router-link>
    </nav>
</template>

<script>
    export default{
        name: 'Navbar'
    }
</script>

<style scoped>
    #nav{
        background-color: #4e4c4c;
        padding: 2% 6%;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }
    #nav a{
        text-decoration: none;
        color: #FFF;
        margin: 1%;
        cursor: pointer;
        transition: .5s;
        font-size: large;
    }

    #nav a:hover{
        color:rgb(235, 136, 44);
        border-bottom: 2px solid rgb(235, 136, 44);
    }

</style>