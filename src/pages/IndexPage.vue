<template>
  <q-page class="column items-center justify-evenly">
    <h1>Cider Store</h1>
    <q-input
      filled
      class="searchBar"
      v-model="text"
      placeholder="Search for awesome themes and plugins here"
      autogrow
      :dark="darkMode"
      debounce="500"
    >
      <template v-slot:prepend>
        <q-icon name="search" />
      </template>
    </q-input>
    <item-shelf title="Featured Themes" />
    <item-shelf title="Featured Plugins" />
  </q-page>
</template>
<style lang="scss" scoped>
.searchBar {
  width: 50%;
  max-width: 500px;
  border-radius: 100vmax;
  overflow: hidden;
}
</style>
<script setup lang="ts">
import { ref } from 'vue';
import { useQuasar } from 'quasar';
import ItemShelf from 'src/components/ItemShelf.vue';
const $q = useQuasar();
console.log($q.dark.isActive);
$q.dark.set(true);
let darkMode = ref<boolean>($q.dark.isActive);
let text = ref<string>('');
</script>
