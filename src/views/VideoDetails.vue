<template>
    <div class="px-8 flex flex-col items-center">
        <div class="video-container sm:w-2/3 w-4/5">
            <iframe 
                :src="`https://youtube.com/embed/${$route.params.id}`"
                class="video rounded-xl shadow-lg"
            >

            </iframe>
        </div>
        <h3 class="mt-4  text-center text-lg">{{ videoInfo.title }}</h3>
    </div>
</template>

<script>
    export default {
        name: "VideosDetails",
        data() {
            return {
                videoInfo: [],
            }
        },
        beforeMount() {
        const url = "https://youtube-v2.p.rapidapi.com/video/data?video_id="+ this.$route.params.id;
        const options = {
            method: 'GET',
            headers: {
                'x-rapidapi-key': 'c4821bd756mshf921430d659f930p1db124jsn09c228a08d6f',
                'x-rapidapi-host': 'youtube-v2.p.rapidapi.com'
            }
        }

        fetch(url, options)
            .then((data) => data.json())
            .then((response) => {
                    this.videoInfo = response
                    console.log(response)
                }
            )
    }
    }
</script>

<style>
    .video-container {
        padding-top: 40%;
        position: relative;
        margin: 0 auto 10px auto;
    }
    .video {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
    } 
</style>
