<template>
  <q-page class="flex flex-center" @drop="onDrop" @dragover="onDragOver">
    <img alt="Quasar logo" src="../assets/logo.svg" style="width: 200px; height: 200px">
    <div>
      <q-btn color="primary" label="+" @click="increment" />
      <q-btn color="primary" label="-" @click="decrement" />
      <p>
        {{count}}
      </p>
    </div>
  </q-page>
</template>

<style>
</style>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import store from '@/store';
export default class HelloWorld extends Vue {
    private name = 'HelloWorld';
    private count = 0;

    public increment(): void {
        // this.count++;
        store.commit('increment');
    }

    public decrement(): void {
        // this.count--;
        this.count = store.state.count;
    }

    public onDragOver(e: DragEvent): void {
      // prevent default to allow drop
      e.preventDefault();
    }

    public onDrop(e: DragEvent): void {
        e.preventDefault();
        e.stopPropagation();
        console.log(e.dataTransfer);
        if (e.dataTransfer == null) {
            return;
        }

        console.log('Drop Event: ' + e.dataTransfer.getData('name'));
    }
}
</script>
