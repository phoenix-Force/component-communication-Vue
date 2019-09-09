<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
        <button @click="fn">change </button>
        <p>{{name}}</p>
        <p>{{age}}</p>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail :name="name" @ageChanged = "age = $event" @nameReset = "name = $event" :age= "age" ></app-user-detail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit :age= "age" @ageEdited = "age =$event"></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {
      data:()=>{
              return{
                name:"paradox",
                age:23
              }
            },
      methods:{
        fn:function(){
          this.name = "!Dox";
        }
      },
      components: {
        appUserDetail: UserDetail,
        appUserEdit: UserEdit
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
