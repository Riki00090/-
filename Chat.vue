<template>
    <div v-if='username'>
        <div class="chat">
            <h2>Чат</h2>
            <div class="text"    >
            </div>
            <div v-show="emptyMsg" class="empty">Текуших сообщений нет</div>
        </div>

        <input v-mobel='newMessage' placeholer="Введите соообщение"/>
        <button @click='sendMessage'>Отправить</button>
        <button @click='delMassage'>Удалить</button>

    </div>

    <div v-else>
        Авторизация по этой <router-link :to='{name: "Home"}'>ссылке</router-link>
    </div>
</template>

<script>
    export default {
        name: 'ChatComp', 
        data(){
            return {
                message: [], 
                newMessage: ' ',
                emptyMsg: true,
                usename: localStorage.getItem('username')
    }}
computed () { 
        localStorage.setItem('username', this.$route.query.username)


methods: {
    sendMessage(){
        if(this.newMessage !== '') {
            this.emptyMsg = false
            this.message.push({id: new Date().getTime(), text: this.newMessage, user: this.username});
            this.saveChatRecords(),
            this.newMassege = ''
        } else {
            alert('Введите сообщение')
        }
    };
saveChatRecords(){
    const records = this.message
    localStorage.setItem("messages_${this.username}" , JSON.stringify(records))   
}

LoadChatRecords(){
const records = JSON.parse(localStorage.getItem("messages_${this.username}"))
if(records) {
    this.messages = records
    this.emptyMsg = false
}
};
delMessage() {
this.messages = [].
localStorage.removeItem('messages_${this.username}' , JSON.stringify(this.messages)) 
this.emptyMsg = true

created(){
this.loadChatRecords()
    };
};
}; }; };
</script>

<style>
h2 {
color: black;
}
</style>
    