<template>
<div v-for="landscape in landscapes" :key="landscape.id">

  <a-card hoverable style="width: 300px">
    <template #cover>
      <img
        alt="example"
         :src="require(`../assets/${landscape.img}`)" 
      />
    </template>
    <template #actions>
      <setting-outlined key="setting" />
      <edit-outlined key="edit" />
      <p>{{landscape.created_at}}</p>
    </template>
    <a-card-meta :title="landscape.title" :description="landscape.description">
      <template #avatar>
        <a-avatar src="https://joeschmoe.io/api/v1/random" />
      </template>
    </a-card-meta>
  </a-card>

</div>
</template>

<script>
import { SettingOutlined, EditOutlined } from '@ant-design/icons-vue';
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'LandscapeComponent',
  props:['landscapes'],
  components: {
    SettingOutlined,
    EditOutlined,
  },
});
</script>

<style lang="scss" scoped>

</style>

