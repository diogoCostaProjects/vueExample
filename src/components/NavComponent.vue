<script>
    export default {
       name: 'NavComponent',
       props:{
        text: String
       }
    }
</script>

<template>
    <nav class="navbar navbar-light bg-light">
        <div class="container-fluid">
            <img src="../assets/logo.png" alt="">
            <h4>{{text}}</h4>
        </div>
    </nav>
</template>

<style>
    nav{
        margin-top: -60px;
        margin-bottom: 30px;
    }
    img{
        width: 15%;
    }
</style>