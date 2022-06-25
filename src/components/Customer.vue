<template>
        <tr>
            <td>{{customer.id}}</td>
            <td>{{customer.first_name}}{{ customer.last_name}}</td>
            <td>{{customer.email}}</td>
            <td>
                <button class="mini ui blue button">Edit</button>
                <button class="mini ui red button" @click="onDelete">Delete</button>
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
    },
    methods:{
        onDelete(){
            // window.console.log("customer delete "+ this.customer.id);
            this.$emit("onDelete", this.customer.id);
        }
    }
};
</script>


<style scoped>
</style>