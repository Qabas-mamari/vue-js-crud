<template>
    <div class="customer-list">
        <div class="data">
            <table class="ui celled table">
                <thead>
                    <tr>
                        <th style="width: 50px; text-align: center;">#</th>
                        <th>Name</th>
                        <th>E-mail</th>
                        <th style="width: 148px;">Action</th>
                    </tr>
                </thead>
                <tbody>
                   <Customer />
                </tbody>
            </table>
        </div>
    </div>
</template>


<script>
import Customer from './Customer.vue';

    export default{
        name: "CustomerList",
        components: {
            Customer
        }
    }
</script>


<style scoped>

</style>