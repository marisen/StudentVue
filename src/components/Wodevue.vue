<template>
<div>
    <h2>{{title}}</h2>
    <input type="text" name="" id="" v-model="id">
    <input type="text" name="" id="" v-model="name">
    <input type="button" value="添加" @click="Add">
    <p v-for="(item,i) in historyList" :key="item.id"><input type="checkbox">索引：{{i}}------{{item.id}}-----{{item.name|StringFormat}}</p>
</div>
</template>
<script>

export default {
    name:"wode",
    data(){
        return{
            id:"",
            name:"",
            historyList:[
                   {id:1,name:"秦"},
                   {id:2,name:"汉"},
                   {id:3,name:"晋"},
                   {id:4,name:"隋"}
               ]
        }
    },
    methods: {
        Add(){
            this.historyList.push({id:this.id,name:this.name})
            this.$emit("listenToChild",this.name);
        }
    },
    filters: {
        StringFormat:val=>{
            return val+"777";
        }
    },
    props: ["title"]
}
</script>