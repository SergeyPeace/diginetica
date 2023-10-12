<template>
    <li class="product__item item">
        <div class="item__image-container">
            <img class="item__image iamge" :src="srcImage" alt="Карточка товара">
            <span class="image-discount" v-if="discount">{{ discount }}%</span>
        </div>
        <h3 class="item__title">{{ nameBrand }}</h3>
        <p class="item__description">{{ croppingDescription }}</p>
        <div class="item__container-price" v-if="price">
            <span class="item__price">{{ priceFormatting(getDiscount) }}</span>
            <span class="item__discount" v-if="discount">{{ priceFormatting(price) }}</span>
        </div>
        <button class="item__btn btn-buy btn-reset" v-if="price && price != 0">Купить</button>
        <button class="item__btn btn-no-product btn-reset" v-if="!price || price == 0">Сообщить о поступлении</button>
    </li>
</template>
<script>


export default {
    props: ['nameBrand', 'description', 'image', 'price', 'discount'],
    data(){
        return{
            srcImage: this.image || require('@/assets/img/svg/Photo-product-default.svg'),
        }
    },
    methods:{
        priceFormatting(price){
            let lengthNumber = Math.trunc(`${Math.trunc(price)}`.length / 3);
            const arrayNumber = [];
            let kopecks = `${price}`.split('.')[1];
            
            kopecks = kopecks?.length ? `.${kopecks.slice(0,2)}` : ''
            price = Math.trunc(price);

            for (;lengthNumber > 0 && `${price}`.length > 3; lengthNumber--){
                let numberСharacters = `${price % 1000}`
                switch(numberСharacters.length){
                    case 1:
                        numberСharacters = `0${numberСharacters}`
                    case 2:
                        numberСharacters = `0${numberСharacters}`
                }

                arrayNumber.unshift(numberСharacters);
                price = Math.trunc(price / 1000);
            };              

            arrayNumber.unshift(price); 
            arrayNumber[arrayNumber.length - 1] += kopecks;
            return arrayNumber.length > 1 ? `${arrayNumber.join(' ')} ₽` : `${arrayNumber[0]} ₽`;
        }
    },
    computed:{
        croppingDescription(){
            return this.description?.length > 70 ? `${this.description.slice(0, 67)}...` : this.description ?? 'Описание отсутсвует';
        },
        getDiscount(){
            return this.discount ? (this.price * (1 - this.discount / 100)).toFixed(2) : this.price
        },
    },

}
</script>
<style scoped lang="scss">
@import '@/style/SCSS/style.scss';
    .product__item{
        display: flex;
        flex-direction: column;
        width: 333px;
        font: {
            family: 'PTSans', sans-serif;
            weight: 400;
            size: 14px;
        }

    }
    .item__image-container{
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
        height: 200px;
        background-color: #F8F8FA;
    }
    .item__image{
        position: relative;
        max-width: 100%; 
        max-height: 100%;
    }
    .xit-of-sales{
        .item__image-container{
            &::before{
                position: absolute;
                padding: 7px 31px 7px 7px;
                top: 12px;
                left: 12px;
                z-index: 1;
                content: 'Хит продаж';
                border: 1px solid $--scroll-bar {
                    radius: 4px;
                }
                background: {
                    image: url('@/assets/img/svg/Fire.svg');
                    repeat: no-repeat;
                    position: top 7px right 11px;
                    color: $--color-white;   
                }
            }
        }
        
    }
    .image-discount{
        position: absolute;
        bottom: 12px;
        left: 12px;
        padding: 6px 0;
        min-width: 48px;
        text-align: center;
        font-weight: bold;
        border-radius: 4px;
        background-color: $--color-brand;
        color: $--color-white;
    }
    .item__title{
        margin-top: 30px;
        line-height: 16px;
        color: $--color-font-second;
    }

    .item__description{
        margin-top: 8px;

        color: $--color-font-main
    }
    .item__container-price{
        display: flex;
        padding-top: 16px;
        margin-top: auto;
    }
    .item__price{
        font: {
            size: 16px;
            weight: bold;
        }

    }
    .item__discount{ 
        margin-left: 8px;
        text-decoration: line-through;
        color: $--color-font-second;
        font-size: 12px;
    }
    .btn-buy{
        @include btn;
        margin-top: 16px;
        max-width: 80px;
        color: $--color-brand;
        &:hover{
            background-color: $--color-brand;
            color: $--color-white;
        }
    }

    .btn-no-product{
        @include btn($--color-font-second);
        margin-top: auto;
        max-width: 100%;
        color: $--color-font-second;
    }

@media (max-width: 1440px) {
    .product__item{
        width: 213px;
    }
}
</style>