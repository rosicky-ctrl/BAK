<template>
  <div>
      <h1>Lista produktów</h1>
      <table>
          <tr>
            <th>Nazwa produktu</th>
            <th>Cena produktu</th>
            <th>Dodaj do koszyka</th>
            <th>Usuń z koszyka</th>
          </tr>
          <tr v-for="f in fruits" :key="f.id">
              <td>{{ f.nazwa }}</td>
              <td>{{ f.cena }}</td>
              <td><button @click="f.stan++">Dodaj</button></td>
              <td><button :disabled="f.stan<0" @click="f.stan--">Usuń</button></td>
          </tr>
      </table>
  </div>
</template>

<script setup>

    import fruits from '../dane.js'
    import { computed, ref } from 'vue'
    const filteredProducts = computed(() => fruits.value.filter(f => f.stan > 0))

</script>