<template>
<div id="app">
    <div class="container">
      <div class="row">
        <div class="col-sm-12">
            <div class="form">
              <div class="form-group">
                <label>Note Title</label>
                <input class="form-control" type="text" v-model="notes.title" required>
              </div>
              <div class="form-group">
                <label>Note Text</label>
                <textarea rows="3" class="form-control" v-model="notes.text" required></textarea>
              </div>
              <button class="btn btn-primary" @click="addNote">Save Note</button>
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
   
  data(){
    return {
           notes:{
            text: "",
            title: "",
            date: Date.now(),

           }
    }
  },

  methods:{

    addNote() {
        this.$emit("addNote", this.notes)
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
button.btn { 
    padding-bottom: 40px;
	display: block; 
	padding: 15px 20px;
	font-family: 'Ubuntu', sans-serif;
	margin: 15px 0px;
  width: 100%;
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
h3 { 
  text-align: center; 
  font-size: 14px;
  margin: 30px 0px 30px 0px; 
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
    width: 500px,
}
.form-group{
    padding-top: 30px;
}
.form-control{
    width: 500px;
}
.form-control[type='text']{
    height: 30px;
    outline-offset:30rem;
}
.form-control{
    outline-offset:30rem;
}

</style>