<template>
    <ul class="product__list list">
        <ProductItem class='xit-of-sales' v-for="product in products" :key="product.id" 
            :name-brand="product.title" 
            :description="product.description"
            :image="product.img"
            :price="product.price"
            :discount="product.discount"
        />
    </ul>   
</template>
<script>
import ProductItem from '@/components/product/ProductItem.vue';
export default{
    components: {
        ProductItem,
    },
    data(){
        return{
            products: [{
                id: 0,
                title: 'Бренд',
                img: '',
                price: 5990,
                discount: 25,
            }, {
                id: 1,
                title: 'Бренд',
                description: 'Полное название товара в несколько строк для вида с обрывом в конце Тут мог бы быть еще какой-то текст',
                img: '',
                price: 5990,
                discount: 0,
            }, {
                id: 0,
                title: 'Бренд',
                description: 'Полное название товара в несколько строк для вида с обрывом в конце Тут мог бы быть еще какой-то текст',
                img: '',
                discount: 25,
            }, {
                id: 1,
                title: 'Бренд',
                description: 'Полное название товара в несколько строк для вида с обрывом в конце Тут мог бы быть еще какой-то текст',
                img: '',
                price: 7450,
                discount: 5,
            }, {
                id: 0,
                title: 'Бренд',
                description: 'Полное название товара в несколько строк для вида с обрывом в конце Тут мог бы быть еще какой-то текст',
                img: '',
                price: 5990,
                discount: 0,
            }, {
                id: 1,
                title: 'Бренд',
                description: 'Полное название товара в несколько строк для вида с обрывом в конце Тут мог бы быть еще какой-то текст',
                img: '',
                price: 11219,
                discount: 0,
            },{
                id: 0,
                title: 'Бренд',
                description: 'Полное название товара в несколько строк для вида с обрывом в конце Тут мог бы быть еще какой-то текст',
                img: '',
                price: 23711,
                discount: 7,
            }, {
                id: 1,
                title: 'Бренд',
                description: 'Полное название товара в несколько строк для вида с обрывом в конце Тут мог бы быть еще какой-то текст',
                img: '',
                price: 5990,
                discount: 0,
            }, {
                id: 0,
                title: 'Бренд',
                description: 'Полное название товара в несколько строк для вида с обрывом в конце Тут мог бы быть еще какой-то текст',
                img: '',
                price: 5320,
                discount: 40,
            }, {
                id: 1,
                title: 'Бренд',
                description: 'Полное название товара в несколько строк для вида с обрывом в конце Тут мог бы быть еще какой-то текст',
                img: '',
                price: 4550,
                discount: 0,
            },]
        }
    }
}
</script>
<style lang="scss" scoped>
.product__list{
    display: flex;
    flex-wrap: wrap;
    margin-left: 12px;
    list-style: none;
    & li{
        margin-bottom: 24px;
        margin-left: 24px;
    }
}

</style>