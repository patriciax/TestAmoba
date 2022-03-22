<template>
  <div>
     <div class="search">
      <form>
        <div class="search__form">
          <div class="search__input">
            <select name="Nombre"  class="">
              <option value="">Nombre </option>
              <option>Nombre 2</option>
            </select>
          </div>
          <div class="">
            <input
              type="text"
              class="f"
              v-model="searchText"
              placeholder=""
            />
          </div>
        </div>
      </form>
      <div class="search__icons">
        <img src="../assets/img/icon.svg" alt="" />
        <img src="../assets/img/icon1.svg" alt="" />
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "CustomSearch",

};
</script>
