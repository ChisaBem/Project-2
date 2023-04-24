<template>
  <div class="home">
    <table>
      <thead>
        <tr>
          <th>Title</th>
          <th>Description</th>
          <th>Deadline</th>
          <th>Priority</th>
          <th>Is Complete</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
    <Items :items="items" :delete-item="deleteItem" :edit-item="editItem"></Items>
      </tbody>
    </table>
  </div>
</template>

<script>
import Items from '../components/Items.vue'

export default {
  name: 'HomeView',
  props: {
    items: {
      type: Array,
      required: true
    }
  },
  components: {
    Items
  },
  methods: {
    deleteItem(index) {
      this.$emit('delete-item', index)
    },
    editItem(index) {
      this.$emit('edit-item', index)
    }
  }
}
</script>

<style>
table {
  width: 100%;
  border-collapse: collapse;
}

th, td {
    text-align: center;
  border-bottom: 1px solid rgb(54, 54, 54);
}

th {
  color: black;
  font-weight: normal;
}

</style>
