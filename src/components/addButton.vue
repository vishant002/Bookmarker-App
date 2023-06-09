<template>
  <div>

    <h2>Add Bookmark</h2>
  
  <div class="box">
    <form @submit="submitform">
      <div>
        <label for="title">Title : </label> <br>
        <input type="text" v-model.trim.lazy="addBookmarks.title">
      </div>
      <br>
      <div>
        <label for="discreption">Discreption : </label> <br>
        <textarea id="discreption" v-model.trim.lazy="addBookmarks.discreption"></textarea>
      </div>
      <br>
      <div>
        <label for="link">Link : </label> <br>
        <input type="text" v-model.trim.lazy="addBookmarks.link">
      </div>
      <br>
      <br>
      <button @click=" $emit('close')">Submit</button>
    </form>
  </div>  
</div>
</template>

<script>
  export default{
    name: "addButton",
    // add: false,
    data(){
      return{
        emit: ['close'],
        addBookmarks:{
          title:'',
          discreption: '',
          link:''
        }
      }
    },
    methods:{
      submitform(event){
        event.preventDefault();
        console.log('Added Bookmark was : ', this.addBookmarks);
      }
    }
  };
</script>

<style>
.box{
  /* box-sizing: border-box; */
  width: 300px;
  height: 250px;
  /* -moz-box-align: center; */
  margin : auto;
  /* padding-left: 10%; */
  padding-top: 2%;
  border: 2px solid black;
}
</style>