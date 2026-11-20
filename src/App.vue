<style>
.btnClass {
  background-color: hotpink;
  padding: 5px 15px;
  border: 1px dotted black;
  color: white;
  margin: 10px;
  border-radius: 5px;
  cursor: pointer;
}

.btnClass:hover {
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

    <ProductCard name="Apple" :price="355" :image="product1" />

    <ProductCard name="Banana" :price="25" :image="product2" />

    <ProductCard name="Mango" :price="100" :image="product3" />

  </div>

  <!-- Example of Provide and Inject -->
  <ComponentA />


  <!-- Example of Customer event and emits -->

  <div class="flex items-center justify-center mt-6 mb-6">
    <button @click="showPopup = true" class="px-4 py-2 text-sm rounded-lg bg-gray-900 text-white hover:bg-gray-800">Show
      Popup</button>
  </div>

  <Popup v-show="showPopup" @close="showPopup = false" />

  <Input v-model="inputValue" />
  <Input2 />




  <!-- Slot example -->
  <Slot>
    <template #slot1>
      <h1>Slot 1 Content</h1>
    </template>

    <template #slot2>
      <h1>Slot 2 Content</h1>
    </template>

    <template #slot3>
      <h1>Slot 3 Content</h1>
    </template>
  </Slot>


  <!-- Example of dynamic components  -->

  <div>
    <div class="flex justify-center items-center">
      <button class="bg-green-500 hover:bg-green-600  px-4 py-1 text-white shadow-md cursor-pointer" @click="currentTab = Tab1">Tab 1</button>
      <button class="bg-red-500 hover:bg-red-600  px-4 py-1 text-white shadow-md cursor-pointer" @click="currentTab = Tab2">Tab 2</button>
      <button class="bg-blue-500 hover:bg-blue-600  px-4 py-1 text-white shadow-md cursor-pointer" @click="currentTab = Tab3">Tab 3</button>
    </div>

    <KeepAlive>

      <component :is="currentTab"/>
    </KeepAlive>

  </div>

  <!-- Example of HTTP GET request -->
  <GetRequest />
  <!-- Example of HTTP GET request -->
  <PostRequest/>

  <!-- Example of lifecycle hooks -->

 <LifeCycle/>



</template>

<script setup>
import Navbar from './components/Navbar.vue'
import Form from './components/Form.vue'
import Computed from './components/Computed.vue'
import Watchers from './components/Watchers.vue'
import ProductCard from './components/ProductCard.vue'
import ComponentA from './components/ComponentA.vue'
import Popup from './components/Popup.vue'
import Input from './components/Input.vue'
import Input2 from './components/Input2.vue'
import Slot from './components/Slot.vue'
import GetRequest from './components/GetRequest.vue'


import product1 from './assets/product-images/product1.png'
import product2 from './assets/product-images/product2.png'
import product3 from './assets/product-images/product3.png'
import { provide } from 'vue'
import { ref , shallowRef } from 'vue'

import Tab1 from './components/Tab1.vue'
import Tab2 from './components/Tab2.vue'
import Tab3 from './components/Tab3.vue'
import PostRequest from './components/PostRequest.vue'
import LifeCycle from './components/LifeCycle.vue'


const message = 'Hello, Vue!'
const btnClass = 'btnClass'
const isVisible = true;
const counter = ref(0);

// example of methods
function incrementCounter() {
  counter.value++;
}

function printMessage(event) {
  console.log(event.target.value);
}

provide('userName', 'Omor Faruk');


const showPopup = ref(false);
//v-model and component problem
const inputValue = ref('');
const currentTab = shallowRef(Tab1);

</script>