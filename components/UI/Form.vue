<template>
    <div class="form">
        <div class="form-container">
            <div class="title">{{ title }}</div>
            <div class="subtitle">{{ subtitle }}</div>
            <div class="input-container">
                <n-input size="large" round v-model:value="selectValue.name" type="text" placeholder="Имя" />
                <n-input size="large" round v-model:value="selectValue.phone" type="tel" placeholder="Телефон" />
                <n-select placeholder="Выберите услугу" size="large" v-model:value="selectValue.select" :options="selectOptions" />
            </div>
            <n-button :disabled="!validate" style="width: fit-content" type="error" @click="h">Записаться</n-button>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const props = defineProps({
  title: {
    type: String,
    required: true
  },
  subtitle: {
    type: String,
    default: 'Оставьте свои контактные данные, администратор перезвонит и согласует дату и время приёма'
  }
})


let selectValue = ref({
    name: null,
    phone: null,
    select: null,
})
const validate = computed(() => {
  return (
    selectValue.value.name &&
    selectValue.value.phone &&
    selectValue.value.select
  )
})
let selectOptions = ref([
    {
        label: 'Протезирование',
        value: 'Протезирование'
    },
    {
        label: 'Имплантация',
        value: 'Имплантация'
    }
])
let h = () => {
    console.log(validate);
    // TO DO 
    //Сделать типо отправку на почту и CRM 
}

</script>

<style scoped>
.form{
    width: 600px;
    height: fit-content;
    background-color: white;
    border-radius: 40px;
}
.form-container{
    padding: 40px;
    display: flex;
    flex-direction: column;
    line-height: 200%;
}
.title{
    font-size: 32px;
    margin: 0 auto;
    text-align: center;
}
.subtitle{
    font-size: 20px;
    margin-top: 20px;
    text-align: center;
}
.input-container{
    margin: 50px 0;
    display: flex;
    gap: 20px;
    flex-direction: column;

}


</style>