<template>
    <tr v-for="(item, index) in items" :key="index">
      <td>{{ item.title }}</td>
      <td>{{ item.description }}</td>
      <td>{{ item.date }}</td>
      <td>{{ item.radio }}</td>
      <td>{{  }}</td>
      <td>
        <div style="display: flex; flex-direction: column; justify-content: center;">
          
          <button class="butn" style="background-color: red;" @click="deleteItem(index)">
          <img src="https://cdn-icons-png.flaticon.com/512/1214/1214428.png" alt="delete icon" style="width: 20px; height: 20px; margin-right: 5px;">
           Delete
          </button>



          <button class="butn" @click="editItem(index)">
          <img  class="color" src="https://cdn-icons-png.flaticon.com/512/1159/1159633.png" alt="edit icon" style="width: 20px; height: 20px; margin-right: 5px;">
               Edit
          </button>

        </div>
      </td>
    </tr>
  </template>
  
  <script>
  export default {
    name: 'Items',
    props: {
      items: {
        type: Array,
        required: true
      },
    deleteItem: {
      type: Function,
      required: true
    },
    editItem: {
      type: Function,
      required: true
    }
    },
  methods: {
    deleteItem(index) {
      this.deleteItem(index)
    },
    editItem(index) {
      this.editItem(index)
    }
  }
  }
  </script>
  <style scoped>
  table {
    width: 100%;
    border-collapse: collapse;
  }
  
  tr {
    padding: 8px;
    text-align: center;
    border-bottom: 1px solid rgb(54, 54, 54);
  }
  
  .color{
    color: #eeeef0 !important;
  }

  
.butn {
  appearance: button;
  backface-visibility: hidden;
  background-color: #405cf5;
  border-radius: 6px;
  border-width: 0;
  box-shadow: rgba(50, 50, 93, .1) 0 0 0 1px inset,rgba(50, 50, 93, .1) 0 2px 5px 0,rgba(0, 0, 0, .07) 0 1px 1px 0;
  box-sizing: border-box;
  color: #fff;
  cursor: pointer;
  font-family: -apple-system,system-ui,"Segoe UI",Roboto,"Helvetica Neue",Ubuntu,sans-serif;
  font-size: 100%;
  outline: none;
  overflow: hidden;
  position: relative;
  text-align: center;
  text-transform: none;
  transform: translateZ(0);
  transition: all .2s,box-shadow .08s ease-in;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  width: 39%;
  margin: -1px;
  margin-left: 30%;
}

.butn:disabled {
  cursor: default;
}

.butn:focus {
  box-shadow: rgba(50, 50, 93, .1) 0 0 0 1px inset, rgba(50, 50, 93, .2) 0 6px 15px 0, rgba(0, 0, 0, .1) 0 2px 2px 0, rgba(50, 151, 211, .3) 0 0 0 4px;
}

  </style>