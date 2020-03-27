<template>
    <q-form @submit="submitForm">
        <q-input v-if="tab == 'register'" outlined class="q-mb-sm" v-model="formData.name" label="Name" />
        <q-input outlined class="q-mb-sm" type="email" v-model="formData.email" label="Email" />
        <q-input outlined class="q-mb-sm" type="password" v-model="formData.password" label="Password" />
        <div class="row">
            <q-space />
            <q-btn type="submit" color="primary" :label="tab" />
        </div>
    </q-form>
</template>

<script>
export default {
    props: ['tab'],
    data(){
        return {
            formData: {
                name: '',
                email: '',
                password: ''
            }
        }
    },
    methods: {
        submitForm() {
            if(this.tab == 'login'){
                console.log('login')
            }else{
                console.log('register')
            }
        }
    }
}
</script>