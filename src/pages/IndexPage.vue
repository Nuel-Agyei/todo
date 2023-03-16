<template>
  <q-page class="bg-gray-3 column">
    <q-list class="bg-white" separator bordered>
      <q-item
        v-ripple
        v-for="task in tasks"
        :key="task.title"
        @click="task.done = !task.done"
        :class="{ 'done bg-green-2': task.done }"
        clickable
      >
        <q-item-section avatar>
          <q-checkbox
            v-model="task.done"
            class="no-pointer-events"
            color="primary"
          />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{ task.title }}</q-item-label>
        </q-item-section>
        <q-item-section v-if="task.done" side>
          <q-btn-flat round dense color="primary" icon="delete" />
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  data() {
    return {
      tasks: [
        {
          title: "Get bananas",
          done: false,
        },
        {
          title: "Eat bananas",
          done: false,
        },
        {
          title: "poop",
          done: false,
        },
      ],
    };
  },
  //  name: "IndexPage",
});
</script>

<style lang="scss">
.done {
  q-item__label {
    text-decoration: line-through;
    color: #a90000;
  }
}
</style>
<div class="q-item__label">poop</div>
