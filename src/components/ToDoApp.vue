<template>
  <div class="ToDoApp">
    <h1>{{ title }}</h1>
    <p>Add ToDo:</p>
    <input type="text" placeholder="ToDo" v-model="newItem">
    <button @click="addTask">Add</button>
    <p v-if="this.items.length !== 0">Tasks:</p>
    <li v-for="item in items" v-bind:key="item.id">
      <ul>{{ item.title }}</ul>
    </li>
  </div>
</template>

<script>


export default {
  data() {
    return {
      title: 'ToDoApp in VueJS!',
      newItem: '',
      items: [],
      id: 0
    }
  },
  methods: {
    addTask() {
      if (this.newItem === '') return
      this.items.push({ title: this.newItem, id: this.id++ })
      this.newItem = ''
    }
  }
}
</script>

<style scoped>
p,
input,
button {
  font-size: 20px;
}

input {
  height: 40px;
}

button {
  text-transform: uppercase;
  margin: 0 20px;
  padding: 10px 20px;
  border: 1px solid;
  border-radius: 4px;
}

button:hover {
  background-color: #cdcdcd;
}

ul {
  list-style: none;
}

li {
  font-size: 20px;
  margin-bottom: 10px;
}
</style>
