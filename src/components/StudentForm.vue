<template>
<h1> {{title}}</h1>
<form v-bind:style="{background: activeColor}">
    <label for="Studentname">Studentname</label>
    <input type="text" required v-model="name">

     <label for="email">EMAIL:</label>
    <input type="email" required v-model="email">
       <label for="age">AGE:</label>
    <input type="number" required v-model="age">
    <label for="role">CERITIFICATE:</label>
    <select v-model="certificate">
      <option value="common entrance">common entrance</option>
      <option value="GEC ordinary ">GEC ordinary level</option>
      <option value="GCE Advanced ">GCE Advanced level</option>
    </select>

    <div class="trems">
      <input type="checkbox" v-model="terms" required>
      <label for="checkbox"> accept terms and conditions</label>
    </div>
    <div class="submit" >
      <button v-on:click="submit">Submit Student Form</button>
    </div>
  </form>
  <div class="bag">
    <h2>Preview</h2>
    <hr>
  <p>name:{{name}}</p>
  <p>email:{{email}}</p>
  <p>age:{{age}}</p>
  <p>certificate:{{certificate}}</p>
  <P>terms accepted:{{terms}}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      certificate: '',
      terms: false,
      age: '',
      title: 'Student Form',
      activeColor: 'white',
    };
  },
  methods: {
    submit(event) {
      event.preventDefault();
      this.title = 'form is now submitted and no otherr changes can be made.';
      this.activeColor = 'lightgrey';
    },

  },

};
</script>

<style>
h1{
  color: #5695f3;
}
form{
  max-width: 420px;
  margin: 30px auto;
  text-align: center;
  padding: 40px;
  border-radius: 10px;
}
label{
  color: #aaa;
  display: inline-block;
  margin:25px 0 15px;
  font-size: 0.8em;
  text-transform:uppercase;
  letter-spacing:1px;
  font-weight: bold;
}
input{
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing:border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color:#555;
}
select{
  display: block;
  padding: 10px 6px;
  width: 100%;
  color:#555;
  margin: 0 auto;
  border: 2px solid #ddd;
  border-radius: 10px;
}
option {
  text-align: center;
  font-size: 16px;

}
input[type="checkbox"]{
  display: inline-block;
  width: 16px;
  margin: 0 10 0 0;
  position: relative;
  top: 2px;
  left: -2px;
  border:1px solid #ddd;
}
.bag{
background: #ddd;
width: 99%;
margin: 0 auto;
border-radius: 6px;
padding: 10px 6px;
color:#FFF;
}
hr{
  width: 30%;
  border: 2px solid #fff;
}
button{
  background: #417eda;
  border:0;
  padding: 10px 20px;
  margin-top: 20px;
  color:#FFF;
  border-radius: 10px;
  transition:0.5s
}
.submit{
  text-align: center;
}
button:hover{
  opacity: 0.8;
  transition:0.5s
}
</style>
