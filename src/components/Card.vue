<template>
    <div class="cardBox">
        <div>
            <h3>
                <slot name="title">    
                </slot>
            </h3>
        </div>
        <div>
            <p>
                <slot>
                        
                </slot>
            </p>
        </div>
        <div>
            <slot name="link">
                    
            </slot>
        </div>
    </div>
</template>

<script>
    export default {
        name:'carD'
    }
</script>

<style scoped>
.cardBox{
    margin: auto;
    margin-bottom: 10px;
    width : 500px;
    padding-left: 10px;
    padding-top: px;
    padding-bottom: 10px;
    text-shadow: 10px;
    border: 2px solid grey;
}
</style>