<template>
    <RouterLink :to="`video/${videoInfo.video_id}`">
        <div 
        class="w-40 h-44 m-2 p-2 rounded-xl bg-white shadow-lg"
        @mouseover="isHovering=true"
        @mouseleave="isHovering=false" 
    >
        <img :src="videoInfo.thumbnails[0].url" alt="thumbnail" class="rounded-xl" />
        <h3 class="title my-2 text-xxs">{{ videoInfo.title }}</h3>
        <h4 class="text-xxs">Herman87</h4>
        <p class="text-xxs">{{ videoInfo.number_of_views }} views - {{ videoInfo.published_time }}</p>
    </div>
    </RouterLink>
</template>

<script>

export default {
    name: "VideoCard",
    props: {
        videoInfo: Object,
    },
    data() {
        return {
            isHovering: false,
        }
    }
}
</script>

<style>
    .title {
        display: -webkit-box;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: 2;
        overflow: hidden;
        text-overflow: ellipsis;
        line-height: 1.5em;
        font-weight: bolder;
    }
</style>
