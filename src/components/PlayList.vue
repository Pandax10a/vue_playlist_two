<template>
    <div>
        <h1> Your current Play List:</h1>
        <section v-for="(list,index) in playlist" :key="index">
            <p>{{list}}</p>
        </section>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                playlist: [{
                     title: "",
                    artist: "",
                    song_id: "",
                    image_url:""

                }]
            }
        },
        methods: {
            the_playlist(song) {
                song
                this.playlist.push(song)
                
            }
        },
        mounted () {
            this.$root.$on(`put_into_playlist`, this.the_playlist);
        },
        name: 'play-list'
    }
</script>

<style scoped>

</style>