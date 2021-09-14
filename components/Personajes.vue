<template>
  <div>
      <b-overlay :show="show" no-wrap>
      </b-overlay>
    <div class="d-flex flex-wrap container">
      <b-col sm="12" md="4" lg="4" v-for="(personaje,index) in listado" :key="index">
        <div class="card mt-4">
          <img class="card-img-top img" :src="personaje.image" width="100%" />
          <div class="card-body">
            <h4 class="card-title text-capitalize"> {{ personaje.name }}</h4>
          </div>
        </div>
      </b-col>
      

    </div>

    <div class="container">
      <div class="d-flex justify-center">
        <b-button @click="changePageDow(page)">Anterior</b-button>
        <b-list-group-item variant="primary">{{ this.page }}</b-list-group-item>
        <b-button @click="changePageUp(page)">Siguiente</b-button>

      </div>
    </div>

  </div>
</template>

<script>
export default {
  data(){
    return {
      listado:[],
      page:1,
      pages:1,
      show:true
    }
  },
  mounted(){
    this.cargaPersonajes();
  },
  methods:{
    async cargaPersonajes(){
      this.show=true;
      const params = { page: this.page };
      const personajes = await this.$axios.get("https://rickandmortyapi.com/api/character", { params });
      this.listado= personajes.data.results;
      this.pages= personajes.data.info.pages;
      this.show=false;
    },
    changePageDow(page){
      page=this.page-1;
      this.page = (page <=0 || page > this.pages) ? this.page: page;
      this.cargaPersonajes();
    },
    changePageUp(page){
      page=this.page+1;
      this.page = (page <=0 || page > this.pages) ? this.page: page;
      this.cargaPersonajes();
    }
  }
}
</script>
