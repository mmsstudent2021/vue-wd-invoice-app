<template>
  <div>

    <table class="table table-bordered">
      <thead>
      <tr>
        <th>#</th>
        <th>Item</th>
        <th class="text-end">Price</th>
        <th class="text-end">Quantity</th>
        <th class="text-end">Cost</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="(list,index) in lists" :key="list.id">
        <td>{{ index+1 }}</td>
        <td>{{ list.itemName }}</td>
        <td class="text-end">{{ list.price }}</td>
        <td class="text-end">{{  list.quantity }}</td>
        <td class="text-end">{{ list.cost }}</td>
      </tr>

      <tr>

        <td colspan="4" class="text-center">Total</td>
        <td class="text-end">1000</td>
      </tr>
      </tbody>
    </table>

  </div>
</template>

<script>
export default {
  props: {
    lists: Object,
  },
}
</script>

<style scoped>

</style>