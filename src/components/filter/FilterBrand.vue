<template>
    <div class="container__filter-brand">
        <div class="filter-brand__information">
            <h3 class="filter-brand__title">Бренд</h3>
            <button class="filter-brand__btn--clear btn-reset" @click="inputValue = ''">Очистить</button>
        </div>
        <label class="filter-brand__label">
            <input class="filter-brand__input" id="filter-brand__input" type="text" name="brand" placeholder="Поиск" v-model="inputValue"/>
        </label>
        <checkboxList :attributes-list="attributes"/>
    </div>
</template>
<script>
import checkboxList from '../ui/checkboxList.vue';
export default{
    name: 'FilterBrand',
    components: {
        checkboxList,
    },
    data(){
        return{
            inputValue:'',
            attributes: ['Атрибут','Атрибут','Атрибут','Атрибут','Атрибут','Атрибут','Атрибут','Атрибут'],
        }
    }
}
</script>
<style scoped lang="scss">
@import '@/style/SCSS/style.scss';
    .container__filter-brand{
        margin-top: 28px;
        font-family: 'PTSans', sans-serif;
    }
    .filter-brand__information{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    .filter-brand__title{
        font: { 
            size: 16px;
            weight: bold;
        }
        line-height: 20px;
    }
    .filter-brand__btn--clear{
        color: $--color-font-second;
        text-decoration: underline;
    }

    .filter-brand__input{
        @include input;
        padding-left: 35px;
        width: 236px;
        &::placeholder{
            color: $--color-font-second;
        }
    }
    .filter-brand__label{
        position: relative;
        display: block;
        margin-top: 16px;
        &::before{
            position: absolute;
            left: 12px;
            top: 10px;
            content: '';
            width: 16px;
            height: 16px;
            background: {
                image: url('@/assets/img/svg/Search.svg');
                repeat: no-repeat;
            }
        }
    }
</style>