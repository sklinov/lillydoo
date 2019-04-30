<template>
    <div class="screen">
        <div class="cell">
            <img :src="current.image" :alt="current.size" class="image__main"/>
        </div>
        <div class="cell">
            <h3>{{text.title}}</h3>
            <p class="text">{{text.choosesize}}</p>
            <div class="selector" v-for="pack in trialPacks" :key="pack.size" v-on:click="changeImage(pack.size)" >       
                <input type="radio" name="sizes-selector" class="selector__radio">
                <label class="selector__item">
                    <div class="selector__main">{{pack.size}}</div>
                    <div class="selector__extra">({{pack.kg}})</div>  
                </label>
            </div>
            <p class="text">
               {{text.desc}}
            </p>
            <ul class="text" v-for="listitem in text.extra">
                <li class="text" v-html="listitem">
                </li>
            </ul>
            <button class="button button-wide">{{text.buttonText}}</button>
        </div>
    </div>
</template>

<script>
import stickerUrl from '../assets/img/oeko.png';
import trialPacks from '../assets/products/trialPacks.json';
import items      from '../assets/products/items.json';

export default {
    name: 'Product',
    methods: {
        changeImage : function(size) {
            this.current = this.trialPacks[size-1];
        },
    },
    data() {
        return {
            trialPacks,
            items,
            current : trialPacks,
            text: {
                    title : "Unser gratis testpaket",
                    desc : "Teste jetzt unsere Windeln und Feuchttücher. Wir zahlen die Produkte, Du nur den Versand.",
                    buttonText : "IN DEN WARENKORB LEGEN",
                    choosesize : "WÄHLE DEINE GRÖSSE",
                    extra : [
                             "<span class='highlighted'>Automatischer Übergang ins jederzeit kündbare Windel-Abo für 49,50 € pro Lieferung.</span>",
                             "Preise inkl. MwSt., ggf. zzgl. <span class='highlighted'>Versandkosten.</span>"
                            ]
                   }
        }
    },
    created() {
        this.current = this.trialPacks[0];
    }

}
</script>

<style lang="scss" scoped>
$grey : #979797;
.image__main {
    width: 50vw;
    max-width: 550px;
    text-align: center;
}

.selector {
    display: inline-flex;
    .selector__item {
        color: $grey;
        border: 1px solid $grey;
        margin: 3px;
        text-align: center;
        font-size : 0.7em;
        width: 4.5em;
        line-height: 1em;
        padding: 5px;
        
        &:hover {
            background-color: #00afab;
            color: white;
        }
    }
    .selector__extra {
        font-size : 0.5em;
        text-transform: uppercase;
    }
    .selector__radio {
        display: none;
    }
}

.checkeditem {
    background-color: #00afab;
    color: white;
}
 
.button-wide {
    width: 90%;
} 
</style>
