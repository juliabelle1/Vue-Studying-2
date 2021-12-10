<template>
    <div class="col">
        <div class="card h-100">
            <div class="card-header bg-primary text-center text-white">
            <h2 class="card-title">Login</h2>
            </div>
            <div class="card-body">
            <form @submit.prevent="update">
                <!-- Name input -->
                <div class="mb-2">
                <label class="form-label" for="name">Name</label>
                <input type="text" id="name" class="form-control" v-model="newName"/>
                </div>
                <!-- age input -->
                <div class="mb-2">
                <label class="form-label" for="password">Password </label>
                <input type="password" id="password" class="form-control" v-model="newPassword"/>
                </div>



                <!-- Submit button -->
                <button v-if="text !== 'log out'" type="submit" class="btn btn-primary btn-block mb-4">Login</button>
            </form>
            </div>
        </div>
        </div>


</template>

<script>
export default {
    props: ['name','text', 'password'],
    data(){
        return{
            newName: this.name,
            newPassword: this.password,
            newText: this.text
        }
    },
    methods: {
        update(){
            let user = {
                name: this.newName,
                password: this.newPassword,
                text: this.newText
            }
            this.$emit('login-user', user)
        }
    }
}
</script>

<style>

</style>