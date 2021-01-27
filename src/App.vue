<template>
  <div id="app" class="container-fluid">
    <note-list />
  </div>
</template>

<script>
  import NoteList from '@/components/NoteList'

  export default {
    name: 'App',
    components: {
      NoteList
    }
  }
</script>

<style>
  .list-title {
    font-size: 1.75rem;
    font-weight: bold;
  }

</style>