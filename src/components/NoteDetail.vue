<template>
  <div class="note-detail">
    <h3>Note Detail</h3>
    <table>
      <thead>
        <th>ID</th>
        <th>TITLE</th>
        <th>BODY</th>
        <th>DATE</th>
      </thead>
      <tbody>
        <td>{{ note.id }}</td>
        <td>{{ note.title }}</td>
        <td>{{ note.body }}</td>
        <td>{{ note.date }}</td>
      </tbody>
    </table>
    <button @click="hideDetail">Hide Detail</button>
  </div>
</template>

<script>
  export default {
    props: {
      note: {
        type: Object,
        required: true
      },
    },
    methods: {
      hideDetail() {
        this.$emit('hide-detail-event');
      },
    }
  }
</script>

<style scoped>
  table,
  th,
  td {
    border: 1px solid black;
  }

  button {
    margin-top: 1em;
  }
</style>