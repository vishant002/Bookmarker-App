<template>
    <div>
        <h2>{{ noOfVisits }}</h2>
    </div>
</template>

<script>
    export default {
        name : 'CardTwo',
        props: {
            noOfVisits : {
                type: Number,
                required : true,
                default : 0,
            }, 
        },
    }
</script>

<style scoped>

</style>