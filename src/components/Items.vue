<template>
    <div class="item" v-bind:class="{'is-complete':lijst.completed}">
        <input type="checkbox" v-on:change="markComplete">
        <p>{{ lijst.name }}</p>
        <button class="del" @click="$emit('del-lijst', lijst.id)">x</button>
    </div>
</template>

<script>
    export default {
        name: "Item",
        props: ["lijst"],
        methods: {
            markComplete() {
                this.lijst.completed = !this.lijst.completed;
            }
        }
    }
</script>

<style scoped>
    .item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 10px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
        position: relative;
        top: -2em;
    }
</style>