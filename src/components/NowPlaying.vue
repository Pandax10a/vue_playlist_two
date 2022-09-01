<template>
    <div>
        <h1>Playing:</h1>
        <!-- needed key index so it updates -->
        <section :key="index">
            <h3>{{now_playing[0].title}}</h3>
            <h3>{{now_playing[0].artist}}</h3>
            <img :src="now_playing[0].image_url">
        </section>
    </div>
</template>

<script>
    export default {
        methods: {
            current_playing(song) {
                // using splice to remove the first empty or the object already there to keep it having only 1 object in array
                this.now_playing.splice(0, 1)
                this.now_playing.push(song)
                console.log(`this is in now playing` + song)
            }
        },
        mounted () {
           this.$root.$on(`prepping_play`, this.current_playing) ;
        },
        data() {
            return {
                // the splice function didnt work well without the the first empty object
                now_playing: [{}]
            }
        },
        name: 'now-playing'
    }
</script>

<style scoped>

</style>