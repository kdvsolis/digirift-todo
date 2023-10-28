<template>
  <v-list-item>
    <v-list-item-action>
        <v-checkbox v-model="todo.done" style="border: 1px solid black;" @change="$emit('change')"></v-checkbox>
    </v-list-item-action>
    <v-list-item-content>
      <v-list-item-title style="color: black">{{ todo.text }}</v-list-item-title>
    </v-list-item-content>
  </v-list-item>
</template>

<script>
export default {
  props: ['todo'],
}
</script>