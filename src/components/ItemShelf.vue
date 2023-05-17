<template>
  <div class="itemShelf">
    <div class="header">
      <span class="title"> {{ props.title }} </span>
      <q-space />
      <q-btn rounded icon="arrow_forward" label="View All" />
    </div>
    <div class="items-container">
      <q-card
        class="item"
        v-for="item in items"
        :key="item.id"
        :to="item.link"
        clickable
      >
        <q-card-section>
          <q-img :src="item.image" />
        </q-card-section>
        <q-card-section>
          <q-card-title>{{ item.title }}</q-card-title>
          <q-card-main>{{ item.description }}</q-card-main>
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.itemShelf {
  width: 100%;
  max-width: 1400px;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  padding: 1rem;
  .header {
    width: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: flex-start;
  }
  .title {
    font-size: 1.5rem;
    font-weight: 500;
  }
  .items-container {
    width: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: flex-start;
    flex-wrap: wrap;
    .item {
      width: 100%;
      max-width: 300px;
      margin: 1rem;
    }
  }
}
</style>
<script setup lang="ts">
import { defineProps, withDefaults } from 'vue';

export interface ItemShelfProps {
  title: string;
}

const props = withDefaults(defineProps<ItemShelfProps>(), {
  title: 'Item Shelf',
});

const items = [
  {
    id: 1,
    title: 'Item 1',
    description: 'This is the first item',
    image: 'https://cdn.quasar.dev/img/parallax2.jpg',
    link: '#',
  },
  {
    id: 2,
    title: 'Item 2',
    description: 'This is the second item',
    image: 'https://cdn.quasar.dev/img/parallax2.jpg',
    link: '#',
  },
  {
    id: 3,
    title: 'Item 3',
    description: 'This is the third item',
    image: 'https://cdn.quasar.dev/img/parallax2.jpg',
    link: '#',
  },
  {
    id: 4,
    title: 'Item 4',
    description: 'This is the fourth item',
    image: 'https://cdn.quasar.dev/img/parallax2.jpg',
    link: '#',
  },
];
</script>
