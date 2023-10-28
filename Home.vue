<template> 
    <div>
<div v-if='isAuthenticated'>
<div>Привет <b>{{username}}</b></div> 
<button @click="logout">Bыйти</button>
</div>
<div v-else>
    <label>Введите Имя:</label> 
    <input v-model='username'/>
    <button @click="login">Coxpaнитb</button>
</div>
</div>
</template>
<script>
export default {
name: 'HomePage',
data(){
    return {
        isAuthenticated: false,
        username: ''
}
methods: {
login(){
if(this.username !== '') {
this.isAuthenticated = true
localStorage.setItem('isAuthenticated', true)
localStorage.setItem('username', this.username)

this.$router.push({
name: 'Chat',
query: { username: this.username}
})
} else {
alert('Напишите имя')
}
}
logout() {
this.isAuthenticated = false
this.username=''
localStorage.removeItem('isAuthenticated') 
localStorage.removeItem('username')
}
},
created(){
if(localStorage.getItem('isAuthenticated')) {
this.isAuthenticated = true
this.username = localStrage.getItem('username')
}
}
}}
</script>