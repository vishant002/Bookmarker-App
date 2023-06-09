<template>
  <h1 class="middle">bookMarker.com</h1>
  <hr />
  <div class="box">
    <button class="button" @click="showAdd">ADD</button>&nbsp;&nbsp;
    <button class="button" @click="showModify">MODIFY</button>&nbsp;&nbsp;
    <button class="button" @click="showSearch">SEARCH</button>&nbsp;&nbsp;
    <button class="button" @click="showDelete">DELETE</button>
  </div>
  <addButton v-if="activated == 'addButton'" @close="formSubmitted" />
  <deleteButton v-if="activated == 'deleteButton'" />
  <searchButton v-if="activated == 'searchButton'" />
  <modifyButton v-if="activated == 'modifyButton'" />
  <br>
  <div v-if="recentlyAddedBookmarks.length >= 1" class="recentBox">
  
  <!-- <div class="recentBox"> -->
    <h2 class="middle">Recently Added Bookmarks</h2>
    <hr />
    <div v-for="value in reverserecentlyAddedBookmarks" :key="value.title">
      <carD>
        <template v-slot:title>
          Title: {{ value.title }}
          <hr />
        </template>
        <template v-slot:default>
          Discreption:<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          {{ value.discription }}
          <hr />
        </template>
        <template v-slot:link>
          <a href="value.link"
            ><button class="linkbtn" @click.prevent="linkButton">
              Open Link
            </button></a
          >
          <button class="delbtn" @click="deleteBookmark(value)">Delete</button>
        </template>
      </carD>
      <!-- <h3>{{ value.title }} </h3>
          <h5>{{ value.discription }}</h5>
          <a href="value.link">LINK</a> -->
    </div>
  </div>
</template>

<script>
import addButton from "./components/addButton.vue";
import searchButton from "./components/searchButton.vue";
import deleteButton from "./components/deleteButton.vue";
import modifyButton from "./components/modifyButton.vue";
import carD from "./components/Card.vue";

export default {
  name: "App",
  components: {
    addButton,
    searchButton,
    deleteButton,
    modifyButton,
    carD,
  },
  data() {
    return {
      activated: '',
      addbtn:false,
      delbtn:false,
      modbtn:false,
      secbtn:false,
      recentlyAddedBookmarks: [
        {
          title: "Srila Prabhupada",
          discription:
            "His Divine Grace A.C. BHaktivedanta Swami Srila Prabhupada, Founder Acharaya of International Society for Krsna Consiousness.",
          link: "www.vedabase.com",
        },
      ],
    };
  },
  computed: {
    reverserecentlyAddedBookmarks() {
      return this.recentlyAddedBookmarks.slice().reverse();
    },
  },
  methods: {
    linkButton() {},
    deleteBookmark(value){
        const index=this.recentlyAddedBookmarks.indexOf(value);
        this.recentlyAddedBookmarks.splice(index,1);
    },
    formSubmitted(entry) {
      this.activated = "";
      console.log(entry);
      this.recentlyAddedBookmarks.push(entry);
    },
    closeAdd() {
      this.activated = 0;
    },
    showAdd() {
      if (this.activated == "addButton") {
        this.activated = "";
      } else {
        this.activated = "addButton";
      }
    },
    showDelete() {
      if (this.activated == "deleteButton") {
        this.activated = "";
      } else {
        this.activated = "deleteButton";
      }
    },
    showModify() {
      if (this.activated == "modifyButton") {
        this.activated = "";
      } else {
        this.activated = "modifyButton";
      }
    },
    showSearch() {
      if (this.activated == "searchButton") {
        this.activated = "";
      } else {
        this.activated = "searchButton";
      }
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 0px;
}

.recentBox {
  border: 1px solid black;
}

.middle {
  text-align: center;
}

.button {
  margin: 6px;
  padding: 6px;
  font-size: 20px;
  width: 110px;
  height: 45px;
  color: rgb(255, 255, 255);
  background-color: rgba(0, 38, 255, 0.838);
  border-color: rgb(0, 47, 255);
}

.button:hover {
  font-size: 22px;
  background-color: rgba(37, 110, 162, 0.838);
  border-color: rgba(37, 110, 162, 0.838);
}

.box {
  margin: auto;
  padding: 8px;
  border: 2px solid rgb(32, 27, 27);
  background-color: rgb(32, 27, 27);
}

.linkbtn {
  color: white;
  background-color: rgba(38, 156, 38, 0.845);
  border-color: rgba(38, 156, 38, 0.845);
  margin-left: 170px;
}

.linkbtn:hover {
  background-color: rgba(52, 102, 52, 0.845);
  border-color: rgba(52, 102, 52, 0.845);
}

.delbtn {
  margin-left: 10px;
  color: white;
  background-color: red;
  border-color: red;
}

.delbtn:hover {
  background-color: rgb(235, 100, 100);
  border-color: rgb(235, 100, 100);
}
</style>
