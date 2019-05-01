<template>
    <div class="screen screen-column screen-padding3em">
        <h2>{{text.header}}</h2>
        <div  class="container">
            <div class="item" v-for="item in itemsFiltered" :key="item.id">
                <div class="item__imagewrapper">
                    <img :src="item.image" class="item__image">
                </div>
                <div class="item__textwrapper">
                    <div class="item__header">{{item.name}}</div>
                    <ul>
                        <li class="item__text" v-for="desc in item.desc">{{desc.text}}</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import items from '../assets/products/items.json';

export default {
    name: 'Contents',
    props: ['filtered'],
    data () {
            return {
                items,
                text: {
                    header: "Dein Testpaket enthält"
                }
            }
        },
    computed : {
        itemsFiltered : function () {
                var filtering = []; 
                if(this.filtered.length)
                {   
                    this.filtered.forEach(element => {
                        this.items.forEach(item => {
                            if(item.id == element.id)
                            {
                                filtering.push(item);
                            }
                        });
                    });
                }
                else {
                    filtering.push(this.items[0]);
                    filtering.push(this.items[1]);
                }
                return filtering;
        }
    }
}
</script>

<style lang="scss" scoped>
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
 //   max-width: 70vw;
    margin-left: auto;
    margin-right: auto;
}
.item {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;

    .item__imagewrapper {
        object-fit: contain;
    }
    .item__image {
        margin: 20px;
        max-width: 150px;
        height: auto;
    }
    
    .item__textwrapper {
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
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

