<template>
  <div>
    <h3>Items:</h3>
    <ul>
      <!--      un v-for que renderizará todos nuestros items en elementos <li>.-->
      <li v-for="item in items" :key="item.id">{{ item.name }}</li>
    </ul>
  </div>
</template>

<!--En primer lugar, especificamos el atributo lang en el
elemento <script> con el valor ts para que podamos usar TypeScript.-->

<!--// declaramos la propiedad items como un array de any-->
<!--//es muy recomendable proporcionar interfaces y tipos para evitar usar ‘any’.-->
<script lang="ts">
import {defineComponent, PropType} from 'vue'
import {ItemInterface} from "@/models/items/Item.interface";

export default defineComponent({
  name: 'ItemListComponent',
  props: {
    items: {
      type: Array as PropType<ItemInterface[]>
      // type: Array as PropType<any[]>
    }
  }
})
</script>
