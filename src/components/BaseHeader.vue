<template>
  <div>
    <header class="header">
      <div class="header__item">
        <div class="header__bars"></div>

        <img
          class="header__logo"
          src="../assets/img/logo_amoba.svg"
          alt="logo amoba"
        />
      </div>
      <div class="header__item">
        <p>Dr. Juan Sarmiento Test</p>
        <img
          class="header__icon"
          src="../assets/img/icon_engranaje.svg"
          alt="icon"
        />
        <img
          class="header__perfil"
          src="../assets/img/user.png"
          alt="image user"
        />
      </div>


    </header>
    <!---------nav--------->
    <nav class="nav">
      <ul class="nav__list">
        <div class="nav__item">
          <li>
            <a class="nav__link nav__link--active--noti" href="#">
              <img src="../assets/img/icon_reloj.svg" alt="Icono reloj"
            /></a>
          </li>
          <li class="nav-xs">
            <a class="nav__link  nav__link--active--btn" href="#">Citas</a>
          </li>
           <li  class="nav-xs">
            <a class="nav__link" href="#">Consultas</a>
          </li>
        </div>

        <div class="nav__item">
         
          <li>
            <a class="nav__link" href="#">
              <img class="nav__icon"
                src="../assets/img/nuevo_paciente.svg"
                alt="Icono paciente"
              />
              <span>Nuevo </span> Paciente
            </a>
          </li>
          <li>
            <a class="nav__link nav__link--active" href="#">
              <img class="nav__icon"
                src="../assets/img/icon_ficha_historica.svg"
                alt="Icono ficha historica"
              />
              Historia <span>&nbsp; clinica</span></a
            >
          </li>
          <li>
            <a class="nav__link" href="#">
              <img class="nav__icon" src="../assets/img/agenda.svg" alt="Icono ficha historica" />
              Agenda
            </a>
          </li>
        </div>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: "BaseHeader",

};
</script>
