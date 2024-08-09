<template>
    <div class="sm:px-32 flex flex-wrap justify-center">
        <VideoCard v-for="video in videos" :key="video.video_id" :videoInfo="video" />
    </div>
</template>

<script>
import VideoCard from '../components/VideoCard.vue';


export default {
    name: "HomeFeed",
    components: {
        VideoCard
    },
    data() {
        return {
            videos: []
        };
    },
    beforeMount() {
        const url = "https://youtube-v2.p.rapidapi.com/channel/search/continuation?query=Anthony&continuation_token=4qmFsgJ3EhhVQ1h1cVNCbEhBRTZYdy15ZUpBMFR1bncaJkNCNFNCbk5sWVhKamFEQUJPQUZnQVdvQWVnTkhRalM0QVFBJTNEWgdBbnRob255mgIpYnJvd3NlLWZlZWRVQ1h1cVNCbEhBRTZYdy15ZUpBMFR1bndzZWFyY2g%253D&channel_id=UCXuqSBlHAE6Xw-yeJA0Tunw&lang=en&country=us";
        const options = {
            method: 'GET',
            headers: {
                'x-rapidapi-key': 'c4821bd756mshf921430d659f930p1db124jsn09c228a08d6f',
                'x-rapidapi-host': 'youtube-v2.p.rapidapi.com'
            }
        }

        fetch(url, options)
            .then((data) => data.json())
            .then((response) => this.videos = response.videos)
    }
}
</script>
 