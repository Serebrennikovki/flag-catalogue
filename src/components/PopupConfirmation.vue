<script>
    export default{
        name: 'PopupComfirmation',
        props: {
            show:{
                type:Boolean,
                default: false
            }
        }
    }
</script>

<template>
    <div class="popup popup_function_confirmation">
                    <div class="popup__overlay"></div>
                    <div class="popup__window">
                        <button class="popup__close-button " type="button"></button>
                        <p class="popup__textConfirmation">Вы успешно зарегистрировались!</p>
                        <button class="popup__save-button" type="submit">К покупкам</button>
                    </div>
                </div>
    </template>

<style >
.popup{
    position: fixed;
    z-index: 10;
    color: black;
    background: rgba(0, 0, 0, 0.6);
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    justify-content: center;
    align-items: center;
    display: flex;
    visibility: hidden;
    opacity: 0;
    transition: visibility 0.2s, opacity 0.2s linear;
    /*visibility: visible;
    opacity: 1;*/
}

.popup__overlay{
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 0;
    background: rgba(252, 213, 186, 0.8);
}

.popup__window{
    position: relative;
    background-color:white;
    width: 687px;
    background: #FFFFFF;
    box-shadow: 8px 16px 32px rgba(255, 102, 51, 0.2);
    border-radius: 4px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.popup__save-button{
    font-family: 'Rubik';
    font-style: normal;
    font-weight: 400;
    font-size: 24px;
    line-height: 150%;
    width: 260px;
    height: 68px;
    background: #FCD5BA;
    border:none;
    border-radius: 4px;
    text-align: center;
    color: #FF6633;
    margin: 40px auto;
}
.popup__close-button{
    background-image: url('../assets/ButtonclosePopup.png');
    width: 40px;
    height: 40px;
    border: none;
    align-self: end;
}
.popup__textConfirmation{
    max-width: 315px;
    margin: 32px auto 0;
    font-family: 'Rubik';
    font-style: normal;
    font-weight: 700;
    font-size: 24px;
    line-height: 150%;
    text-align: center;
    color: #70C05B;
}

</style>
