<!-- Template for Wishlist Modal  -->

<!-- Custom event handler $emit on child component
to send data back to parent component
-->
<template>
  <div>
    <ul class="list-group">
      <li class="list-group-item" v-for="item in items" :key="item.id">
        {{ item.name }} {{ item.price.formatted_with_symbol }}
        <button
          @click="$emit('remove-from-wishlist',item)"
          class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded float-right"
        >Remove</button>
      </li>
    </ul>
    
  </div>
</template>
<script>
export default {
  props: ["items"]
  
};
</script>