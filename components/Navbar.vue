<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-brand href="#" to="/">Desafío</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-navbar-brand href="#" to="/">Personajes</b-navbar-brand>
          <b-navbar-brand href="#" to="/acerca">Acerca</b-navbar-brand>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>

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
  </div>
</template>