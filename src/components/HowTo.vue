<template>
    <div class="screen screen-grey screen-column screen-padding3em">
        <h2>{{text.header}}</h2>
        <div  class="container">
            <div class="item" v-for="howto in howtos">
                <img :src="howto.image" class="item__image">
                <div class="item__header">{{howto.header}}</div>
                <div class="item__text">{{howto.text}}</div>
            </div>
        </div>
        <a class="link link-narrow" :href="links.howtobottom.url">{{links.howtobottom.text}}</a>
    </div>
</template>


<script>
import howtos from '../assets/products/howtos.json';

export default {
    name: 'HowTo',
    data () {
        return {
            howtos,
            links: {
                howtobottom: {
                    text: "Erfahre hier mehr über das LILLYDOO Windel-Abo.",
                    url: "https://www.lillydoo.com/de/windel-abo"
                } 
            },
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
.link-narrow {
    max-width: 25ch;
    text-align: center;
    margin-top: 1.5em;
    margin-bottom: 1.5em;
    margin-left: auto;
    margin-right: auto;
    font-size: 0.75em;
}

</style>
