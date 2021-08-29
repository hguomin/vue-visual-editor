<template>
  <q-layout view="hHh Lpr lFf">
    <q-header elevated class="flat">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
          icon="las la-bars"
        />

        <q-toolbar-title>
          The Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      class="bg-grey-2"
    >
      <component-list />
    <!--

      -->
    </q-drawer>

    <q-page-container>
      <HelloWorld />
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from 'vue'
import ComponentList from './components/ComponentList.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'LayoutDefault',

  components: {
    ComponentList,
    HelloWorld
  },
  setup () {
    return {
      leftDrawerOpen: ref(false)
    }
  }
}
</script>
