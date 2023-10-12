<template>
    <div class="container__filter-size">
        <h3 class="filter-size__title">Размер</h3>
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
            attributes: ['Атрибут','Атрибут','Атрибут','Атрибут','Атрибут'],
        }
    }
}
</script>
<style scoped lang="scss">
@import '@/style/SCSS/style.scss';
    .container__filter-size{
        text-align: center;
        margin-top: 28px;
        font-family: 'PTSans', sans-serif;
    }
    .filter-size__title{
        font: { 
            size: 16px;
            weight: bold;
        }
        line-height: 20px;
    }
</style>