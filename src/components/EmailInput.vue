<template>
    <input
        type="email"
        class="form-control"
        placeholder="E-mail"
        :value="modelValue"
        @input="updateValue($event)"
        :class="{
            'is-valid': validateEmail(modelValue),
            'is-invalid': !validateEmail(modelValue),
        }"
    />
</template>

<script>
import validateEmail from '../validate-email';

export default {
    name: "EmailInput", 
    props: ['modelValue'],
    methods: {
        updateValue($event) {
            this.$emit('update:modelValue', $event.target.value)
        }, 
        validateEmail
    }
}
</script>