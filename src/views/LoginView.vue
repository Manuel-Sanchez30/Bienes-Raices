<script setup>
    import { useField, useForm } from 'vee-validate';
    import { loginSchema } from '@/validation/loginShema';
    import { useFirebaseAuth } from 'vuefire';
    import { signInWithEmailAndPassword } from 'firebase/auth'

    const {handleSubmit} = useForm({ validationSchema : loginSchema });
    const auth = useFirebaseAuth();

    const email = useField('email');
    const password = useField('password');
    const submit = handleSubmit((values)=>{
        console.log(values);
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
                :error-messages="email.errorMessage.value"
                class="mb-5"
            />
            <v-text-field
                type="password"
                label="Password"
                v-model="password.value.value"
                :error-messages="password.errorMessage.value"
                class="mb-5"
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
