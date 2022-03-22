<template>
  <div id="app" class="main">
    <BaseHeader></BaseHeader>
    <div class="container">
      <div class="container__item">
        <div v-if="isLoading == true">
          <LoadingCustom />
        </div>
        <CustomCalendar></CustomCalendar>
        <CardInfo v-for="card in malePatients" :key="card" :info="card" />
      </div>
      <div class="container__item">
        <CustomSearch></CustomSearch>
        <div v-if="isLoading == true">
          <LoadingCustom />
        </div>
        <HistorialInfo
          v-for="historial in femalePatients"
          :key="historial"
          :info="historial"
        />
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import LoadingCustom from "./components/LoadingCustom.vue";
import BaseHeader from "./components/BaseHeader.vue";
import CardInfo from "./components/CardInfo.vue";
import HistorialInfo from "./components/HistorialInfo.vue";
import CustomSearch from "./components/CustomSearch.vue";
import CustomCalendar from "./components/CustomCalendar.vue";


export default {
  name: "App",
  components: {
    BaseHeader,
    CardInfo,
    HistorialInfo,
    CustomSearch,
    LoadingCustom,
    CustomCalendar
  },
  data() {
    return {
      femalePatients: [],
      malePatients: [],
      isLoading: false,
    };
  },

  methods: {
    async getToken() {
      this.isLoading = true;
      const response = await axios.post(
        "http://test.amobamed.com/oauth/token",
        {
          grant_type: "password",
          client_id: 2,
          client_secret: "rDnLA1OfY8nHovztVBU8rcvOP9K5iH7LngUZNIzB",
          username: "pruebas@amobasoftware.com",
          password: "123456",
        }
      );
      return response.data.token_type + " " + response.data.access_token;
    },
    async getPatients() {
      let token = await this.getToken();

      let headers = {
        Authorization: token,
      };

      const response = await axios.post(
        "http://test.amobamed.com/api/v1/patient/all",
        {
          doctor_id: 1,
          company_id: 1,
        },
        { headers }
      );
      this.femalePatients = response.data.filter(
        (data) => data?.person?.people_sex == "F"
      );
      this.malePatients = response.data.filter(
        (data) => data?.person?.people_sex == "M"
      );
      this.isLoading = false;
    },
  },
  mounted() {
    this.getPatients();
  },
};
</script>

<style lang="scss" src="./assets/css/main.scss"></style>
