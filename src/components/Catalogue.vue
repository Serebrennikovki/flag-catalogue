<template>
    <section name="catalogueGoods" class="catalogue">
        <h1 class="catalogue__title">
            Каталог
        </h1>
        <ul class="catalogue__goods">
            <li :key="categorie.id" v-for="categorie in categories" v-bind:class="['catalogue__item', 'catalogue__item-'+categorie.id]">
                <a class="catalogue__itemLink" :href='categorie.href' >
                    <img v-bind:class="['catalogue__itemImg', categorie.isBrown ? 'catalog__itemImg_type_brown': '']" :src="categorie.src" :alt='categorie.title' />
                    <h2 class="catalogue__itemTitle">{{categorie.title}}</h2>
                    <div v-bind:class="['catalogue__itemOverlay', categorie.isBrown ? 'catalogue__itemOverlay_type_brown':'catalogue__itemOverlay_type_green']"></div>  
                </a>
            </li>
        </ul>
    </section>
</template>
<script>
    import imgMilk from '../assets/imgMilk.png'
    import imgBread from '../assets/imgBread.png'
    import imgFruits from '../assets/imgFruits.png'
    import imgPasta from '../assets/imgPasta.png'
    import imgHealth from '../assets/imgHealth.png'
    import imgZoo from '../assets/imgZoo.png'
    import imgKids from '../assets/imgKids.png'
    import imgMeat from '../assets/imgMeat.png'
    import imgNonFood from '../assets/imgNonFood.png'

    export default{
        name: 'CatalogueGoods',
        data(){
            return{
                categories:[
                    {id:1, title:'Молоко, сыр, яйцо', src:imgMilk, href:'#', isBrown:false},
                    {id:2, title:'Хлеб', src:imgBread, href:'#', isBrown:true},
                    {id:3, title:'Фрукты и овощи', src:imgFruits, href:'#', isBrown:false},
                    {id:4, title:'Бакалея', src: imgPasta, href:'#', isBrown:false},
                    {id:5, title:'Здоровое питание', src: imgHealth, href:'#', isBrown:false},
                    {id:6, title:'Зоотовары', src:imgZoo, href:'#', isBrown:false},
                    {id:7, title:'Детское питание', src:imgKids, href:'#', isBrown:false},
                    {id:8, title:'Мясо, птица, колбаса', src:imgMeat, href:'#', isBrown:false},
                    {id:9, title:'Непродовольственные товары', src:imgNonFood, href:'#',  isBrown:false}
                ],

            }
        }
    }
</script>

<style>
    .catalogue{
        width: 1208px;
        margin: 0 auto; 
        }
    .catalogue__title{
        font-family: 'Rubik',sans-serif;
        font-style: normal;
        font-weight: 700;
        font-size: 64px;
        line-height: 150%;
        color: #414141;
        text-align: left;
    }
    .catalogue__goods{
        list-style-type: none;
        display: grid;
        grid-template-columns: repeat(4, 272px);
        grid-auto-rows:  200px;
        grid-gap: 40px;
    }
    .catalogue__item{
        position: relative;
        height: 200px;
        box-shadow: 1px 2px 4px rgba(112, 192, 91, 0.2);
        border-radius: 4px;
        overflow: hidden;
    }
    .catalogue__item-1{
        grid-column-start: 1;
        grid-column-end: 3;
        grid-row: 1;
    }
    .catalogue__item-6{
        grid-column-start: 3;
        grid-column-end: 5;
        grid-row: 2;
    }
    .catalogue__item-8{
        grid-column-start: 2;
        grid-column-end: 4;
        grid-row: 3;
    }

    .catalogue__itemImg{
        object-fit: contain;
        position: relative;
        z-index: 1;
    }
    .catalogue__itemLink{
        position: relative;
        height: 100%;
        display: block;
    }
    .catalogue__itemOverlay{
        position: absolute;
        top:0;
        bottom:0;
        right:0;
        left:0;
        z-index: 1;
          }
    .catalogue__itemOverlay_type_green{
        background: linear-gradient(180deg, rgba(112, 192, 91, 0) 0%, #70C05B 82.81%);
    }
    .catalogue__itemOverlay_type_brown{
        background: linear-gradient(180deg, rgba(255, 102, 51, 0) 0%, #FF6633 100%);
    }

    .catalogue__itemTitle{
        position: absolute;
        bottom: 10px;
        left: 10px;
        color: white;
        font-family: 'Rubik';
        font-style: normal;
        font-weight: 700;
        font-size: 18px;
        line-height: 150%;
        z-index:2;

    }
</style>