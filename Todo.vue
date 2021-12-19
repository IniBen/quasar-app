<template>
  <q-page class="bg-grey-3 column">
  <div class="q-pa-md">
    <div class="q-gutter-sm">
    <q-list class="bg-white">
      <q-item
      v-for="task in tasks" 
      :key="task.title" 
      @click="task.done = !task.done"
      :class="{'done' : task.done}"
      onclick="clickMethod"
      tag="label" v-ripple>
        <q-item-section avatar>
          <q-checkbox v-model="task.done" class="no-pointer-events" color="teal" />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{ task.title }} </q-item-label>
        </q-item-section>
      </q-item>
    </q-list>
    </div>

    <div class="q-px-sm q-mt-sm">
      Your selection is: <strong>{{ color }}</strong>
    </div>
  </div>
  </q-page>
</template>

<script>
// import { defineComponent } from 'vue';

export default ({
  data() {
    return {
      tasks:[
        {
          title: 'create login for ipay',
          done : false
        },
        {
          title: 'push login for ipay',
          done: false
        },
        {
          title: 'create login for newdevz',
          done: false
        }
      ]
    }
  } 
})
</script>

<style land="SCSS">
  .done {
    .q-item__label {
      text-decoration: line-through;
    }
  }
</style>