<template>
  <div>
    <ul  @click="h2($event)">
      <li v-for="item in list" :key=item.nid >
        <h2>{{item.name}}</h2>
        <audio ref="audio" :src="item.music" id="audio"></audio>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data(){
    return{
      list:[],
      mu:[],
    }
  },
  methods:{
    h1(){
      var url ="http://127.0.0.1:3000/may"
      this.axios.get(url).then((result)=>{
        console.log(result.data)
        this.list=result.data;
      
      })
    },
    h2(e){
     var audio =document.querySelector('#audio');
  
      console.log(e.target)
    audio.play();
    }
  },
  created(){
    this.h1();
  }
}
</script>
<style>

</style>

