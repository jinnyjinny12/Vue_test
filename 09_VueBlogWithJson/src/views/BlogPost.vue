<script setup>
import { useRoute } from "vue-router";
import { useBlogStore } from '../stores/blog';
import { watchEffect, ref } from "vue";

const { postBlog, postHandler } = useBlogStore();

const handler = () => {
    postHandler(postBlog);
}
</script>

<template>
    <div class="blogContainer">
        <div class="titleContainer">
            <input v-model="postBlog.title" placeholder="제목을 입력해주세요" class="" />
        </div>
        <div class="content">
            <div>
                <textarea v-model="postBlog.content"></textarea>
            </div>
            <div class="imgContainer">
                <div>
                    <label> 이미지 url : </label>
                    <input class="imgInput" v-model="postBlog.img" />
                </div>
                <template v-if="postBlog.img">
                    <img class="imgBox" :src="postBlog.img" />
                </template>
            </div>
        </div>
       
            <button class="styled-button" @click="handler">등록하기 </button>
               
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

.blogContainer {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 70%;
    height: 700px;
    margin-left: auto;
    margin-right: auto;

}

.titleContainer {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    margin-top: 3%;
    margin-bottom: 2%;
    margin-left: auto;
    margin-right: auto;
}

.title {
    width: 40%;

    text-align: center;
    border-bottom: 1px solid;
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
</style>