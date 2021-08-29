<template>
    <q-list>
        <q-item-label header>{{name}}</q-item-label>
        <q-item clickable tag="a" target="_blank" href="https://quasar.dev" draggable="true" @dragstart="onDragStart">
          <q-item-section avatar>
            <q-icon name="las la-graduation-cap" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Docs</q-item-label>
            <q-item-label caption>quasar.dev</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://github.com/quasarframework/">
          <q-item-section avatar>
            <q-icon name="las la-code" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Github</q-item-label>
            <q-item-label caption>github.com/quasarframework</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://chat.quasar.dev">
          <q-item-section avatar>
            <q-icon name="las la-comments" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Discord Chat Channel</q-item-label>
            <q-item-label caption>chat.quasar.dev</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://forum.quasar.dev">
          <q-item-section avatar>
            <q-icon name="lar la-clipboard" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Forum</q-item-label>
            <q-item-label caption>forum.quasar.dev</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://twitter.com/quasarframework">
          <q-item-section avatar>
            <q-icon name="lab la-twitter" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Twitter</q-item-label>
            <q-item-label caption>@quasarframework</q-item-label>
          </q-item-section>
        </q-item>
        <q-item>
          <q-btn color="primary" label="OK" draggable="true"/>
        </q-item>
    </q-list>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  components: {},
  computed: {}
})

class ComponentList extends Vue {
    name = 'Component List';

    public onDragStart(e: DragEvent):void {
        if (e.dataTransfer == null) {
            return;
        }

        e.dataTransfer.setData('name', 'div');
        console.log(e.dataTransfer.getData('name'));
        console.log(e.dataTransfer);
        console.log(e.target);
    }
}

export default ComponentList;

</script>
