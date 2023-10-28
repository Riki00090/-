<template> 
    <div>
    <div>Kоманды</div>
    <div v-if='isLoad'>загрузка данныx...</div>
    <div v-else>
        <div v-for="el in teamData" :key="el.id">
            {{el.id}}. {{ el.abbreviation }} {{ el.city }}
            <img 
            src='https://catherineasquithgallery.com/uploads/posts/2023-02/1676592601_catherineasquithgallery-com-p-fon-dlya-zelenoi-lyagushki-2.jpg'
            />
        </div>
    </div> 
</div> 
</template>
<script>
    export default {
    name: 'TestApi',
    data(){
    return {
    teamData: [],
    isLoad: true
    }
}
    mounted () {
        const url = 'https://sudoku-suite.p.rapidapi.com/levels';
const options = {
	method: 'GET',
	headers: {
		'X-RapidAPI-Key': 'a0ef84a0d9msh698803cda26fb37p1d5602jsnbcddcb591289',
		'X-RapidAPI-Host': 'sudoku-suite.p.rapidapi.com'
	}}
    fetch(url, options)
.then((res) => res.json()) 
.then((res)=>{ 
    console.log(res);
    this.teamData = res.data 
    this.isLoad = false
})
    }
    methods: {
    removeTeam(id) {
this.teamData = this.teamData.filter((el) => el.id !== id)
}
}}
    </script>