<template>
    <form class="form" id="form" @submit.prevent='submitForm'>
      <div class="form__input">
        <div class="form__block_title block">
          <div class="input-block">    
            <label class="form__name">Имя*</label>    
            <input class="form__name_input" type='text'
             v-model="nameP" 
             :class="{invalid:($v.nameP.$dirty && !$v.nameP.required) || ($v.nameP.$dirty && !$v.nameP.alpha) || (!$v.nameP.minLength &&$v.nameP.$dirty)}">    
            <span class="form__name_error" v-if='$v.nameP.$dirty && !$v.nameP.required'>Заполните поле имя</span>   
            <span class="form__name_error" v-if='$v.nameP.$dirty && !$v.nameP.alpha || !$v.nameP.minLength'>Введите корректное имя</span>  
          </div>
          <div class="input-block">    
            <label class="form__name">Фамилия*</label>    
            <input class="form__name_input" type='text' v-model="surname"
            :class="{invalid:($v.surname.$dirty && !$v.surname.required) || ($v.surname.$dirty && !$v.surname.alpha) || (!$v.surname.minLength &&$v.surname.$dirty)}"
            >    
            <span class="form__name_error" v-if='$v.surname.$dirty && !$v.surname.required'>Заполните поле фамилия</span>   
            <span class="form__name_error" v-if='$v.surname.$dirty && !$v.surname.alpha || !$v.surname.minLength'>Введите корректное фамилия</span>   
          </div>
          <div class="input-block">    
            <label class="form__name">Отчество</label>    
            <input class="form__name_input" type='text' v-model="fatherName"
            :class="{invalid:($v.fatherName.$dirty && !$v.fatherName.alpha)}"
            >
            <span class="form__name_error" v-if='$v.fatherName.$dirty && !$v.fatherName.alpha'>Введите корректное Отчество</span>      
          </div>
          <div class="input-block">    
            <label class="form__name">Дата рождения*</label>    
            <input class="form__name_input" type='date' v-model="date"
            :class="{invalid:($v.date.$dirty && !$v.date.required)}"
            >    
            <span class="form__name_error" v-if='$v.date.$dirty && !$v.date.required'>Введите корректную дату</span>   
          </div>
          <div class="input-block">    
            <label class="form__name">Номер телефона*</label>    
            <input class="form__name_input" type='tel' v-model="phone"
            :class="{invalid:($v.phone.$dirty && !$v.phone.required) || ($v.phone.$dirty && !$v.phone.minLength) || ($v.phone.$dirty && !$v.phone.numeric)}"
            >    
            <span class="form__name_error" 
            v-if='$v.phone.$dirty && !$v.phone.required'
            >Введите телефон</span>
            <span class="form__name_error"
            v-if='$v.phone.$dirty && !$v.phone.minLength || !$v.phone.numeric'
            >Введите корректный номер</span>      
          </div>
          <div class="input-block">    
            <label class="form__name">Пол</label>    
            <select class="form__name_input" v-model="gender">
              <option>Мужской</option>
              <option>Женский</option>
            </select>      
          </div>
          <div class="input-block">    
            <label class="form__name">Группа клиентов</label>    
            <select class="form__name_input" v-model="groop">
              <option>Vip</option>
              <option>Проблемные</option>
              <option>ОМС</option>
            </select>   
          </div>
          <div class="input-block">    
            <label class="form__name">Лечащий врач</label>    
            <select class="form__name_input" v-model="doctor">
              <option>Иванов</option>
              <option>Захаров</option>
              <option>Чернышев</option>
            </select>
          </div>
        </div>
        <div class="form__block_home block">
          <div class="input-block">    
            <label class="form__name">Индекс</label>    
            <input  class="form__name_input" type='text' v-model="indexCity"
            :class="{invalid:($v.indexCity.$dirty && !$v.indexCity.numeric)}"
            >    
            <span class="form__name_error" v-if='$v.indexCity.$dirty && !$v.indexCity.numeric'>Введите корректный Индекс</span>
          </div>
          <div class="input-block">    
            <label class="form__name">Страна</label>    
            <input  class="form__name_input" type='text' v-model="counter"
            :class="{invalid:($v.counter.$dirty && !$v.counter.alpha)}"
            >
            <span class="form__name_error" v-if='$v.counter.$dirty && !$v.counter.alpha'>Введите корректно страну</span>      
          </div>
          <div class="input-block">    
            <label class="form__name">Область</label>    
            <input  class="form__name_input" type='text' v-model="region"
            :class="{invalid:($v.region.$dirty && !$v.region.alpha)}"
            >
            <span class="form__name_error" v-if='$v.region.$dirty && !$v.region.alpha'>Введите корректно облость</span>    
          </div>
          <div class="input-block">    
            <label class="form__name">Город*</label>    
            <input class="form__name_input" type='text' v-model="city"
            :class="{invalid:($v.city.$dirty && !$v.city.required) || ($v.city.$dirty && !$v.city.alpha) || (!$v.city.minLength &&$v.city.$dirty)}"
            >    
            <span class="form__name_error" v-if='$v.city.$dirty && !$v.city.required'>Введите Город</span>   
            <span class="form__name_error" v-if='$v.city.$dirty && !$v.city.alpha || !$v.city.minLength'>Введите корректный город</span>  
          </div>
          <div class="input-block">    
            <label class="form__name">Улица</label>    
            <input  class="form__name_input" type='text' v-model='street'
            :class="{invalid:($v.street.$dirty && !$v.street.alpha)}"
            >   
             <span class="form__name_error" v-if='$v.street.$dirty && !$v.street.alpha'>Введите корректно улицу</span> 
          </div>
          <div class="input-block">    
            <label class="form__name">Дом</label>    
            <input  class="form__name_input" type='text' v-model="home">     
          </div>
        </div>
        <div class="form__block_doc block">
          <div class="input-block">
            <label class="form__name">Тип документа*</label>    
            <select class="form__name_input" v-model="typeDoc"
            :class="{invalid:($v.typeDoc.$dirty && !$v.typeDoc.required)}"
            >
              <option>Паспорт</option>
              <option>Свидетельство о рождении</option>
              <option>Вод. удостоверения</option>
            </select>
            <span
            class="form__name_error" v-if='$v.typeDoc.$dirty && !$v.typeDoc.required'
          >Выберете тип документа</span>
          </div>
          <div class="input-block">    
            <label class="form__name">Серия</label>    
            <input  class="form__name_input" type='text' v-model="serialDok"
            :class="{invalid:($v.serialDok.$dirty && !$v.serialDok.numeric)}"
            >
            <span class="form__name_error" v-if='$v.serialDok.$dirty && !$v.serialDok.numeric'>Введите корректный серийный номер</span>  
          </div>
          <div class="input-block">    
            <label class="form__name">Номер</label>    
            <input  class="form__name_input" type='text' v-model="numberDok"
            :class="{invalid:($v.numberDok.$dirty && !$v.numberDok.numeric)}"
            >
            <span class="form__name_error" v-if='$v.numberDok.$dirty && !$v.numberDok.numeric'>Введите корректный номер</span>      
          </div>
          <div class="input-block">    
            <label class="form__name">Кем выдан</label>    
            <input  class="form__name_input" type='text' v-model="whyTake"
            :class="{invalid:($v.whyTake.$dirty && !$v.whyTake.alpha)}"
            >
            <span class="form__name_error" v-if='$v.whyTake.$dirty && !$v.whyTake.alpha'>Заполните поле правильно</span>    
          </div>
          <div class="input-block">    
            <label class="form__name">Дата выдачи*</label>    
            <input class="form__name_input" type='date' v-model="dateTake"
            :class="{invalid:($v.dateTake.$dirty && !$v.dateTake.required)}"
            >    
            <span class="form__name_error" v-if='$v.dateTake.$dirty && !$v.dateTake.required'>Введите корректную дату</span> 
          </div>
            <div class="input-block">    
            <label class="form__name">Не отпрвлять СМС<input   type="checkbox" class="form__check" v-model="check"></label>    
          </div>
        </div>
      </div>
      <button class="buttonSubmit" type="submit">Отправить</button>
    </form>
