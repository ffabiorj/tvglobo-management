<template>
  <nav>
    <v-toolbar flat color="#e5e3e3" height="90" elevation="1">
      <v-icon dark color="deep-orange" class="ml-3" large>mdi-cube-scan</v-icon>
      <span class="mx-4">|</span>
      <v-btn depressed color="white" class="btn-icon btn-custom"
        ><v-icon color="grey">mdi-security</v-icon></v-btn
      >
      <v-btn
        depressed
        color="deep-orange accent-3"
        class="btn-icon btn-custom btn-degrad"
        ><v-icon color="white">mdi-account</v-icon></v-btn
      >
      <v-col cols="3" sm="4" md="3">
        <v-text-field
          label="Pesquisar..."
          solo
          hide-details
          append-icon="mdi-magnify"
          single-line
          light
          height="10"
          class="ml-10"
          style="opacity: 0.2"
        ></v-text-field>
      </v-col>

      <v-spacer></v-spacer>
      <div class="mx-5">
        <v-btn
          depressed
          @click.stop="drawer = !drawer"
          class="mx-2 white btn-custom"
          ><v-icon color="grey" class="btn-icon">mdi-tune</v-icon></v-btn
        >
        <v-btn depressed color="pink" class="mr-1 btn-custom" style="color:white" width="170px">
          <v-icon color="white">mdi-account</v-icon>
          INCLUIR USUÁRIO
        </v-btn>
      </div>
      <span>|</span>
      <div class="mx-4">
        <v-icon class="mr-2">mdi-home</v-icon>
        <v-icon class="mx-2">mdi-settings</v-icon>
        <v-icon class="mx-2">mdi-power-standby</v-icon>
      </div>
    </v-toolbar>
    <v-navigation-drawer
      v-model="drawer"
      width="480px"
      absolute
      temporary
      right
      class="brow lighten-2"
    >
      <v-list-item>
        <v-list-item-content height="280px">
          <v-list-item-title class="title">
            <v-icon class="title-icon">mdi-tune</v-icon>
            <span>FILTROS</span>
            <v-btn
              class="title-btn btn-custom btn-close"
              depressed
              @click.stop="drawer = !drawer"
              right
              elevation="1"
              ><v-icon>mdi-close</v-icon></v-btn
            >
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>
      <v-list-item>
        <v-list-item-content class="text-content">
          Utilize os filtros abaixo para refinar os resultados da tabela, clique
          no botão APLICAR para salvar as alterações.
        </v-list-item-content>
      </v-list-item>
      <v-list-item class="border-grey">
        <v-icon>mdi-calendar-range-outline</v-icon>
        <span class="title-filter">TODAS AS DATAS DE INCLUSÃO</span>
        <v-icon right class="set-icon">mdi-chevron-down</v-icon>
      </v-list-item>
      <v-list-item class="border-grey">
        <v-icon>mdi-calendar-range-outline</v-icon>
        <span class="title-filter">TODAS AS DATAS DE ALTERAÇÃO</span>
        <v-icon right class="set-icon-2">mdi-chevron-down</v-icon>
      </v-list-item>
      <v-list-item class="border-grey">
        <v-icon>mdi-scatter-plot-outline</v-icon>
        <span class="title-filter">ATIVOS E INATIVOS</span>
        <v-icon right class="set-icon-3">mdi-chevron-down</v-icon>
      </v-list-item>
      <v-list-item>
        <v-btn class="bottom-aplicar" depressed>APLICAR</v-btn>
      </v-list-item>
    </v-navigation-drawer>
  </nav>
</template>
<style>
.title-icon {
  margin-top: -4px;
  margin-right: 10px;
}
.title {
  padding: 10px 0;
}
.title-btn {
  text-align: center;
  float: right;
  margin-right: 5px;
}

.v-application--is-ltr .v-btn__content .v-icon--right.btn-close {
  margin-left: -3px;
  margin-right: -4px;
}

.title-filter {
  color: #d81b60;
  font-weight: 900px;
  margin: 30px 15px;
}

.btn-icon {
  height: 45px;
  width: 54px;
}
.v-btn:not(.v-btn--round).v-size--default.bottom-aplicar {
  width: 100%;
  margin-top: 40px;
  height: 70px;
  border: 1px solid #d81b60;
  color: #d81b60;
  padding: 0 10px;
  min-width: 0;
}
.v-btn:not(.v-btn--round).v-size--default.btn-custom {
  height: 48px;
  width: 50px;
  min-width: 0;
}
.list-color {
  background-color: grey;
}
.text-content {
  font-size: 16px;
  margin-top: 20px;
  color: gray;
}
.v-icon--right.set-icon {
    margin-left: 130px;
}
.v-icon--right.set-icon-2 {
    margin-left: 120px;
}
.v-icon--right.set-icon-3 {
    margin-left: 220px;
}
.border-grey {
  border-bottom: 1.5px solid grey;
}
</style>
<script>
export default {
  data() {
    return {
      drawer: false
    };
  }
};
</script>
