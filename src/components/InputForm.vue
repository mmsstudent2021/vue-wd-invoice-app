<template>
  <div class="border rounded my-4 p-3">
    <form @submit.prevent="inputToApp" action="">
      <div class="row g-3">
        <div class="col-md-6">
          <label class="form-label" for="">Select Item</label>
          <select required name="" v-model="selectedItem" class="form-select" id="">
            <option
                v-for="item in items"
                :key="item"
                :value="item.id">
              {{ item.name }}
            </option>
          </select>
        </div>
        <div class="col-md-3">
          <label class="form-label" for="">Quantity</label>
          <input required type="number" v-model.number="quantity" class="form-control">
        </div>
        <div class="col-md-3">
          <button  class="btn btn-lg btn-primary h-100 w-100">
            <i class="bi bi-plus-circle-dotted me-2"></i>
            Add Item
          </button>
        </div>
      </div>
    </form>

  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          id:1,
          name:"Apple",
          price:50,
        },
        {
          id:2,
          name:"Orange",
          price:100,
        },
        {
          id:3,
          name:"Mango",
          price:150,
        },
        {
          id:4,
          name:"Banana",
          price:30,
        }
      ],
      quantity : 0,
      selectedItem: null,
    }
  },
  methods: {
    inputToApp() {

      this.$emit("addList",this.quantity,this.items.find(item => item.id === this.selectedItem))

    }
  },

}
</script>

<style scoped>

</style>