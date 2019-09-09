<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <h2>{{rev()}}</h2>
        <h3>{{age}}</h3>
        <button @click ="rst">Reset</button>
        <button @click ="nwAge">Eduit age</button>
    </div>
</template>

<script>
    import {eventBus} from "../main"
export default {
  props:{
    // name:[String,Array]
    name:{
      type:String,
      required:true
      // default:
    },
    age:{
      type:Number
    }
  },
  methods:{

    rev:function(){
      return this.name.split("").reverse().join("");
    },
    rst:function(){
      this.name = "!pi"
      this.$emit("nameReset",this.name)
    },
    // nwAge:function(){
    //    this.age = 30
    //   this.$emit('ageChanged',this.age)
    // },
    created(){
      eventBus.$on("ageEdited",(data)=>{
        this.age = data
      })

    }

  }

}
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