</template>

<script>
import {required,minLength,numeric,alpha} from 'vuelidate/lib/validators'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: ()=>({
    nameP: '',
    surname: '',
    date: '',
    phone: '',
    city: '',
    dateTake: '',
    fatherName:'',
    doctor: '',
    groop: '',
    gender:'',
    typeDoc: '',
    indexCity:'',
    counter: '',
    region: '',
    street: '',
    home: '',
    serialDok: '',
    numberDok: '',
    whyTake:'',
    check: ''
  }),
  validations:{
    nameP: {required,alpha,minLength: minLength(2)},
    surname: {required,alpha,minLength: minLength(2)},
    fatherName:{alpha},
    date: {required},
    phone: {required,minLength: minLength(11),numeric},
    city: {required,alpha,minLength: minLength(2)},
    dateTake: {required},
    typeDoc: {required},
    index:{numeric},
    counter: {alpha},
    region: {alpha},
    street: {alpha},
    serialDok: {numeric},
    numberDok: {numeric},
    whyTake: {alpha},
    indexCity:{numeric}
  },
  methods:{
    submitForm(){
    const popup = document.querySelector('.popup');
    if(this.$v.$invalid){

      this.$v.$touch();
      console.log('Ошибка')
      return
    }
    else{
      popup.classList.add('popup__open');
      setTimeout(()=>{
        popup.classList.remove('popup__open');
      },2000);
      const formData={
        namePepol: this.nameP,
        surnamePepol: this.surname,
        datePepole: this.date,
        phonePepole: this.phone,
        cityPepole: this.city,
        dateTakePepole: this.dateTake,
        fatherNamePepole: this.fatherName,
        doctorPepole: this.doctor,
        groopPepole: this.groop,
        genderPepole: this.gender,
        typeDocPepole: this.typeDoc,
        indexCityPepole: this.indexCity,
        counterPepole: this.counter,
        regionPepole: this.region,
        streetPepole: this.street,
        homePepole: this.home,
        serialDokPepole: this.serialDok,
        numberDokPepole: this.numberDok,
        whyTakePepole:this.whyTake,
        checkPepole: this.check 
      }
      this.nameP='';
      this.surname='';
      this.date='';
      this.phone='';
      this.city='';
      this.dateTake='';
      this.fatherName='';
      this.doctor='';
      this.groop='';
      this.gender='';
      this.typeDoc='';
      this.indexCity='';
      this.counter='';
      this.region='';
      this.street='';
      this.home='';
      this.serialDok='';
      this.numberDok='';
      this.whyTake='';
      this.check='';
      return
    }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans&display=swap');

.complitReg{
  display: none;
}
.complitText{
  color: rgb(11, 93, 139);
    font-weight: bolder;
    font-family: 'Open Sans', sans-serif;
}
.form{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 40px;
    background: linear-gradient(to right bottom,rgba(225,225,225,0.7),rgba(225,225,225,0.3));
    border-radius: 2rem;
    max-width: 640px;
}
.form__check{
    margin: 0 0 0 4px;
}
.form__name{
    color: rgb(11, 93, 139);
    font-weight: bolder;
    font-family: 'Open Sans', sans-serif;
}
.form__input{
    display: flex;
    flex-direction: column;
}
.block{
    display:flex;
    flex-wrap: wrap;
    margin-bottom: 40px;
    justify-content: center;
}
.input-block{
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    height: 70px;
    width: 150px;
    margin-right: 10px;
    text-align: center;
    margin-bottom: 10px;
}
.form__name_error{
    color: red;
    font-weight: bolder;
    font-family: 'Open Sans', sans-serif;
    font-size: 12px;
}
.form__name_input{
    padding: 5px;
    border-radius: 5px;
    border:rgb(11, 93, 139) solid 2px;
    color: rgb(11, 93, 139);
    background: rgb(186, 224, 247);
    font-weight: bolder;
    font-family: 'Open Sans', sans-serif;
}
.buttonSubmit{
    height: 50px;
    align-self: center;
    border-radius: 5px;
    border:rgb(11, 93, 139) solid 2px;
    color: rgb(11, 93, 139);
    background: rgb(186, 224, 247);
    font-weight: bolder;
    font-family: 'Open Sans', sans-serif;
}
.invalid{
  border: red 1px solid;
}
</style>
