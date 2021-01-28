<template>
  <div class="note-detail">
    <div class="row">
      <div class="col-lg-6 col-md-8 col-sm 12">

        <div class="row">
          <div class="col-12">
            <span class="list-title">Note Detail</span>
          </div>
        </div>
  
        <div class="row">
          <div class="col 12">
            <table class="table table-bordered">
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
          </div>
        </div>
  
      </div>
    </div>
    <button class="btn btn-secondary btn-sm" @click="hideDetail">Hide Detail</button>
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
  .table th, .table td {
    padding: 0.25rem;
  }
</style>