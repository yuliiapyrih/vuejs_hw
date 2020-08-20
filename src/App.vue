<template>
  <div>
  <input type="text" v-model='list'>
  <button @click='save' v-show='show'>Save point</button>
  
  <ul>
      <li v-for="(point, indexList) in todolist" :key='indexList'>
        {{point}} 
         <button @click='remove(indexList)'>Delete point</button>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      msg: 'Hello world!!!',
      todolist:[],
      saveBtn:0,
      list:'',
      show: true,
    }
  },

  methods:{

    save(){
      this.todolist.push(this.list);
      this.list='';
      this.todolist.length>9 ? this.show=false : this.show=true;
    },
    remove(indexList){
      this.todolist.splice(indexList,1);
      this.todolist.length>9 ? this.show=false : this.show=true;
    }
  }
}
</script>

<style>

</style>
