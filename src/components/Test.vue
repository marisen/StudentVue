<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2 v-text="msg"></h2>
    <h3 v-pre>{{msg}}</h3>
    <WodevueVue :title="t1" @listenToChild="show"/>
  </div>
</template>

<script>
import WodevueVue from './Wodevue.vue'
export default {
  name: 'TestVue',
  data () {
    return {
      msg: '在测试我的VUE',
      t1:'父子传值'
    }
  },
  components:{
    WodevueVue
  },methods: {
    show(name){
      console.log(name);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
