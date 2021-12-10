<template>
    <!-- Container wrapper -->
    <div class="container">
        <!-- Navbar brand -->
        <a class="navbar-brand me-2" href="https://mdbgo.com/">
        <img
            src="https://mdbootstrap.com/img/logo/mdb-transaprent-noshadows.png"
            height="16"
            alt="img"
            loading="lazy"
            style="margin-top: -1px;"
        />
        </a>

        <!-- Toggle button -->
        <button
        class="navbar-toggler"
        type="button"
        data-mdb-toggle="collapse"
        data-mdb-target="#navbarButtonsExample"
        aria-controls="navbarButtonsExample"
        aria-expanded="false"
        aria-label="Toggle navigation"
        >
        <i class="fas fa-bars"></i>
        </button>

        <!-- Collapsible wrapper -->
        <div class="collapse navbar-collapse" id="navbarButtonsExample">
        <!-- Left links -->
        <ul class="navbar-nav me-auto mb-2 mb-lg-0 mx-auto">
            <li>{{ name }} </li>
        </ul>
        <!-- Left links -->

        <div class="d-flex align-items-center">
            <button type="button" class="btn btn-primary me-3" @click.prevent="logoutUser">
            {{ text }}
            </button>
        </div>
        </div>
        <!-- Collapsible wrapper -->
    </div>
    <!-- Container wrapper -->
</template>

<script>
export default {
    props: ['name', 'text', 'password'],
    data(){
        return{
            logoutName: this.name,
            logoutText: this.text
        }
    },
    methods:{
        logoutUser(){
            let oldUser = {
                name: this.logoutName,
                text: this.logoutText
            }
            this.$emit('logoutold-user', oldUser)
        }
    }

}
</script>

<style>

</style>