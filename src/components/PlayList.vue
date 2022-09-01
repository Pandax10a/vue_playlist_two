<template>
    <div>
        <h1> Your current Play List:</h1>
        <article v-if="isFilled">
        <section v-for="(list,index) in playlist" :key="index" @click="move_to_play(index)">
            <p>{{index+1}}. {{list.title}}</p>
        </section>
        </article>
        <article v-else>
            <p>Pick some songs from above to add to play list</p>
        </article>
        

    </div>
</template>

<script>
    export default {
        data() {
            return {
                playlist: [
                   

                ],
                isFilled: false
            }
        },
        methods: {
            the_playlist(song) {
                song
                this.playlist.push(song)
                console.log(song)
                
            },
            move_to_play(i) {
                this.$root.$emit(`prepping_play`, this.playlist[i])
               this.isFilled = true
                
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