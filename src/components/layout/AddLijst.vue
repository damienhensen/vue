<template>
    <div>
        <form @submit="addLijst">
            <input type="text" name="title" placeholder="title" v-model="title">
            <input type="text" name="author" placeholder="author" v-model="author">
            <input type="text" name="duration" placeholder="duration in sec" v-model="duration">
            <input type="text" name="uploadDate" placeholder="upload date in MM-DD-YYYY" v-model="uploadDate">
            <input type="text" name="link" placeholder="https://www.youtube.com/watch?v=XXX" v-model="link">
            <input type="submit" name="submit" class="btn">
        </form>
    </div>
</template>

<script>
    import uuid from 'uuid';

    export default {
        name: "AddLijst",
        data() {
            return {
                title: "",
                author: "",
                duration: "",
                uploadDate: "",
                link: "",
            }
        },
        methods: {
            addLijst(e) {
                e.preventDefault();
                const newLijst = {
                    id: uuid.v4(),
                    title: this.title,
                    author: this.author,
                    duration: this.duration,
                    uploadDate: this.uploadDate,
                    link: "https://www.youtube.com/watch?v="+this.link,
                    thumbnail: "https://i.ytimg.com/vi/"+this.link+"/hqdefault.jpg"
                }

                this.$emit('addLijst', newLijst);

                this.title = '';
                this.author = '';
                this.duration = '';
                this.uploadDate = '';
                this.link = '';
            }
        }
    }
</script>

<style scoped>
    form {
        display: flex;
        flex-wrap: wrap;
    }

    input[type="text"] {
        flex: 10;

        padding: 10px;
    }

    input[type="submit"] {
        flex: 2;
    }
</style>