<template>
    <div>
        <table width = "80%" border = "1" style="margin: 1rem auto"> 
            <thead>
                <tr>
                    <th>Id</th>
                    <th>Task</th>
                    <th>Completed</th>
                </tr>
            </thead>

            <tbody>
                <tr 
                    v-for="todo in todos" 
                    :key = "todo.id"
                >

                    <td>
                        {{todo.id}}
                    </td>
                    <td>
                        {{todo.title}}
                    </td>
                    <td>
                        {{todo.completed}}
                    </td>
                    
                </tr>
            </tbody>

        </table>
    </div>
</template>

<script>
import axios from 'axios';

export default ({
    data() {
        return {
            todos: []
        }
    },
    async mounted () {
        const { data } = await axios.get("https://jsonplaceholder.typicode.com/todos")
        this.todos = data
    }
})
</script>