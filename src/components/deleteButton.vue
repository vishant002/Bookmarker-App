<template>
    <div>
    <h2 class="middle">Delete Bookmark</h2>
        <div class="box">
            <div>
                <label for="method">Title : </label>
                <input type="text" id="title">
            </div>
            <br>
            <div>
                <button class="button">Search</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name : 'deleteButton'
    }
</script>

<style scoped>
.box{
    border: 1.3px solid black;
    padding: 10px;
    margin: auto;
    width:50%;
}
.middle{
    text-align: center;
}

.button{
    margin-left: 35%;
}
</style>