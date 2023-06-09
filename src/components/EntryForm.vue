<template>
    <div>
        
      <div>
        <label for="title">Title : </label> <br>
        <input type="text" v-model="entryvalue.title"/>
      </div>
      <br>
      <div>
        <label for="discription">Discription : </label> <br>
        <textarea id="discription" v-model="entryvalue.discription"></textarea>
      </div>
      <br>
      <div>
        <label for="link">Link : </label> <br>
        <input type="text" v-model="entryvalue.link"/>
      </div>
      <br>
      <br>
      <button @click="$emit('close', entryvalue)">Submit</button>
    </div>
</template>

<script>
    export default {
        name : 'EntryForm',
        emits: ['close'],
        data() {
            return {
                entryvalue: {
                    title: '',
                    discription: '', 
                    link : '',
                },
            }
        },
    }
</script>

<style scoped>

</style>