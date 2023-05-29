<template>
  <div id="app">
    <h1 id="tittle">查詢草莓價格</h1>
    <form v-on:submit.prevent="addItem">
      <p>Name<input type="text" required v-model="itemName"></p>
      <p>Year<input type="text" v-model="itemYear"></p>
      <p>Month<input type="text" v-model="itemMonth"></p>
      <p>Price<input type="text" v-model="itemPrice"></p>
      <button type="submit">Submit</button>
    </form>

    <table class="bg-gray-100 ml-20 mr-20 pt-12 flex flex-col  md:flex-col  items-center">
      <thead>
      <tr class="flex flex-row items-center">
        <th class="ml-10 mr-10">Name</th>
        <th class="ml-10 mr-10">Year</th>
        <th class="ml-10 mr-10">Month</th>
        <th class="ml-10 mr-10">Price</th>
      </tr>
      </thead>
      <tbody id="table">
      <tr v-for="item in table" class="flex flex-row place-content-between">
        <td class="flex flex-col flex-auto mr-20" >{{ item.name }}</td>
        <td class="mr-32">{{ item.year }}</td>
        <td class="mr-32">{{ item.month}}</td>
        <td class="mr-18">{{ item.price}}</td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      itemName: null,
      itemYear: null,
      itemMonth: null,
      itemPrice: null,
      table: [
        {Name: 'strawberry', Year: '2020', Month: '3', Price: '110'}
      ]
    }
  },
  methods: {
    addItem() {
      let item = {
        Name: this.itemName,
        Year: this.itemYear,
        Month: this.itemMonth,
        Price: this.itemPrice
      }
      this.table.push(item);
      this.itemName = null;
      this.itemYear = null;
      this.itemMonth = null;
      this.itemPrice = null;

    }
  }
}
</script>

<style scoped>
</style>