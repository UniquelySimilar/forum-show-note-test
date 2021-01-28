<template>
  <div class="note-detail-modal">

    <div class="modal-dialog-content">
      <div class="modal-dialog-header">
        <h4>Note Detail</h4>
        <hr>
      </div>
      <div class="modal-dialog-body">
        <span class="label">ID:</span>{{ note.id }}<br>
        <span class="label">TITLE:</span>{{ note.title }}<br>
        <span class="label">BODY:</span>{{ note.body }}<br>
        <span class="label">DATE:</span>{{ note.date }}
      </div>
      <div class="modal-dialog-footer">
        <div class="btn-wrapper">
          <button type="button" class="btn btn-secondary btn-sm close-btn" @click="closeModal">Close</button>
        </div>
      </div>
    </div>

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
      closeModal() {
        this.$emit('close-modal-event');
      },
    }
  }
</script>

<style scoped>
  .note-detail-modal {
    position: fixed;
    /* Stay in place */
    z-index: 1;
    /* Sit on top */
    left: 0;
    top: 0;
    width: 100%;
    /* Full width */
    height: 100%;
    /* Full height */
    overflow: auto;
    /* Enable scroll if needed */
    background-color: rgb(0, 0, 0);
    /* Fallback color */
    background-color: rgba(0, 0, 0, 0.4);
    /* Black w/ opacity */
  }

  .modal-dialog-content {
    background-color: #fefefe;
    margin: 10% auto;
    padding: 20px;
    border: 1px solid #888;
    border-radius: 0.3rem;
    width: 80%;
  }

  .modal-dialog-footer {
    text-align: center;
  }

  .close-btn {
    margin-left: 1em;
  }

  .label {
    font-weight: bold;
    margin-right: 1em;
  }

  @media only screen and (min-width: 576px) {
    .modal-dialog-content {
      width: 60%
    }
  }

  @media only screen and (min-width: 768px) {
    .modal-dialog-content {
      width: 40%
    }
  }
</style>