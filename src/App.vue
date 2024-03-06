<template>
  <app-header></app-header>
  <div class="container">
    <!-- <compContact></compContact> -->
    <compValidate></compValidate>

  </div>
  <app-footer></app-footer>

 
</template>

<script>
// import compContact from './components/contact/index.vue' custom validate
// vee validate
import compValidate from './components/validate/index.vue'
export default{
  components:{
  //  compContact
  compValidate
  }
}
</script>
<style>
body{
    padding: 0;
    margin: 0;
}
.container{
    min-height: 73vh;
    box-sizing: border-box;
    padding: 20px;

}
button{
    padding: 10px;
    background: green;
    cursor: pointer;
    border-radius: 10%;
    border: none;
}
button:hover{
    background: yellow;
}
</style>