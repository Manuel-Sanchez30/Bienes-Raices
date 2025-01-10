<script setup>
    import { useField, useForm } from 'vee-validate';
    import { loginSchema } from '@/validation/loginShema';

    const {handleSubmit} = useForm({ validationSchema : loginSchema });


    const email = useField('email');
    const password = useField('password');
    const submit = handleSubmit(()=>{
        console.log('submit...');
    });

</script>

<template>

    
    <v-card
        flat
        max-width="600"
        class="mx-auto"
    >
        <v-card-title
            class="text-h4 font-weight-bold"
        >
            Iniciar Sesion
        </v-card-title>
        <v-card-subtitle
            class="text-h5"
        >
            Inicia sesion con tu Cuenta
        </v-card-subtitle>

        <v-form>
            <v-text-field
                type="email"
                label="Email"
                v-model="email.value.value"
            />
            <v-text-field
                type="password"
                label="Password"
                v-model="password.value.value"
            />
            <v-btn
                block
                color="pink-accent-3"
                @click="submit"
            >
                iniciar sesion
            </v-btn>
        </v-form>

    </v-card>

</template>
