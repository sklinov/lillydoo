<template>
    <div class="screen screen-column">
        <h2>{{text.header}}</h2>
        <div  class="container">
            <div class="item" v-for="item in items">
                <img :src="item.image" class="item__image">
                <div class="item__header">{{item.name}}</div>
                <ul>
                    <li class="item__text" v-for="desc in item.desc">{{desc.text}}</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>

import items      from '../assets/products/items.json';

export default {
 name: 'Contents',
 data () {
        return {
            items,
            text: {
                header: "Dein Testpaket enthält"
            }
        }
    }
}
</script>

<style lang="scss" scoped>
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-around;
    width: 70vw;
    margin-left: auto;
    margin-right: auto;
}
.item {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    max-width: 35ch;
    text-align: center;
    
    .item__image {
        margin: 20px;
    }
    .item__header {
        margin: 10px;
        font-weight: 600;
    }
    .item__text {
        margin: 5px;
        font-size: 0.75em;
        max-width: 35ch;
    }
}

</style>

