<template>
  <q-layout view="lHh Lpr lFf">
    <q-header bordered class="bg-backgroundPage">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="img:icon.png"
          aria-label="Menu"
          href="https://cider.sh"
        />

        <q-toolbar-title> Cider Store </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>
<style lang="scss" scoped>
.bg-backgroundPage {
  background-color: #111;
}
</style>
<script setup lang="ts"></script>
