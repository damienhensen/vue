<template>
    <div class="item">
        <div class="song">
            <p class="song__title">{{ lijst.title }} - {{ lijst.author }}</p>
            <div class="song__misc">
                <p class="song_duration">Duration: {{ lijst.duration }}</p>
                <p class="song__release">Upload date: {{ lijst.uploadDate }}</p>
                <a v-bind:href=lijst.link class="song__link" target="_blank">{{ lijst.title }}</a>
            </div>
            <div class="cover">
                <img v-bind:src=lijst.thumbnail >
            </div>
        </div>
        <button class="del" @click="$emit('del-lijst', lijst.id)">x</button>
    </div>
</template>

<script>
    export default {
        name: "Item",
        props: ["lijst"]
    }
</script>

<style scoped>
    .item {
        background: #f4f4f4;
        padding: 2em .8em;
        border-bottom: 1px #ccc dotted;
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
        top: -3.3em;
        right: 6em;
    }

    .song {
        width: 80%;
        margin: 0 auto;
    }

    .song__title, .song__author {
        font-size: 1.5rem;
        margin: .5em 0;
    }

    .song__misc {
        font-size: 1rem;
        display: flex;
    }

    .song_duration, .song__release {
        margin-right: 1em;
    }

    .song_duration:after, .song__release:after {
        content: "|";
        margin-left: 1em;
        position: relative;
        bottom: .1em;
    }

    .cover {
        position: absolute;
        right: 20vw;
    }

    .cover img {
        height: 70px;
        position: relative;
        bottom: 4em;
    }

</style>