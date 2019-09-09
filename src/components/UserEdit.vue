<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>Edit me!</p>
        <button @click ="editAge">Edit Age</button>
        <p>{{age}}</p>

    </div>
</template>
<script>
import {eventBus} from "../main"
export default {
  props:{
    age:{
      type:Number
    }
  },
  methods:{
    editAge:function(){
       this.age = 25,
      //  this.$emit("ageEdited",this.age )
        // eventBus.$emit("ageEdited",this.age)
        eventBus.changeAge(this.age)

    }
  }
}
</script>>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>
