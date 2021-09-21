<template>
  <div class="category">
    <table>
      <thead>
        <input type="text" v-model="search" placeholder="Search.." />
      </thead>
      <tr v-for="cat in filterCategories">
        <td>{{ cat }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'Category',
  data() {
    return {
      name: 'gam',
      catagories: [],
      search: '',
    };
  },
  created() {
    this.loadData();
  },
  computed: {
    filterCategories() {
      return this.catagories.filter((item) => {
        return item.toLowerCase().includes(this.search.toLowerCase());
      });
    },
  },
  methods: {
    async loadData() {
      await fetch('https://api.publicapis.org/categories')
        .then((res) => res.json())
        .then((data) => {
          this.catagories = data;
        });
    },
  },
};
</script>

<style>
input {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  font-size: 1em;
  margin-bottom: 10px;
}

table {
  width: 100%;
}
</style>
