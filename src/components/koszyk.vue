<template>
  <div>
      <h1>Koszyk</h1>
      <table>
          <tr>
            <th>Nazw</th>
            <th>Cena</th>
            <th>Ilość sztuk</th>
            <th>Łączna cena</th>
          </tr>
          <tr v-for="f in filteredProducts" :key="f.id">
              <td>{{ f.nazwa }}</td>
              <td>{{ f.cena }}</td>
              <td>{{ f.stan }}</td>
              <td>{{ f.stan*f.cena }}</td>
          </tr>
      </table>
      <p>Witam</p>
  </div>
</template>

<script setup>

    import fruits from '../dane.js'
    import { computed, ref } from 'vue'
    const filteredProducts = computed(() => fruits.value.filter(f => f.stan > 0))

</script>