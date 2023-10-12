<template>
    <label for="search-product" class="header__search-product">
        <input type="input" id="search-product" class="search-product" v-model="searchData" placeholder="Поиск по 100 000 товаров"/>
        <button v-show="searchData" class="search-product__btn-clear btn-reset" @click="clearInputSearch"></button>
        <button v-show="searchData" class="search-product__btn-search btn-reset">Найти</button>
    </label>   
</template>
<script>

export default{
    data(){
        return{
            searchData:'',
        }
    },
    methods: {
        clearInputSearch(){
            this.searchData = ''
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/SCSS/style.scss';
    .header__search-product{
        position: relative;
        flex-grow: 1;
        margin-left: 24px;
        margin-right: 68px;
        &::before{
            position: absolute;
            display: block;
            top: 14px;
            left: 18px;
            content: '';
            width: 18px;
            height: 18px;
            background-image: url('@/assets/img/svg/Loupe.svg');
            background-repeat: no-repeat;
        }
        .search-product{
            padding: 14px 16px 14px 48px;
            width: 100%;
            font-size: 16px;
            border: 1px solid $--color-brand{
                radius: 10px;
            };
            &::placeholder{
                color: #5A5A5A;
            }
            &:focus-visible{
                outline: none;
            }
        }

        .search-product__btn-clear{
            position:absolute;
            top: 13px;
            right: 24px;
            height: 20px;
            width: 20px;

            background-image: url('@/assets/img/svg/Btn-clear.svg');
        }

        .search-product__btn-search{
            position: absolute;
            top: 4px;
            right: -60px;
            @include btn;
            border-radius: 8px;
            background-color: $--color-brand;
            color: $--color-white;
        }
    }

</style>