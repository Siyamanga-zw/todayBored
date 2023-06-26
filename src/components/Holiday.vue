<template>
    <div class="output">
      
    </div>
</template>

<script>
// Fetching Data from Json Server and adding it to HTML
    export default {
        
    }
async function jsData(){
let data = await fetch("https://siyamanga22.github.io/jason-server/index.json")
const string =  await data.json()
// console.log(string);
let info = string.weekend
// console.log(info);
let result = document.querySelector(".output")
info.forEach(data =>{
    result.innerHTML +=`
    <div class="card" >
    <img src="https://www.spier.co.za/imager/blocks/53230/Spier-Farm-Cafe-Entrance_31ba3d8ce57885e43403070350632d54.jpg" class="card-img-top" alt="...">
    <div class="card-body">
      <h5 class="card-title">${data.place}</h5>
      <p class="card-text">${data.day}</p>
      <a href="#" class="btn btn-primary">ENJOY THE WEEK</a>
    </div>
  </div>
   
    `
})
}
jsData()
</script>

<style scoped>
 .card{
    width: 18rem;
 }
</style>