<template>
  <div v-for="landscape in landscapes" :key="landscape.id">
    
    <div>

      <div class="top-half">
        <img :src="require(`../assets/${landscape.img}`)" alt="LANDSCAPE-picture" />
        <h1>{{landscape.title}}</h1>
      </div>

      <div class="bottom-half">
        <p class="description">{{landscape.description}}</p>
        <div class="date">
          <p>{{landscape.created_at}}</p>
        </div>
      </div>

    </div>

  </div>
</template>

<script>
export default {
  name: 'LandscapeComponent',
  props:['landscapes'],
};
</script>

<style lang="scss" scoped>
</style>

