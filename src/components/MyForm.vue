<template>
    <div class="my-form">
        <form action="" class="ui form">
            <div class="fields">
                <div class="four wide field">
                    <label for="">First name</label>
                    <input type="text" name="first_name" id="" placeholder="first name">
                </div>
                <div class="four wide field">
                    <label for="">Last name</label>
                    <input type="text" name="last_name" id="" placeholder="last name">
                </div>
                <div class="four wide field">
                    <label for="">E-mail</label>
                    <input type="email" name="jeo@gmail.com" id="" placeholder="email">
                </div>
                
                <div class="two wide field">
                    <button class="ui primary button submit-button">Save</button>
                </div>
            </div>
        </form>
    </div>
</template>


<script>
    export default{
        name: "MyForm"
    }
</script>


<style scoped>

</style>