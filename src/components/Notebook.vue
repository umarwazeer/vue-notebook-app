<template>
    <div class="">
      <h3>NotePade</h3>
      <h3>Total tasks: {{ notes.length }}</h3>
      <NoteForm @add-note="addNote" />
      <div class="row">
        <div class="card">
          <div class="" >
            <NoteComponent
              v-for="(note, index) in notes"
              :key="index"
              :note="note"
              :index="index"
              @remove="removeNote"
            />
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import NoteComponent from './NoteComponent.vue';
  import NoteForm from './NoteForm.vue';
  
  export default {
  name:'NoteBookComponent',
    components: { 
      NoteComponent, 
      NoteForm 
    },
    data() {
      return {
        notes: []
      };
    },
    mounted(){
      this.getNotes()
    },

    methods: {
      getNotes(){
        const noteitem = JSON.parse(localStorage.getItem("notesData"));
        if (noteitem) {
          this.notes = noteitem;
        }
        console.log("noteitem", noteitem);
      },

    addNote(note) {
      this.notes.push(note);
      localStorage.setItem('notesData', JSON.stringify(this.notes));
    },

    removeNote(index) {
      this.notes.splice(index, 1);
      localStorage.setItem('notesData', JSON.stringify(this.notes));
      this.getNotes()
    },
    },
  };
  </script>