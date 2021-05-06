<template>
    <div class="todoListContainer">
        <div class="heading">
            <h2 id="title">Todo List</h2>
            <AddItemForm />
        </div>
        <ListView />
    </div>
</template>

<script>
import AddItemForm from "./AddItemForm"
import ListView from "./ListView"
export default {
    components: {
        AddItemForm,
        ListView
    }
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

