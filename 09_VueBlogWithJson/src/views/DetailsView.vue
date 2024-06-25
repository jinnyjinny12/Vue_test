<script setup>
import { useRoute } from 'vue-router';
import { useBlogStore } from '@/stores/blog'
import { watchEffect, ref } from 'vue';

const route = useRoute();
const blogStroe = useBlogStore();
const modify = ref(true);

watchEffect(() => {
    blogStroe.detailsHandler(route.params.id);
});

const handler = () => {
    blogStroe.modifyHandler({id : route.params.id, ...blogStroe.detailsBlog.value })
}
const deleteMethod = () =>{
    blogStroe.deleteHandler(route.params.id);
}

</script>

<template>
    <div class="blogContainer">
        <div class="titleContainer">
            <h1 class="title" v-if="modify"> {{ blogStroe.detailsBlog.value?.title }}</h1>
            <input v-else v-model="blogStroe.detailsBlog.value.title"/>
           
            
        </div>

      
        <div class="contentContainer" v-if="modify">
            <div class="content">
                {{ blogStroe.detailsBlog.value?.content }}
            </div>
            <div>
                <img class="imgBox" :src="blogStroe.detailsBlog.value?.img" :alt="blogStroe.detailsBlog.value?.title" />
            </div>
        </div>

        

        <div v-else class="button2">
                <button class="styled-button" @click="handler">완료</button>
                <button class="styled-button" @click="() => modify = true">취소</button>
        </div>

        <div v-if="modify" class="button2">
                <button class="styled-button" @click="() => modify = false">수정</button>
                <button class="styled-button"@click="deleteMethod">삭제</button>
        </div>
        <div class="content" v-else>
            <div>
                <textarea v-model="blogStroe.detailsBlog.value.content" ></textarea>
            </div>
            <div class="imgContainer">
                <div>
                    <label> 이미지 url : </label>
                    <input class="imgInput" v-model="blogStroe.detailsBlog.value.img" />
                </div>
                <img class="imgBox" :src="blogStroe.detailsBlog.value.img" :alt="blogStroe.detailsBlog.value.title" />
            </div>
        </div>

        
    </div>
</template>

<style scoped>
@font-face {
    font-family: 'HSSanTokki20-Regular';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/2405@1.0/HSSanTokki20-Regular.woff2') format('woff2');
    font-weight: normal;
    font-style: normal;
}

*{
font-family: 'HSSanTokki20-Regular', sans-serif;
}

.blogContainer {
    display: flex; 
    flex-direction: column;
    background-color: aliceblue;
    border-radius: 10px;
    align-items: center;
    width: 70%;
    height: 700px;
    margin-top: 30px;
    margin-left: auto;
    margin-right: auto;

}

.titleContainer {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    margin-left: auto;
    margin-right: auto;
}

.title {
    width: 30%;
    text-align: center;
}

.contentContainer {
    text-align: center;
    width: 70%;
}

.content {

    text-align: left;
    margin-bottom: 2%;
    border: 1px;
}

textarea {
    width: 100%;
    height: 200px;
}

.imgInput {
    width: 65%;
}

.imgBox {
    width: 300px;
    height: 300px;
}

.imgContainer {
    display: flex;
    flex-direction: column;
}
.button2 {
    display: flex;
    gap: 10px;
    margin-top: 20px;
    margin-bottom: 20px;
}

.styled-button {
    font-family: 'ONE-Mobile-POP', sans-serif;
    font-size: 16px;
    padding: 10px 20px;
    background-color: #4CAF50; /* Green background */
    color: white; /* White text */
    border: none; /* Remove border */
    border-radius: 12px; /* Rounded corners */
    cursor: pointer; /* Pointer cursor on hover */
    transition: background-color 0.3s, transform 0.3s; /* Smooth transition */
}

.styled-button:hover {
    background-color: #45a049; /* Darker green on hover */
    transform: scale(1.05); /* Slightly larger on hover */
}

.styled-button:active {
    background-color: #3e8e41; /* Even darker green on click */
    transform: scale(1); /* Reset scale on click */
}
</style>