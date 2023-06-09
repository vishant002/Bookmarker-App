<template>
  <div>
    <h2 class="middle">Add Bookmark</h2>
    <div class="box">
      <form @submit.prevent="submitform">
        <div>
          <label for="title">Title : </label> <br />
          <input type="text" v-model.trim.lazy="addBookmarks.title" />
        </div>
        <br />
        <div>
          <label for="discreption">Discription : </label> <br />
          <textarea
            id="discreption"
            rows="4"
            cols="64"
            v-model.trim.lazy="addBookmarks.discription"
          >
          </textarea>
        </div>
        <br />
        <div>
          <label for="link">Link : </label> <br />
          <input type="text" v-model.trim.lazy="addBookmarks.link" />
        </div>
        <br />
        <button 
          :class="Hover?'hover':'button'"  
          @mouseover="changeColor(true)" 
          @mouseout="changeColor(false)" 
          @click="$emit('close',addBookmarks)
          ">Submit</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "addButton",
  data() {
    return {
      emit: ["close"],
      addBookmarks: {
        title: "",
        discription: "",
        link: "",
      },
      Hover:false,
    };
  },
  methods: {
    submitform() {
      console.log("Added Bookmark was : ", this.addBookmarks);
    },
    changeColor(todo){
      if(todo==true){
        this.Hover=true;
      }
      else{
        this.Hover=false;
      }
    }
  },
};
</script>

<style scoped>
.card{
  margin-top: 10px;

  height: 400px;
  margin-bottom: 20px;
  border: 2px solid black;
}
.box {
  width: 500px;
  height: 265px;
  margin: auto;
  /* margin-top:100px; */
  padding-top: 2%;
  border: 2px solid black;
  padding-left: 10px;
}
.middle {
  text-align: center;
}

.hover{
  padding: 6px;
  font-size: 15px;
  width: 100px;
  height: 35px;
  color: rgb(255, 255, 255);
  background-color: rgba(12, 164, 91, 0.959);
  border-color: rgba(12, 164, 91, 0.959);
}
.button{
  padding: 6px;
  font-size: 15px;
  width: 100px;
  height: 35px;
  color: rgb(255, 255, 255);
  background-color: rgb(44, 71, 32);
  border-color: rgb(44, 71, 32);
}

</style>
