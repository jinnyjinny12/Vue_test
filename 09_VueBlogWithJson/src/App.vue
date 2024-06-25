<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
<body>
  <header>
    <div >
      <nav>
        <RouterLink to="/">
          <button class="nav-button">전체조회</button>
        </RouterLink>
      
        <RouterLink to="/post">
          <button class="nav-button">등록하기</button>
        </RouterLink>
      </nav>
    </div>
  </header>
  <RouterView />
</body>  
 
</template>

<style scoped>
/* header{
  display: flex;
  flex-direction: column;
  align-items: center;
}*/

a{
  margin-top: 10px;
  margin-left: 20px;
  font-size: 20px;
  display: flex;
  justify-content: center;
  text-decoration-line : none;
}

@font-face {
    font-family: 'HS-Regular';
    src: url('https://gcore.jsdelivr.net/gh/projectnoonnu/noonfonts_2201-2@1.0/HS-Regular.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}

body{
  height: 100dvh;
  background-color: rgba(172, 113, 58, 0.8); /* Add background color with transparency */;
}

header {
  display: row;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 90px;
  background-color: #FFEBB0;
  width: 100%;
}

nav {
  font-family: 'HS-Regular', sans-serif;
  justify-content: flex-end;
  gap: 10px;
  display: flex;
  gap: 10px;
  width: 100%;
  padding-right: 20px;
 
  
}

.nav-button {
  font-family: 'HS-Regular', sans-serif;
  font-size: 30px;
  background-color: #4CAF50; /* Green */
  color: white;
  border: none;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  margin: 4px 2px;
  /* margin-top: 10px; */
  cursor: pointer;
  border-radius: 12px;
  transition: background-color 0.3s, transform 0.3s;
}

.nav-button:hover {
  background-color: #45a049; /* Darker green */
  transform: scale(1.05);
}

.nav-button:active {
  background-color: #3e8e41; /* Even darker green */
  transform: scale(1);
}


</style>
