<script>
    export default {
    name: "BreadCrumbs"
}
</script>

<template>
    <ul class="breadCrumbs">
        <li><a href="#" class="breadCrumbs__link">Главная</a></li>
        <li><a href="#" class="breadCrumbs__link breadCrumbs__link_type_active">Каталог</a></li>
    </ul>
</template>

<style>
    .breadCrumbs{
        padding: 0;
        width: 1208px;
        margin: 27px auto 0;
        display:flex;
        flex-direction: row;
        list-style-type: none;
        justify-content: left;
        align-items: center;
    }
    .breadCrumbs__link{
        list-style-type: none;
        text-decoration: none;
        font-family: 'Rubik',sans-serif;
        font-style: normal;
        font-weight: 400;
        font-size: 12px;
        line-height: 150%;
        color: #414141;
    }
    .breadCrumbs__link_type_active{
        color: #8F8F8F;
    }
    .breadCrumbs li+li:before{  
        content: url(../assets/chevron-right.png);
        margin: 0 16px;
        width: 24px;
        height: 24px;
        color: #414141;
    }
    .breadCrumbs li{
        display: flex;
        flex-direction: row;
        align-items: center;
    }
</style>