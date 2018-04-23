<template>
  <div id="toolbar">
    <span class="title">Vue Notebook //</span>
    <span>
      <i @click="addNote" class="glyphicon glyphicon-plus">New</i>
      <i @click="toggleFavorite"
        class="glyphicon glyphicon-pushpin"
        :class="{starred: activeNote.favorite}">Pin</i>
      <i @click="deleteNote" class="glyphicon glyphicon-remove">Delete</i>
    </span>
  </div>
</template>

<script>
  import { addNote, deleteNote, toggleFavorite } from '../vuex/actions'

  export default {
    vuex: {
      getters: {
        activeNote: state => state.activeNote
      },
      actions: {
        addNote,
        deleteNote,
        toggleFavorite
      }
    }
  }
</script>
