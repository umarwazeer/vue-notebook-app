<template>
       <div class="row">
            <div  class="col-sm-12 note">
              <div  style="margin: 10px;" class="card">
                <button class="close" @click="$emit('remove', index)">Delete</button>
                <button class="close" @click="saveEdit">Edit</button>
                <div class="card-block notes">
                  <h4 class="card-title">{{note.title}}</h4>
                  <h6 class="card-subtitle mb-3">{{note.date}}</h6>
                  <p class="card-text mb-4">{{note.text}}</p>
                </div>
              </div>
            </div>
          </div>
  </template>
  
<script>

  export default {
    props: {
    note: {
      type: String,
      required: true,
    },
    
    index: {
      type: Number,
      required: true,
    },

    onRemove: {
      type: Function,
      required: true,
    },
    edit: {
      type: Function,
      required: true,
    },
  },
  data(){
    return{
      isEditing: false,
       updatedNote:{}

    }
    },

    methods:{
      saveEdit() {
      this.$emit('edit', this.index, this.updatedNote);
      // this.isEditing = false;
    },
    }

  };
</script>

<style scoped>
body { 
	font-size: 14px;
	min-width: 300px;
	font-family: 'Ubuntu', sans-serif;
  /* background: #F3F3F3; */
	margin: 0;
	-webkit-user-select: none;
	user-select: none;
	padding: 70px 30px 0px 30px;
	font-weight: 100; 
}


.card {
    margin: 20px 0;
    width: 500px;
    /* background: #e7e2e2; */
    border: 10px;
    background: #F3F3F3;

  /* padding: 20px;  */
}

button.btn { 
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
  text-align: left; 
  margin: 15px 0px; 
}

h2 { 
  text-align: left; 
  margin: 15px 0px; 
  color: #b5b5b5; 
}


.card-block{
  /* padding: 0px; */
  text-align: left;
  padding: 10px 0px 0px 20px;

}

h4.card-title { 
    /* margin: 21px 101px 17px 28px;  */
}

h6.card-subtitle{
  color: #6a707a;
  padding:0px 0px 0px 0px;
  /* margin: 0px 0px 0px 0px; */
  
}

p.card-text { 
    /* margin: 25px 0px 0px 0px;  */
}

.card { 
  background: #F3F3F3;
  border-radius: 3px; 
  width: 400px;
  /* padding: 10px; */
  box-shadow: 0px 2px 3px rgb(217, 217, 217); 
}

.alert { 
  /* display: none;  */
}
.form-control[data-v-5cb8db00] {
    width: 500px;
}
.active { 
  display: block; 
}

.col-sm-12 > div {
  max-width: 600px;
  margin: 0px auto; 
}

.card{
    float: left;
    margin-left: 20px;
    margin-top: 50px;
    width: 300px;
    height: auto;
    border-color: 1px #b5b5b5

}
/* @media screen and (min-width: 480px) {
  .card{
    width: 100px;
} */
/* } */
.col-sm-6{
    box-align: left; 
    width: 1100px 
}
.close{
    float: right;
    padding: 5px;
    margin:20px 10px 10px 2px;
}
</style>
   