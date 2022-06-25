<template>
  <div id="app">
    <div class="ui fixed inverted menu vue-color">
      <div class="ui container">
        <a href="#" class="header item">Vue Js CRUD with Laravel API</a>
      </div>
    </div>

    <div class="ui main container">
      <MyForm />
      <Loader v-if="loader"/>
      <CustomerList 
        :customers = "customers" 
        @onDelete="onDelete"
      />

    </div>
  </div>
</template>

<script>
import axios from "axios";
import MyForm from './components/MyForm.vue';
import CustomerList from './components/CustomerList.vue';
import Loader from "./components/Loader.vue";
// import { assertExpressionStatement } from '@babel/types';

export default {
  name: 'App',
  components: {
    MyForm,
    CustomerList,
    Loader
  },
  data(){
    return {
      url: "http://127.0.0.1:8000/api/customers",
      customers: [],
      loader: false
    };
  }, 
  methods:{
    getCustomers(){
      this.loader = true;

      axios.get(this.url).then(data =>{
        this.customers = data.data;
        this.loader = false;
      });
    },

    deleteCustomer(id) {
      this.loader = true;
      axios
        .delete(`${this.url}/${id}`)
        .then(() => {
          this.getCustomers();
        })
        .catch(e => {
          alert(e);
        });
    },

    onDelete(id){
      // window.console.log("app delete " + id);
      this.deleteCustomer();
    }
  },
  created(){
    this.getCustomers();
  }
}
</script>

<style>
.vue-color {
  background: #41b883 !important;
}
.main.container{
  margin-top: 60px;
}
.submit-button{
  margin-top: 24px !important;
  float: right;
}
.data{
  margin-top: 15px;
}
thead tr th{
  background: #e0e0e0 !important;
}
.ui.inverted.dimmer{
  background-color: rgba(255, 255, 255, 0) !important;
}
</style>
