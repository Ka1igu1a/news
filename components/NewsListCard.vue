<template>
    <div class="max-w-[60rem] max-h-[20rem] flex overflow-clip">
        <img :src="cardInfo.image === '' ? require('../static/card-tmp-img.png') : cardInfo.image" alt="card-tmp-img" class="w-[20rem] h-[20rem] mr-[1.6rem] rounded-2xl">
        <div>
            <span class=" text-[1.3rem] leading-[1.8rem] text-opacity-50">{{cardInfo.datePublish}}</span>
            <p class="my-[1rem] text-[2rem] leading-[2.2rem] text-[#1D5AB6] hover:(cursor-pointer)">{{cardInfo.title}}</p>
            <span class="text-[1.6rem] leading-[2.2rem]">{{cardInfo.shortText}}</span>
        </div>

    </div>
</template>

<script>
export default {
    name: 'NewsListCard',
    props: ['cardInfo'],
}
</script>

<style scoped>
    
</style>