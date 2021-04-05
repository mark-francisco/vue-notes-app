<template>
  <div class="note-selector" v-on:click="selectNote(note)" v-bind:class="{ active: note === selectedNote }">
    <p class="note-selector-title">{{ note.body }}</p>
    <p class="note-selector-timestamp">{{ note.timestamp }}</p>
  </div>
</template>

<script>
export default {
  props: ["note", "selectedNote"],
  methods: {
    selectNote: function (note) {
      // method in the child component should not mutate props. you should use this.$emit instead.
      // emit means "send this data back." "@parent: please update this data."
      // first argument: name of the fn (the parent version). second argument: the data that you're actually passing back.
      this.selectedNote = note;
    },
  },
};
</script>
