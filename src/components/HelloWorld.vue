<template>
  <div class="hello">

    <div >姓名：{{name}}---年龄：{{age}}</div>
    <input type="text" v-model = "name" />
    <div >姓名：{{person.school}}---年龄：{{person.name}}</div>


    <button v-on:click="showInfo1">展示信息1</button>  &nbsp;
    <button @click="showInfo2($event,66)">展示信息2</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  methods:{
    showInfo1(event){
      console.log('show info1',event);
    },
    showInfo2(event,num){
      console.log('showInfo2',num,event);
      // alert('show info2'+num);
    }
  },
  data(){
    return {
      name:'bella',
      age:13,
      person:{
        name:'miao',
        age:17
      }

    }
  },
  mounted(){
    // Object.defineProperties(this.person,'school',{
    //   value:'nanya'
    // });
    console.log(this.person)
  }


}
</script>

<style scoped>

</style>
