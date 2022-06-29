<template>
  <div class="bio-container">
    <img class="bio-image" :src="require(`@/assets/${this.user.img}`)" alt="PROFILE PICTURE">
    <div class="bio-summary">{{user.bio}}</div>
    <div class="bio-contact-details">
      {{user.email}}
      {{user.phone}}
      </div>
  </div>
</template>

<script>

export default {
  name: 'UserComponent',
  props: ['user'],
  methods: {

  }
};
</script>

<style lang="scss" scoped>
.bio-container{
height: 50px;
width: 80%;
}
</style>