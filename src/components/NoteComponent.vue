<template>
       <div class="row">
            <div class="col-sm-6 note">
              <div class="card">
                <button class="close" style="" @click="$emit('remove', index)">&times;</button>
                <button class="close" style="" @click="$emit('edite', index)">&times;</button>
                <div class="card-block notes">
                  <h4 class="card-title">{{note.title}}</h4>
                  <h6 class="card-subtitle mb-2 text-muted">{{note.date}}</h6>
                  <p class="card-text">{{note.text}}</p>
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
  },
  data(){
    return{

    }
    },

    methods:{
    }

  };
</script>

<style scoped>
body { 
	font-size: 14px;
	min-width: 300px;
	font-family: 'Ubuntu', sans-serif;
    background: #c0bebe;
	margin: 0;
	-webkit-user-select: none;
	user-select: none;
	padding: 70px 30px 0px 30px;
	font-weight: 100; 
}

.card {
    margin: 20px 0;
    background: #e7e2e2;
    border: 10px;
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

.alert { display: none; 
}

.active { display: block; 
}

.col-sm-12 > div {
  max-width: 600px;
  margin: 0px auto; 
}

.card{
    float: left;
    margin-left: 20px;
    margin-top: 50px;
    width: 200px;
    height: 150px;
    border-color: 1px #b5b5b5

}

.col-sm-6{
    box-align: left;
    width: 1100px
}
.close{
    float: right;
    padding: 10px;
    margin: 10px;
}
</style>
   