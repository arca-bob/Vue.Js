<script setup lang="ts">
import ButtonComponent from './ButtonComponent.vue';
import FieldsComponent from './FieldsComponent.vue';

interface FormComponentProperties {
    data:{
        fields: Array<{id: string, placeholder: string, class?: string, type?: string, name: string}>
        buttons: {id: string, type?: 'button' | 'submit' | 'reset', class: string }[]
    }
}

defineProps<FormComponentProperties>()

</script>

<template>
    <main class="login_main">
        <form class="custom-form">
            <section class="custom-form_fields-section">
               <FieldsComponent 
               v-for="(field,index) in data.fields"
               :key="index"
               :data="field"
               /> 
            </section>
                <ButtonComponent
                    v-for="(button,index) in data.buttons"
                    :key="index"
                    :data="button"
                />

        </form>
    </main>

</template>
