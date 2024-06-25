<script setup>
    import { useRouter } from "vue-router";

    const router = useRouter();
    const {blog} = defineProps(["blog"]);

    function detailView(id) {
        router.push(`/blogs/${id}`);
    }
</script>

<template>
    <div class="itemBox">

        
        <label> {{ blog.title }}</label>
        <button class="button1" @click="detailView(blog.id)">조회하기</button>
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
    font-family: 'Ownglyph_jooreeletter-Rg';
    src: url('https://fastly.jsdelivr.net/gh/projectnoonnu/2405-2@1.0/Ownglyph_jooreeletter-Rg.woff2') format('woff2');
    font-weight: normal;
    font-style: normal;
}


.button1 {
    font-family: 'ONE-Mobile-POP', sans-serif;
    font-size: 20px; /* Increase font size */
    padding: 10px 20px; /* Increase padding */
    background-color: #4CAF50; /* Green background */
    color: white; /* White text */
    border: none; /* Remove border */
    border-radius: 12px; /* Rounded corners */
    cursor: pointer; /* Pointer cursor on hover */
    transition: background-color 0.3s, transform 0.3s; /* Smooth transition */
}

.button1:hover {
    background-color: #45a049; /* Darker green on hover */
    transform: scale(1.05); /* Slightly larger on hover */
}

.button1:active {
    background-color: #3e8e41; /* Even darker green on click */
    transform: scale(1); /* Reset scale on click */
}



.itemBox {
    display: flex;
    justify-content: space-between;
    border: 1px solid;
    align-items: center;
    height: 30px;
    margin-top: 2%;
    margin-bottom: 1%;
    border-radius: 10px;
   
}

label {
    margin-left: 1%;
}

button {
    margin-right: 1%;
}
</style>