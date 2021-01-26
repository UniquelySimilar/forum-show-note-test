<template>
  <div>
    <h3>Note List</h3>
    <ul>
      <li v-for="note in notes" :key="note.id">
        {{ note.title }}
        <button class="show-btn" @click="showDetail(note.id)">Show Detail on page</button>
        <button class="show-btn" @click="showModal(note.id)">Show Detail in Modal</button>
      </li>
    </ul>
    <note-detail
      v-if="displayDetail"
      :note="selectedNote"
      @hide-detail-event="hideDetail"
      />
    <note-detail-modal
      v-if="displayModal"
      :note="selectedNote"
      @close-modal-event="hideModal" />
  </div>
</template>

<script>
  import NoteDetail from '@/components/NoteDetail'
  import NoteDetailModal from '@/components/NoteDetailModal'

  export default {
    name: 'NoteList',
    components: {
      NoteDetail,
      NoteDetailModal
    },
    data() {
      return {
        displayModal: false,
        displayDetail: false,
        selectedNoteId: 0,
        notes: [
          {
            id: 1,
            title: "1st Note",
            body: "Body of note 1",
            date: "10/17/20",
            isSelected: true,
          },
          {
            id: 2,
            title: "2nd Note",
            body: "Body of note 2",
            date: "11/17/20",
            isSelected: false,
          },
          {
            id: 3,
            title: "3rd Note",
            body: "Body of note 3",
            date: "12/17/20",
            isSelected: false,
          }
        ]
      }
    },
    computed: {
      selectedNote() {
        return this.notes.filter( note => {
          return note.id === this.selectedNoteId;
        })[0];
      }
    },
    methods: {
      showModal(id) {
        //console.log('showModal for id: ' + id);
        this.selectedNoteId = id;
        this.displayModal = true;
      },
      hideModal() {
        this.displayModal = false;
      },
      showDetail(id) {
        this.selectedNoteId = id;
        this.displayDetail = true;
      },
      hideDetail() {
        this.displayDetail = false;
      }
    }
  }
</script>

<style scoped>
  .show-btn {
    margin-left: 1em;
  }

</style>