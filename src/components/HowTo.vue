<template>
    <div class="screen screen-grey screen-column">
        <h2>{{text.header}}</h2>
        <div  class="container">
            <div class="item" v-for="howto in howtos">
                <img :src="howto.image" class="item__image">
                <div class="item__header">{{howto.header}}</div>
                <div class="item__text">{{howto.text}}</div>
            </div>
        </div>
    </div>
</template>


<script>
import howtos from '../assets/products/howtos.json';

export default {
    name: 'HowTo',
    data () {
        return {
            howtos,
            text: {
                header: "Wie es funktioniert"
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
        max-width: 25ch;
    }
}

</style>
