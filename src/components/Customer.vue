<template>
        <tr>
            <td>{{customer.id}}</td>
            <td>{{customer.first_name}}{{ customer.last_name}}</td>
            <td>{{customer.email}}</td>
            <td>
                <button class="mini ui blue button">Edit</button>
                <button class="mini ui red button">Delete</button>
            </td>
        </tr>
</template>


<script>
export default {
    name: "Customer",
    props:{
        customer:{
            type: Object
        }
    }
}
</script>


<style scoped>
</style>