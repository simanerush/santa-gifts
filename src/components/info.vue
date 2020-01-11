<template>
  <div>
    <v-card
      class="mx-auto"
      color="white"
      width="200px"
    >
        <v-card-text>
        <p class="font-weight-regular">Доставлено лично Дедом Морозом: {{ santacount }} </p>
        <p class="font-weight-regular">Доставлено эльфами-курьерами: {{ elfscount }}</p>
        <p class="font-weight-regular">Доставлено "Почтой России": {{ pochtacount }} </p>
        </v-card-text>
    </v-card>
    <div class = "mt-10">
      <p class = "display-1 text-center">Заказать доставку</p>
        <v-col cols="12" sm="4">
        <div class="my-2">
          <v-btn color="error" dark large @click="santacount += 1">Доставит дед Мороз</v-btn>
        </div>
      <div class="my-2">
          <v-btn color="error" dark large @click="elfscount += 1">Доставит эльф</v-btn>
        </div>
        <div class="my-2">
          <v-btn color="error" dark large @click="pochtacount += 1">Доставит ПР</v-btn>
        </div>
        <div class="my-2">
          <v-btn color="error" dark large @click="pochtacount += 1, santacount += 1, elfscount += 1">Доставка всеми тремя способами</v-btn>
        </div>
        <div class="my-2">
          <v-btn color="error" dark large @click="persist">Сохранить значения на сервер</v-btn>
        </div>
      </v-col>
    </div>
  </div>
</template>

<script>
export default {
    name: "clicker",
    
    data: () => ({
        santacount: 0,
        elfscount: 0,
        pochtacount: 0
    }),

     mounted() {
      if (localStorage.santacount) {
        this.santacount = localStorage.santacount;
      }
      if (localStorage.elfscount) {
        this.elfscount = localStorage.elfscount;
      }
      if (localStorage.pochtacount) {
        this.pochtacount = localStorage.pochtacount;
      }
    },

    methods: {
       persist() {
        localStorage.santacount = this.santacount;
        localStorage.elfscount = this.elfscount;
        localStorage.pochtacount = this.pochtacount
      }
    }

}
</script>

<style>

</style>