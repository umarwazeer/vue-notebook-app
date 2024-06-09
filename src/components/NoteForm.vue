<template>
<div id="app">
    <div class="container">
      <div class="row">
        <div class="col-sm-12">
            <div class="form">
              <div class="form-group">
                <label>Note Title*</label>
                <input class="form-control" type="text" v-model="note.title" required>
              </div>
              <div class="form-group">
                <label>Note Text*</label>
                <textarea type="textarea" rows="3" class="form-control" v-model="note.text" required></textarea>
              </div>
              <!-- <button type="submit" @click="submit">{{ isEdit ? 'Update Note' : 'Add Note' }}</button> -->
              <button class="btn btn-primary" @click="addNote">{{ isEdit ? 'Update Note' : 'Add Note' }}</button>
              <!-- <div class="alert alert-danger text-center" role="alert" v-bind:class="{ active: isActive }">All fields are Required</div> -->
            </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NoteForm',
  props: {
    noteData: {
      type: Object,
      default: () => ({ title: '', date: new Date().toISOString(), text: '' }), // Ensure a default note structure
    },
    isEdit: {
      type: Boolean,
      default: false,
    },
  },

   
  data(){
    return {
      note: { ...this.noteData },

    }
  },

  methods:{

    addNote() {
        // this.$emit("addNote", this.notes)
        this.$emit('submit', this.note);

    }
}
}
</script>


<style scoped>
body { 
	font-size: 14px;
	min-width: 300px;
	font-family: 'Ubuntu', sans-serif;
	background: #f3f3f3;
	margin: 0;
	-webkit-user-select: none;
	user-select: none;
	padding: 70px 30px 0px 30px;
	font-weight: 100; 
}
.card {
  margin: 20px 0;
  background: #ffffff;
  border: 10px;
  padding: 20px; 
}
.container{
  align-items: center;
}
label{
  font-size: 17px;
  font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-weight: 50;

  /* margin-bottom: 20px; */
  /* margin-left: 20px; */
}
button.btn { 
  padding-bottom: 40px;
	display: block; 
	padding: 15px 20px;
	font-family: 'Ubuntu', sans-serif;
	margin: 15px 0px;
  width: 608px;
	box-shadow: 0px 1px 3px rgb(217, 217, 217);
	border: none; 
	border-radius: 2px; 
}
h1 { 
  text-align: center; 
  margin: 15px 0px; 
}
h2 { 
  text-align: center; 
  margin: 15px 0px; 
  color: #b5b5b5; 
}
h4.card-title { 
    margin: 5px 0px 15px 0px; 
}
p.card-text { 
    margin: 25px 0px 0px 0px; 
}
.card { 
  border-radius: 3px; 
  box-shadow: 0px 2px 3px rgb(217, 217, 217); 
}
.alert { 
    display: none; 
}
.active { 
    display: block; 
}
.col-sm-12 > div {
    max-width: 600px;
    margin: 0px auto; 
    }
.btn {
    margin-bottom: 30px;
    background-color: indigo;
    color:#ffffff
}
.btn:hover{
    background-color: rgb(32, 1, 54);
    font-size: 15px
}
.form{
    width: 500px;
    padding-top: 0px;
}
.form-group{
    padding-top: 20px;
}
.form-control{
    width: 600px;
    outline-offset:30rem;
    margin-top: 5px;

}
.form-control[type='text']{
    height: 30px;
    outline-offset:30rem;
}
.form-control[type='textarea']{
    height: 100px;
    outline-offset:30rem;
}
.form.label{
  text-align: left;
}
</style>