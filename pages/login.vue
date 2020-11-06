<template>
    <section>
        <div v-if="$route.query.message" class="alert alert-danger mb-3">
            Need login first
        </div>
        <h1>Login page</h1>
        <form @submit.prevent="onSubmit">
            <div class="form-group">
                <input type="text" class="form-control">
            </div>
            <p>
                <nuxt-link to="/">To home page</nuxt-link>
            </p>

            <button class="btn btn-primary">Login</button>
        </form>
    </section>
</template>

<script>
export default {
    layout:'empty',
    methods:{
        onSubmit(){
            this.$store.dispatch('login')
            this.$router.push('/')
        }
    }
}
</script>

<style scoped>
section{
    width: 500px;
    margin: 0 auto;
    padding-top: 30px;
}
</style>