<template>
  <div>

    <table v-if="lists.length" class="table table-bordered">
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
      <tr
          class="animate__animated animate__fadeIn"

          v-for="(list,index) in lists"
          :key="list.id"
      >
        <td>
          {{ index+1 }}
        </td>
        <td class="d-flex justify-content-between ">
          {{ list.itemName }}
          <i class="ms-2 bi bi-trash3 text-danger d-print-none" @click="del(index)"></i>
        </td>
        <td class="text-end">{{ list.price }}</td>
        <td class="text-end">{{  list.quantity }}</td>
        <td class="text-end">{{ list.cost }}</td>
      </tr>

      <tr>

        <td colspan="4" class="text-center">Total</td>
        <td class="text-end">{{ total }}</td>
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
  computed: {
    total() {
      return this.lists.reduce((p,c)=>p+c.cost,0)
    }
  },
  methods: {
    del(index) {
      this.$emit("deleteList",index)
    }
  },
}
</script>

<style scoped>

</style>