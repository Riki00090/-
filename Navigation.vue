<template>
    <div class="nav">
    <nav>
    <router-link to='/'>Главная</router-link>
    <router-link to='/chat'>Чат</router-link>
    <router-link to='/test'>Подгрузка даннных</router-link>
    </nav>
    </div>
</templates>
    <script>
    export default {
    name: 'NavComp'
    }
    </script>
    <style scoped>
    .nav {
        background-color: black;
        width: 100%;
    display: flex;
    justify-content: center;
    }
    nav {
    width: 500px;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 30px;
    }
</style>