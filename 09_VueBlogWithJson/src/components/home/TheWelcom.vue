<script setup>
import BlogItem from "./BlogItem.vue";
import {useBlogStore} from "../../stores/blog";
import {onMounted, provide} from "vue";

const blogStore = useBlogStore();

onMounted(()=>{
    blogStore.blogHandler();
})
</script>

<template>
    <div v-for="blog in blogStore.blogs" class="listBox">
        
            <BlogItem :key="blog.id" :blog="blog" class="listTag"></BlogItem>    
        
        
    </div>

</template>

<style scoped>
@font-face {
    font-family: 'ONE-Mobile-POP';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/noonfonts_2105_2@1.0/ONE-Mobile-POP.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}




@font-face {
    font-family: 'HSSanTokki20-Regular';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/2405@1.0/HSSanTokki20-Regular.woff2') format('woff2');
    font-weight: normal;
    font-style: normal;
}

.listBox{
    font-family: 'HSSanTokki20-Regular' , sans-serif;
    font-size: 50px;
    width: 70%;
    font-size: 20px;
    
    
}

.listTag{
    background-color: aliceblue;
    height: 50px;
}


</style>