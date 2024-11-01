<template>
    <header>
        <div class="header-top container">
            <div class="header-logo-block">
                <a href="/" class="header-logo-link">
                    <img src="../public/tais-logo.png" alt="" class="logo-icon" />
                </a>
                <div class="header-logo-title">
                    <p>Центр красоты <br />и здоровья</p>
                    <span>Работаем с 1993 года</span>
                </div>
            </div>
            <div class="header-time-block">
                <p>ПН - ПТ: 9:00 -20:00</p>
                <p>СБ: 9:00 -15:00</p>
                <p>ВС: Выходной</p>
            </div>
            <n-button type="error" round @click="showModal = true">Записаться на прием</n-button>
            <n-modal v-model:show="showModal">
                <UIForm title="Записаться на прием" />
            </n-modal>
            <a href="tel:+7 (4852) 28-02-25" class="header-phone">+7 (4852) 28-02-25</a>
        </div>
        <div class="header-bottom">
            <div class="container">

            </div>
        </div>
    </header>
</template>

<script setup>
import { ref } from "vue";


let showModal = ref(false)



</script>

<style scoped>
header {}

.header-top {
    width: 100%;
    height: fit-content;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 120px;
}

.header-logo-block {
    display: flex;
    align-items: center;
    gap: 20px;
}

.logo-icon {
    height: 92px;
}

.header-logo-title {
    display: flex;
    flex-direction: column;
    gap: 5px;
    line-height: 140%;

    span {
        opacity: 0.5;
        font-size: 12px;
    }
}

.header-time-block {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
}
.header-phone{
    font-size: 20px;
    font-weight: 700;
    color: black;
}
.header-phone:hover{
    color: #c6333c
}

.header-bottom{
    background-color: aqua;
    height: 50px;
    
}
</style>
