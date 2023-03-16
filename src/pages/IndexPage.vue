<template>
  <q-page class="bg-gray-3 column">
    <q-list class="bg-white" separator bordered>
      <q-item
        v-ripple
        v-for="task in tasks"
        :key="task.title"
        @click="task.done = !task.done"
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
