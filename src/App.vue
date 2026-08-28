<style>
.btnClass{
  background-color: hotpink;
  padding: 5px 15px;
  border: 1px dotted black;
  color: white;
  margin: 10px;
  border-radius: 5px;
  cursor: pointer;
}

.btnClass:hover{
  background-color: lightpink;
  color: black;
  transform: scale(1.2);
}
</style>

<template>
  <!-- component example -->
  <Navbar />
  <!-- Example of text binding -->
  <h1>{{ message }}</h1>
  <!-- Example of attribute binding -->
  <button :class="btnClass" @click="incrementCounter()">Increment Counter</button>
   <!-- Example of conditional rendering -->
  <div v-show="isVisible">
    Visible Content
  </div>
  <div v-show="!isVisible">
    Unvisible Content
   </div>
   <!-- Example of methods -->
   <h1>Counter : {{ counter }}

   </h1>
   <!-- Example of event handling -->
   <input type="text" placeholder="Type something..." @input="printMessage($event)" />


   <!-- Example of form handling -->

   <Form />

   <!-- Example of computed properties -->
   <Computed />
   <!-- Example of watchers -->
   <Watchers />

   <!-- Example of props -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">

        <ProductCard
            name="Apple"
            :price="355"
            :image="product1"
        />

        <ProductCard
            name="Banana"
            :price="25"
            :image="product2"
        />

        <ProductCard
            name="Mango"
            :price="100"
            :image="product3"
        />

    </div>

</template>
<script setup>
import Navbar from './components/Navbar.vue'
import Form from './components/Form.vue'
import Computed from './components/Computed.vue'
import Watchers from './components/Watchers.vue'
import ProductCard from './components/ProductCard.vue'
import product1 from './assets/product-images/product1.png'
import product2 from './assets/product-images/product2.png'
import product3 from './assets/product-images/product3.png'




import { ref } from 'vue'



const message = 'Hello, Vue!'
const btnClass = 'btnClass'
const isVisible = true;
const counter = ref(0);

// example of methods
function incrementCounter(){
  counter.value++;
}

function printMessage(event){
  console.log(event.target.value);
}
</script>