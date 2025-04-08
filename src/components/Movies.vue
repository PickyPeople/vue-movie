<template>
  <h1>영화 정보</h1>
  <div v-for="(movie, i) in data" :key="i" class="item">
    <!--v-for은 데이터를 반복을 할 때 쓰인다.-->
    <figure>
      <img :src="`${movie.imgUrl}`" :alt="movie.title" />
    </figure>
    <div class="info">
      <h3 class="bg-yellow" :style="textRed">{{ movie.title }}</h3>
      <p>개봉: {{ movie.year }}</p>
      <p>장르: {{ movie.category }}</p>
      <button @:click="increaseLike(i)">좋아요</button>
      <span>{{ movie.like }}</span>
      <p>
        <button @click="isModal=true; selectedMovie= i" >상세보기</button>
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    name: "MoviesComponent",
    props: {
      data: Array
    }
  }
</script>

<style>
</style>