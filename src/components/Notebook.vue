<template>
    <div class="">
      <h3>Vue NotePade-App</h3>
      <h3 class="spam">Total tasks: {{ notes.length }}</h3>
      <NoteForm v-if="isEditing" :noteData="currentNote" :isEdit="isEditing" @submit="updateNote" />
      <NoteForm v-else @submit="addNote" />      
      <div class="row">
        <div class="card">
          <div class="" >
            <NoteComponent
              v-for="(note, index) in notes"
              :key="index"
              :note="note"
              :index="index"
              @remove="removeNote"
              @edit="startEditNote"
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
        notes: [],
        isEditing: false,
        currentNote: null,
        currentNoteIndex: null,
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
      if(note.title && note.text){
      this.notes.push(note);
      localStorage.setItem('notesData', JSON.stringify(this.notes));
      note.title = null
      note.text = null
    }
    else{
      alert("the cunrrent field is required..")
    }
  },

    removeNote(index) {
      this.notes.splice(index, 1);
      localStorage.setItem('notesData', JSON.stringify(this.notes));
      this.getNotes()
    },
    startEditNote(index) {
      this.isEditing = true;
      this.currentNote = { ...this.notes[index] };
      this.currentNoteIndex = index;
    },
    updateNote(updatedNote) {
      this.notes.splice(this.currentNoteIndex, 1, updatedNote);
      localStorage.setItem('notesData', JSON.stringify(this.notes));
      this.isEditing = false;
      this.currentNote = null;
      this.currentNoteIndex = null;
      this.getNotes()
    },
    },
  };
  </script>
<style scoped>
.body{
  /* background: #F3F3F3; */
}
h3{
  text-align: center;
}
h3.spam{
  margin: 0px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  text-align: center;
  font-style:unset;
  font-size:24px;
  color: rgb(78, 77, 75)

}

</style>
