<template>
    <div>
        <form @submit="addLijst">
            <input type="text" name="name" placeholder="name" v-model="name">
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
                name: ''
            }
        },
        methods: {
            addLijst(e) {
                e.preventDefault();
                const newLijst = {
                    id: uuid.v4(),
                    name: this.name,
                    completed: false
                }

                this.$emit('addLijst', newLijst);

                this.name = '';
            }
        }
    }
</script>

<style scoped>
    form {
        display: flex;
    }

    input[type="text"] {
        flex: 10;

        padding: 10px;
    }

    input[type="submit"] {
        flex: 2;
    }
</style>