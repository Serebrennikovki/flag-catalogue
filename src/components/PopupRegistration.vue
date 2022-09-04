<script>
    
    export default{
        name: 'PopupRegistration',
        props: {
            show:{
                type:Boolean,
                default: false
            }
        },
        methods: {
            closePopupRegistration(){
                console.log('closepopup registr');
                this.$emit('update:show',false);
            }
        }
    }
</script>

<template>
    <div class="popup popup_function_registration" v-if="show">
        <div class="popup__overlay" @click="closePopupRegistration"></div>
        <form class="popup__window">
            <button class="popup__close-button" type="button" @click="closePopupRegistration"></button>
            <h1 class="popup__title">Регистрация</h1>
            <fieldset class="form__fieldset">
                <legend class="popup__subtitle">Обязательные поля</legend>
                <div class="form__fieldsetSection form__fieldsetSection_type_required">
                    <div class="input input_type_phone">
                        <label class="input__title" for="phone">Телефон</label>
                        <input class="input__el" type='tel' id="phone" name="phone" v-bind:value="phone" maxlength='10' inputmode="tel" autocomplete="on" required pattern="\+?[0-9\s\-\(\)]+"/>
                    </div>
                    <div class="input input_type_name">
                        <label class="input__title" for="name">Имя</label>
                        <input class="input__el" type='text' id="name" v-bind:value="name" name="name" autocomplete="on" required/>
                    </div>
                    <div class="input input_type_surname">
                        <label class="input__title" for="surname">Фамилия</label>
                        <input class="input__el" type='text' id="surname" v-bind:value="surname" name="surname" autocomplete="on" required/>
                    </div>
                    <div class="input input_type_birthDate">
                        <label class="input__title" for="birthDate">Дата рождения</label>
                        <input class="input__el" type='date' id="birthDate" v-bind:value="birthDate" name="birthDate" required/>
                    </div>
                    <div class="input input_type_passwordNew">
                        <label class="input__title" for='passwordNew'>Пароль</label>
                        <input class="input__el" type='password' id="passwordNew" name="passwordNew" required minlength='5'/>
                        <label v-bind:class="['input__passwordEye', isChoosen ? 'input__passwordEye_type_choosen' : '']"><input type="checkbox" class='input__passwordCheckbox'/></label>
                    </div>
                    <div class="input input_type_passwordCopy">
                        <label class="input__title" for="passwordCopy">Повторите пароль</label>
                        <input class="input__el" type='password' id="passwordCopy" name="passwordCopy" minlength='5' required/>
                        <label v-bind:class="['input__passwordEye', isChoosen ? 'input__passwordEye_type_choosen' : '']"><input type="checkbox" class='input__passwordCheckbox'/></label>
                    </div>
                    <div class="input input_type_city">
                        <label class="input__title" for="city">Населенный пункт</label>
                        <select class="input__el" type='search' id="city" name="city" required>
                            <option value="value1">Екатеринбург</option>
                            <option>Каменск-Уральский</option>
                            <option>Богданович</option>
                            <option>Ревда</option>
                        </select>
                    </div>
                    <div class="input input_type_gender">
                        <label class="input__title" for="city">Пол</label>
                        <div class="input__el input__el_type_gender">
                            <button type="button" class="input__button input__button_type_active ">Мужской</button>
                            <button type="button" class="input__button">Женский</button>
                        </div>
                    </div>
                </div>
            </fieldset>
            <fieldset class="form__fieldset">
                <legend class="popup__subtitle">Необязательные поля</legend>
                <div class="form__fieldsetSection form__fieldsetSection_type_optional">
                    <div class="input input_type_numberCard">
                        <label class="input__title" for="numberCard">Номер карты</label>
                        <input class="input__el" type='numberCard' id="" name="numberCard"/>
                    </div>
                    <div class="input input_type_email">
                        <label class="input__title" for="email">Email</label>
                        <input class="input__el" type='email' id="email" name="email"/>
                    </div>
                    <div class="input input_type_stateCard">
                        <input class="input__el input__el_type_stateCard" type='checkbox' id="stateCard" name="stateCard"/>
                        <label class="input__title input__title_type_checkbox" for="stateCard">У меня нет карты лояльности</label>
                    </div>
                </div>
            </fieldset>
            <button class="popup__save-button" type="submit">Продолжить</button>
        </form>
    </div>
