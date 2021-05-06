<template>
    <div class="todoListContainer">
        <div class="heading">
            <h2 id="title">Todo List</h2>
            <AddItemForm v-on:reloadlist="GetList()" />
        </div>
        <ListView
            :items='items'
            v-on:reloadlist="GetList()"
        />
    </div>
</template>

<script>
import AddItemForm from "./AddItemForm"
import ListView from "./ListView"
export default {
    components: {
        AddItemForm,
        ListView
    },
    data () {
        return {
            items: []
        }
    },
    methods: {
      GetList() {
          axios.get('api/items')
          .then( response => {
              this.items = response.data
          })
          .catch( error =>{
              console.log( error );
          })
      }
    },
    created () {
      this.GetList();
    },
}
</script>

<style scoped>
.todoListContainer {
    width: 350px;
    margin: auto;
}

.heading{
    background: #e6e6e6;
    padding: 10px;
}

#title {
    text-align: center;
}
</style>>

