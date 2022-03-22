<template>
  <div>
    <div class="card historial" @click="dropDownOpen = !dropDownOpen">
      <div class="card__info">
        <div class="card__details">
          <img
            class="card__img"
            :src="info.person.ima_profile_person"
            alt="Imagen de perfil"
          />
          <div>
            <h4 class="card__name">{{info.person.people_first_name}} {{info.person.people_surnames}}</h4>
          </div>
        </div>
        <div class="card__tipo">
          <span class="card__hora">0105254361</span>
        </div>
        <div class="card__expand historial__expand">
          <img class="mas" src="../assets/img/icon_correo.svg" alt="" />
          <img class="mas" src="../assets/img/icon_bote de basura.svg" alt="" />
        </div>
      </div>
      <transition name="slide">
        <div class="card__more" v-if="dropDownOpen">
          <p>Info</p>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: "HistorialInfo",
  data: () => ({
    dropDownOpen: false,
  }),
  props:{
   info:[]
  }
};
</script>
