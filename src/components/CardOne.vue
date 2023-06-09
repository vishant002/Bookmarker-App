<template>
    <div class="card">
        <h2>{{ title }}</h2>
        <a v-bind="$attrs">Visit Link</a>
        <div class="card-btn">
            <button >Remove</button>
            <button >Edit</button>
        </div>
    </div>


</template>

<script>
export default{
    name: 'CardOne',
    props : ['title', 'link'],
    inheritAttrs: false,
}
</script>


