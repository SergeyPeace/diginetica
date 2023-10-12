<template>
    <header class="header">
        <router-link to="/" class="header__link-logo">
            <img class="header__logo logo" src="@/assets/img/svg/Logo.svg" alt="Логотип магазина">
            <span class="logo__title">Логотип</span>
        </router-link>
        <button class="header__btn btn-reset">Каталог</button>
        <HeaderSearch/>
        <nav class="header__nav nav">
            <router-link to="/" class="nav__link">Информация о компании</router-link>
            <router-link to="/" class="nav__link">Контакты</router-link>
            <router-link to="/" class="nav__link">Полезные ссылки</router-link>
        </nav>
    </header>
</template>
<script>
import HeaderSearch from './HeaderSearch.vue';
export default{
    components: {
        HeaderSearch,
    }
}
</script>
<style scoped lang="scss">
@import '@/style/SCSS/style.scss';
    .header{
        display: flex;
        align-items: center;
        margin: 12px 0;
        font: {
            family: 'Inter', sans-serif;
            weight: 400;
        }
    }
    .header__link-logo{
        display: flex;
        text-decoration: none;
        font-size: 16px;
        color: $--color-black;
    }
    .logo__title{
        margin-left: 12px;
    }
    .header__btn{
        margin-left: 32px;
        padding: 15px 23px;
        border: 1px solid $--color-brand{
            radius: 8px;
        }
        font: {
            family: 'Inter', sans-serif;
            weight: 500;
            size: 14px;
        }
        color: $--color-black;
        &:active{
            background-color: $--color-brand;
        }
        
    }
    .nav__link{
        margin-left: 20px;
        color: $--color-font-main;
        text-decoration: none;
        font-size: 14px;
    }
</style>