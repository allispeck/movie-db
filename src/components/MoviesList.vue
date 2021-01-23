<template>
    <div>
        <ul>
            <li v-for="movie in movies">
                <Movie v-bind:movie="movie"/>
            </li>
        </ul>
    </div>
</template>

<script>
    import Movie from './Movie.vue'

    export default {
        name: 'MoviesList',
        data() {
            return {
                movies: []
            }
        },
        created: function () {
            this.fetchData()
        },
        methods: {
            fetchData: async function () {
                try {
                    const res    = await fetch('https://api.themoviedb.org/3/discover/movie?primary_release_date.gte=2019-04-01&primary_release_date.lte=2019-04-21&api_key=470b4212d69c36e055c8d232f13bc812');
                    const movies = await res.json();
                    this.movies  = movies.results
                } catch (e) {
                    console.log(e);
                }
            }
        },
        components: {
            Movie,
        }
    }
</script>

<style scoped>
    ul {
        display               : grid;
        list-style            : none;
        padding               : 1rem;
        margin                : 0;
        grid-row-gap          : 1rem;
        grid-template-columns : repeat(6, 1fr);
    }
</style>