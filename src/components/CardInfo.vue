<template>
  <div>
    <div
      :class="dropDownOpen ? openClass : 'card'"
      @click="dropDownOpen = !dropDownOpen"
    >
      <div class="card__options">
        <img class="cerrar" src="../assets/img/icon_copiar_pegar.svg" alt="" />
        <span class="card__hora">10:00 / 11:00</span>
        <img class="cerrar" src="../assets/img/equis.svg" alt="" />
      </div>
      <div class="card__info">
        <div class="card__details">
          <img
            class="card__img"
            :src="info.person.ima_profile_person"
            alt="Imagen de perfil"
          />
          <div>
            <h4 class="card__name">
              {{ info.person.people_first_name }}
              {{ info.person.people_surnames }}
            </h4>
            <div class="card__tipo">
              <div class="card__p">
                <p>Consulta Online</p>
                <div class="card__description">
                  <p>40 años 3 Meses 5 días</p>
                </div>
              </div>
              <span class="card__hora">10:00 / 11:00</span>
            </div>
          </div>
        </div>
        <div class="card__expand">
          <img class="mas" src="../assets/img/mas.svg" alt="" />
        </div>
      </div>
      <transition name="slide">
        <div class="card__more" v-if="dropDownOpen">
          <div class="card__link">
            <img src="../assets/img/icon_ficha_historica2.svg" alt="" />
            <p>Ficha historica</p>
          </div>
          <div class="card__link">
            <img src="../assets/img/Nueva_consulta.svg" alt="" />
            <p>Nueva Consulta</p>
          </div>
          <div class="card__link">
            <img src="../assets/img/Vector.png" alt="" />
            <p>Reenviar cita</p>
          </div>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardInfo",
  data: () => ({
    dropDownOpen: false,
    openClass: "card active",
  }),
  props: {
    info: [],
  },
};
</script>
