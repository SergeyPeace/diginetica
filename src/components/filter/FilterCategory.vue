<template>
    <ul class="filter__category-group category-group item--show">
        <li class="category-group__item-group item-group" 
            v-for="group in categoriesList" 
            :key="group.nameGroup"
            @click="categoryGroup = categoryGroup == group.nameGroup ? false : group.nameGroup, categoryProduct= false"
        >   
            <div class="inside-element">
                {{group.nameGroup}} 
                <div class="item-count">
                    {{ group.groupCategories.length }}
                </div>
            </div>
            <ul class="item-group__category-product category-product" :class="{'item--show': categoryGroup == group.nameGroup}">
                <li class="category-product__list"
                    v-for="category in group.groupCategories"
                    :key="category.nameCategories"
                    @click.stop="categoryProduct =  categoryProduct == category.nameCategories ? false : category.nameCategories"
                >
                    <div class="inside-element">
                        {{  category.nameCategories }} 
                        <div class="item-count">
                            {{ category.categories.length }} 
                        </div>
                    </div>
                    <ul class="list__product product" :class="{'item--show': categoryProduct == category.nameCategories}">
                        <li class="product__item"
                            v-for="product in category.categories"
                            :key="product"
                        >
                            <div class="inside-element">
                                <button class="btn-reset">
                                    {{ product }}
                                </button>
                            </div>
                        </li>
                    </ul>
                </li>
            </ul>
        </li>
    </ul>
</template>

<script>
export default{
    name: 'FilterCategory',
    props: ['categoriesList'],
    data(){
        return{
            categoryGroup: false,
            categoryProduct: false,
        }
    }
}

</script>

<style scoped lang="scss">
@import '@/style/SCSS/style.scss';
    ul{
        display: none;
    }
    .item--show{
        display: block;
    }
    .category-group{
        font: {
            family: 'PTSans', sans-serif;
            size: 14px;
        }
        line-height: 16px;
        cursor: pointer;
    }
    
    .category-product__list .inside-element{
        padding-left: 32px;
    }
    .product__item .inside-element{
        padding-left: 48px;
    }
    .item-count{
        color: $--color-font-second;
    }
    .inside-element{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        padding: 7px 16px 7px 8px;
        border-radius: 5px;
        &:hover{
            background-color: $--color-font-bg;
            .item-count{
                color: $--color-font-main;
            }
        }
    }


</style>