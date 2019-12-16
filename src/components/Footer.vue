<template>
  <v-footer class="font-size" height="45px" color="grey darken-3">
    <div class="">
      <v-icon size="18" class="mr-1" color="orange">mdi-radiobox-marked</v-icon>
      <span class="orange-box">NO AR</span>
    </div>
    <div class="space">
      <v-icon size="18" class="mx-2" color="grey">mdi-television</v-icon>
      <span class="date-white">ENCONTRO - 10:00</span>
    </div>
    <div>
      <v-icon size="18" class="mx-1" color="grey">mdi-update</v-icon>
      <span class="date-white">Última atualização em 10:28</span>
    </div>
    <v-spacer></v-spacer>
    <div>
      <span class="date"
        >Quinta, <span class="date-white">30</span> de
        <span class="date-white">Maio</span> de
        <span class="date-white">2019</span>
      </span>
      <span class="time">// 10:30:42</span>
    </div>
  </v-footer>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.space {
  margin: 0 40px;
}
.time {
  color: orange;
  font-weight: 500;
  margin-left: 10px;
  font-size: 19px;
}
.font-size {
  font-size: 12px;
}
.date-white {
  color: white;
}
.date {
  color: grey;
  font-size: 14px;
}
.orange-box {
  color: orange;
}
</style>
