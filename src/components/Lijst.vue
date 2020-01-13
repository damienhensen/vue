<template>
    <div>
        <div v-bind:key="lijst.id" v-for="lijst in lijsten">
            <Item v-bind:lijst="lijst" v-on:del-lijst="$emit('del-lijst', lijst.id)" />
        </div>
    </div>
</template>

<script>
    import Item from './Items.vue';

    export default {
        name: "Lijsten",
        components: {
            Item
        },
        props: ["lijsten"]
    }
</script>

<style scoped>

</style>