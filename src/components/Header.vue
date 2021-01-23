<template>
    <header>

        <h1>
            <router-link to="/">
                <img src="../assets/logo2.png">
            </router-link>
        </h1>

        <h4>Movies In Theatres Now</h4>

    </header>
</template>

<script>

    export default {
        name: "Header",
        props: {
            title: String,
        },
        data() {
            return {
                name: "Allison",
                show: false,
            };
        },
        computed: {
            newTitle: function () {
                return this.title;
            }
        }
    }
</script>

<style scoped>
    header {
        background-color : #111;
        padding          : 20px;
        color            : white;
    }

    h1 {
        margin : 0;
    }


</style>