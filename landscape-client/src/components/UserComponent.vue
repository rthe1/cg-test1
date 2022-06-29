<template>
  <div style="background: #ececec; padding: 30px">
    <a-card :title="user.name" :bordered="false" style="width: 70vw">
      <div class="card">
      <div class="picture">
      <!-- <img style="width: 25px height: 25px" :src="require(`../assets/${user.img}`)"  alt="profile-picture"> -->
      </div>
      <div class="details">
      <p>{{user.bio}}</p>
      <p>{{user.phone}}</p>
      <p>{{user.email}}</p>
      </div>
      </div>
    </a-card>
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
img{
height: 150px;
width: 150px;
}

.card{
  display: flex;
  flex-direction: row;
  justify-content: space-between;

}
</style>