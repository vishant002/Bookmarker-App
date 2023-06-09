<template>
    <div>bookMarker.com</div>
 

    <!-- buttons for diff funtions  -->
    <!-- <div>
      <button @click="trueadd">ADD</button>
      <button>MODIFY</button>
      <button>SEARCH</button>
      <button>DELETE</button>
    </div> -->
    <!-- <div>
      <pre>
        {{ JSON.stringify(addBookmarks,null,2) }}
      </pre>
    </div> -->
  
    <!-- form for adding new link  -->
    <!-- <div v-show='add' class="box">
      <form @submit.prevent="submitform">
        <div>
          <label for="Name">Name : </label> <br>
          <input type="text" id="name" v-model.trim.lazy="addBookmarks.name">
        </div>
        <br>
        <div>
          <label for="Discreption">Discreption :</label> <br>
          <textarea id="discreption" v-model.lazy="addBookmarks.discreption"></textarea>
        </div>
        <br>
        <div>
          <label for="Link">Link : </label> <br>
          <input type="text" id="link" v-model.lazy="addBookmarks.link">
        </div>
        <br>
        <div>
          <button class="cen">Submit</button>
        </div>
      </form>
    </div>
    
    <div id="content">

    </div> -->

    <!-- <CardOne title="Github" href="github.com"/> -->
    <!-- <CardOne title="Github" link="github.com"/> -->
    
    <!-- <CardTwo :noOfVisits="20"/> -->
    <button @click="showEntryForm = true">Add New Link</button>
    <EntryForm v-show="showEntryForm" @close="submit"/>
    <CardOne :title="items[items.length - 1].title" :href="items[items.length - 1].link"/>
    
  </template>
  
  <script>
  // import HelloWorld from './components/HelloWorld.vue'
  import CardOne from './components/CardOne.vue'
  // import CardTwo from './components/CardTwo.vue'
  import EntryForm from './components/EntryForm.vue'
  
  export default {
    components :{
      CardOne,
      // CardTwo,
      EntryForm,
    },
    name: 'App',
    data(){
      return{
        // add: false,
        // // name : 'Radheshyam prji website',
        // addBookmarks : {
        //   name:'',
        //   discreption:'',
        //   link:''
        // },

        items : [
          {
            title : 'RadheyShyam Prji Website', 
            discription : 'Githubb website', 
            link : 'www.github.com'
          }, 
        ],
        showEntryForm : false,

      }
    },

    methods: {
      submit(entryvalue){
        this.showEntryForm = false,
        console.log('Title', entryvalue);
        this.items.push(entryvalue);

      }
    }
    // methods:{
    //   trueadd(){
    //     if(this.add==true){
    //       this.add=false;
    //     }
    //     else{
    //       this.add=true;
    //     }
    //   },
    //   submitform(event){
    //     event.preventDefault();
    //     console.log('Add Bookmarks', this.addBookmarks);
    //     this.add=false;

    //     let newitem = {
    //         name: document.getElementById('name').value,
    //         discreption: document.getElementById('discreption').value,
    //         link: document.getElementById('link').value
    //     }
    //     this.items.push(newitem)
    //     console.log(this.items.values);
    //     document.getElementById('content').appendChild

    //     const node = document.createElement("li");
    //     const textnode = document.createTextNode(document.getElementById('name').value);
    //     node.appendChild(textnode);
    //     document.getElementById("content").appendChild(node);
    //     // this.items.push({event.name, event.discreption, event.link});
    //   }
    // }
    
  }
  </script>
  
  <style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  
  .box{
    box-sizing: border-box;
    width: 300px;
    height: 250px;
    -moz-box-align: center;
    margin : auto;
    /* padding-left: 10%; */
    padding-top: 2%;
    border: 2px solid black;
  }
  .cen{
    /* margin-left: 45px; */
    align-content: center;
  }

  .card{
    padding: auto;
    text-align: left;
    /* margin: auto; */
    margin-left: 2px;
    margin-top: 5px;
    margin-bottom: 5px;
    border: 1px solid black;
  }

  .card-btn{
    display: block;
    text-align: center;
    /* margin-left: 5px;
    margin-right: 5px; */
    padding: 5px;
    margin: auto;
    margin-top: 2px;
    margin-bottom: 2px;
  }

  .card-btn button{
    padding-left: 3px;
    padding-right: 3px;
    margin-left: 3px;
    margin-right: 3px;
  }
  </style>