</template>

<style scoped>
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
    visibility: visible;
    opacity: 1;
}
.popup__title{
    font-family: 'Rubik';
    font-style: normal;
    font-weight: 700;
    font-size: 24px;
    line-height: 150%;
    text-align: center;
    color: #414141;
}
.form__fieldset{
    margin: 40px auto 0;
    max-width: 452px;
    border:none;
}
.form__fieldsetSection{
    display: grid;
    margin: 24px 0 0;
    grid-template-columns: 260px 260px;
    grid-auto-rows: 64px;
    grid-row-gap: 16px;
    grid-column-gap: 32px;
}
.form__fieldsetSection_type_required{
    grid-template-areas:"phone birthDate"
                        "name city"
                        "surname gender"
                        "passwordNew ."
                        "passwordCopy .";
}
.form__fieldsetSection_type_optional{
    grid-template-areas:"numberCard email"
                        "stateCard .";

}
    
.popup__subtitle{
    font-family: 'Rubik';
    font-style: normal;
    font-weight: 700;
    font-size: 18px;
    line-height: 150%;
    text-align: center;
    color: #414141;
}
.input{
    display:flex;
    position: relative;
    flex-direction: column;
    justify-content: flex-start;
}

.input_type_gender{
    grid-area: gender;
}
.input_type_passwordNew{
    grid-area: passwordNew;
}
.input_type_passwordCopy{
    grid-area: passwordCopy;
}
.input_type_birthDate{
    grid-area: birthDate;
}
.input_type_phone{
    grid-area: phone;
}
.input_type_name{
    grid-area: name;
}
.input_type_surname{
    grid-area: surname;
}
.input_type_city{
    grid-area: city;
}
.input_type_stateCard{
    flex-direction:row;
}
.input__title{
    font-family: 'Rubik',sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 150%;
    color: #8F8F8F;
    text-align: left;
}
.input__title_type_checkbox{
    margin: 0 0 0 8px;
}
.input__el{
    box-sizing: border-box;
    padding: 8px 16px;
    width: 260px;
    height: 40px;
    background: #FFFFFF;
    border: 1px solid #BFBFBF;
    border-radius: 4px;
}
.input__el:focus{
    outline: 0;
    outline-offset: 0;
    box-shadow: 4px 8px 16px rgba(112, 192, 91, 0.2);
    border: 1px solid #70C05B;
    caret-color: #70C05B;
}
.input__el_type_gender{
    display: flex;
    flex-direction: row;
    background: #F3F2F1;
    padding:0;
    align-items: center;
    justify-content: center;
}
.input__el_type_stateCard{
    padding: 0;
    margin: 0;
    width: 20px;
    height: 20px;
}
.input__passwordEye{
    width: 23px;
    height: 23px;
    position: absolute;
    bottom: 8.5px;
    right: 8.5px;
    background-image: url(../assets/eyeOff.png);
    object-fit: contain;
}
.input__passwordEye_type_choosen{
    background-image: url(../assets/eyeOpen.png);
}
.input__passwordCheckbox{
    position: relative;
    width: 23px;
    height: 23px;
    cursor: pointer;
    z-index: -1;
}
.input__button{
    margin:auto 0;
    border:none;
    padding: 8px;
    gap: 8px;
    width: 126px;
    height: 32px;
    font-family: 'Rubik';
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 150%;
    text-align: center;
    color: #414141;
    border-radius: 4px;
}
.input__button_type_active{
    background: #70C05B;
    color: #FFFFFF;
}

</style>