<template>
  <div class="mt-7 mx-9 font-size">
    <v-data-table
      :headers="headers"
      :items="users"
      :page.sync="page"
      :items-per-page="itemsPerPage"
      hide-default-footer
      @page-count="pageCount = $event"
      show-select
      singleSelect
      disable-sort
      class="table-round-corner"
    >
      <template v-slot:item="{ item }">
        <tr
          @mouseover="hoverOver(item)"
          @mouseout="hoverOut(item)"
          style="position: relative;"
        >
          <td><v-checkbox></v-checkbox></td>
          <td>{{ item.user }}</td>
          <td>{{ item.email }}</td>
          <td class="text-center">{{ item.incluseDate }}</td>
          <td class="text-center">{{ item.alterDate }}</td>
          <td class="text-center">{{ item.rules }}</td>
          <td class="text-center">
            <span v-if="item.status"
              ><span class="green--text status">ATIVO</span></span
            >
            <span v-else><span class="red--text status">DESATIVADO</span></span>
          </td>
          <td width="130" class="text-right">
            <span v-show="item.hover" style="position: relative; z-index: 2;"
              ><v-icon>mdi-delete</v-icon>
              <v-icon>mdi-archive</v-icon>
              <v-icon>mdi-security</v-icon>
              <v-icon>mdi-pencil</v-icon></span
            >
          </td>
          <td width="120" class="text-center">
            <v-icon>mdi-dots-horizontal</v-icon>
          </td>
          <div v-show="item.hover" class="table-item-overlay"></div>
        </tr>
      </template>
    </v-data-table>
    <div class="text-center pt-2 mt-5 mb-10">
      <v-btn class="pagination-custom-btn" v-on:click="page = 1"
        >Primeiro</v-btn
      >
      <v-pagination
        class="custom-datatable-pagination"
        v-model="page"
        color="pink"
        :length="pageCount"
        prev-icon="Anterior"
        next-icon="Próximo"
      ></v-pagination>
      <v-btn
        class="pagination-custom-btn btn-color"
        v-on:click="page = pageCount"
        >Último</v-btn
      >
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      page: 1,
      pageCount: 0,
      itemsPerPage: 6,
      singleSelect: true,
      active: false,
      search: "",
      headers: [
        { text: "USUÁRIO", value: "user", align: "start" },
        { text: "EMAIL", value: "email", align: "start" },
        { text: "DATA DE INCLUSÃO", value: "incluseDate", align: "center" },
        { text: "DATA DE ALTERAÇÃO", value: "alterDate", align: "center" },
        { text: "REGRAS", value: "rules", align: "center" },
        { text: "STATUS", value: "status", align: "center" },
        { text: "", value: "", align: "center" },
        { text: "AÇÕES", value: "actions", align: "center" }
      ],
      users: [
            {"id": 1, "user": "ANPINA", "email": "antonio.pina@tvglobo.com.br", "incluseDate": "28/05/2019", "alterDate": "30/05/2019", "rules": 1, "status": true, "hover": false},
            {"id": 2, "user": "CCHANG", "email": "ciro.chang@tvglobo.com.br", "incluseDate": "28/05/2019", "alterDate": "30/05/2019", "rules": 1, "status": true, "hover": false},
            {"id": 3, "user": "TMARCAL", "email": "thiago.marcal@tvglobo.com.br", "incluseDate": "28/05/2019", "alterDate": "30/05/2019", "rules": 1, "status": false, "hover": false},
            {"id": 4, "user": "ECGIANN", "email": "ecgiannotto@tvglobo.com.br", "incluseDate": "28/05/2019", "alterDate": "30/05/2019", "rules": 1, "status": true, "hover": false},
            {"id": 5, "user": "YFERNAND", "email": "yuri.vasquez@tvglobo.com.br", "incluseDate": "28/05/2019", "alterDate": "30/05/2019", "rules": 2, "status": false, "hover": false},
            {"id": 6, "user": "PLACERDA", "email": "pedro.soares.larceda@tvglobo.com.br", "incluseDate": "28/05/2019", "alterDate": "30/05/2019", "rules": 2, "status": true, "hover": false},
            {"id": 7, "user": "JOGATINA", "email": "joao.agular@tvglobo.com.br", "incluseDate": "28/05/2019", "alterDate": "30/05/2019", "rules": 2, "status": true, "hover": false},
            {"id": 8, "user": "SARADA", "email": "sara.silva@tvglobo.com.br", "incluseDate": "28/05/2019", "alterDate": "30/05/2019", "rules": 1, "status": true, "hover": false},
            {"id": 9, "user": "FAMAOL", "email": "fabio.oliveira@tvglobo.com.br", "incluseDate": "28/05/2019", "alterDate": "30/05/2019", "rules": 1, "status": true, "hover": false}
        ]
    };
  },
  methods: {
    hoverOver(index) {
      index.hover = true;
    },
    hoverOut(index) {
      index.hover = false;
    }
  }
};
</script>
<style scoped>
/deep/ .v-pagination__navigation {
  width: 70px;
  padding: 5px 10px;
  font-size: 10px;
  padding: 9px 12px;
  height: 50px;
  font-family: "Roboto", sans-serif;
}
/deep/ .v-pagination__navigation i {
  font-size: 10px;
}

/deep/ .v-input--selection-controls__input {
  height: 0 !important;
}
/deep/ .theme--light.v-pagination .v-pagination__item {
  background: #e91e63;
  color: rgba(247, 241, 241, 0.87);
  min-width: 34px;
  padding: 0 5px;
  width: 40px;
  height: 40px;
  margin: 0 3px;
}

/deep/ .v-pagination__navigation {
  width: 70px;
  padding: 5px 10px;
  font-size: 10px;
  padding: 9px 12px;
  height: 40px;
  font-family: "Roboto", sans-serif;
  margin: 0 1px;
}
/deep/ .theme--light.v-pagination .v-pagination__navigation {
  background: #ececec;
}

/deep/ .v-btn:not(.v-btn--round).v-size--default {
  height: 40px;
}
</style>
<style lang="scss" scoped>
.table-item-overlay {
  position: absolute;
  inset: 0px;
  background: rgb(255, 255, 255);
  color: #333;
  opacity: 0.9;
  border-bottom: solid 2px red;
}
.custom-datatable-pagination button {
  width: auto;
  padding: 5px;
}
.custom-datatable-pagination button i {
  font-size: 15px;
}
.v-pagination {
  width: auto;
}
.pagination-custom-btn {
  flex: 0 0 auto;
  align-content: center;
  align-items: center;
  width: 70px;
  font-size: 10px;
  padding: 9px 12px;
  height: 40px;
  margin: 0 4px;
  color: gray;
}
tr:nth-child(odd) {
  background: #eae8e8;
}
tr:nth-child(even) {
  background: #e0dede;
}
.status {
  font-weight: 500;
}
.border {
  border-radius: 1px solid;
}
.table-round-corner {
  // border-collapse:separate;
  border: 1px solid #ccc;
  -webkit-border-radius: 5px;
  -moz-border-radius: 5px;
  border-radius: 5px;
}
.font-size {
  font-size: 13px;
}

.theme--light.v-pagination.btn .v-pagination__item {
  width: 50px;
  height: 50px;
}
</style>
