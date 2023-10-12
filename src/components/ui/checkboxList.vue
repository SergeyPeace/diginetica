<template>
    <ul class="list">
            <li class="item"
                v-for="(attribute, index) in attributesList"
                :key="index"
            >
                <label class="item__label checkbox-label">
                    <input type="checkbox"/>
                    {{ attribute }}
                    <span class="item__count-product">{{ index+1 }}</span>
                </label>
            </li>
        </ul>
</template>
<script>
export default{
    name: 'CheckboxList',
    props:['attributesList'],
}
</script>

<style lang="scss" scoped>
@import '@/style/SCSS/style.scss';
    .list{
        margin-top: 16px;
        overflow-y: scroll;
        height: 180px;
    
        &::-webkit-scrollbar {
            width: 3px;
        }

        &::-webkit-scrollbar-thumb {
            width: 3px;
            height: 121px;
            border-radius: 10px;
            background-color: $--color-icons;
        } 
    }
    .item{
        margin-top: 12px;
    }
    .item__label{
        display: flex;
        flex-direction: row;
    }
    .item__count-product{
        margin-left: auto;
        margin-right: 16px;
        color: $--color-font-second;
    }
</style>