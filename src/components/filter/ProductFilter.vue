<template>
    <div class="filter__container">
        <FilterCategory :categories-list="categoriesList"/>
        <FilterPrice/>
        <FilterBrand/>
        <FilterSize/>
    </div>
</template>
<script>
import FilterCategory from "./FilterCategory.vue";
import FilterPrice from './FilterPrice.vue';
import FilterBrand from "./FilterBrand.vue";
import FilterSize from "./FilterSize.vue";

export default{
    name: 'ProductFilter',
    components: {
        FilterCategory,
        FilterPrice,
        FilterBrand,
        FilterSize,
    }, 
    data(){
        return{
            categoriesList: [
                {
                    nameGroup: 'Название группы категорий (Одежда)',
                    groupCategories: [
                        {
                            nameCategories: 'Название категории (Кофты)',
                            categories: ['Водолазка', 'Кардиган', 'Свитер'],
                        },
                        {
                            nameCategories: 'Название категории (Брюки)',
                            categories: ['Бермуды', 'Бойфренды', 'Бриджи'],
                        },
                    ],
                },
            ],
        }
    }
}
</script>

<style lang="scss" scoped>
    .filter__container{
        width: 280px;
    }
</style>