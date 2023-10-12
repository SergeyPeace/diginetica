<template>
    <div class="container__filter-price">
        <h3 class="filter-price__title">Цена</h3>
        <form class="filter-price__form form">
            <label class="form__label--price">
              <input class="form__input" type="number" name="min-price">
              <span class="form__value">От</span>
            </label>
            <span class="form__dash">&nbsp;—&nbsp;</span>
            <label class="form__label--price">
              <input class="form__input" type="number" name="max-price">
              <span class="form__value">До</span>
            </label>
        </form>
    </div>
</template>
<script>
export default{
    name: 'FilterPrice',
}
</script>
<style lang="scss" scoped>
@import '@/style/SCSS/style.scss';
    .container__filter-price{
        text-align: center;
        margin-top: 28px;
        font-family: 'PTSans', sans-serif;
    }
    .filter-price__title{
        margin-bottom: 16px;
        font: { 
            size: 16px;
            weight: bold;
        }
        line-height: 20px;
    }

    .filter-price__form{
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }

    .form__label--price{
        position: relative;
    }
    .form__value{
        position: absolute;
        top: 11px;
        left: 8px;
        font-size: 12px;
        color: $--color-font-second;
    }

    .form__dash{
        color: $--color-font-second;
    }

    .form__input{
        @include input;
        max-width: 86px;
    }
</style>