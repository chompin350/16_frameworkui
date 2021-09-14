<template>
  <div>
    <Navbar />
    <b-jumbotron
      header="Desafío - Desarrollo en frameworks de Vue"
      lead="Sobre nuxt"
    >
      <p>Se utilizo bootstrap-vue</p>
    </b-jumbotron>
    <div class="container">
      <b-card bg-variant="dark" text-variant="white" title="Sitio Oficial">
        <b-card-text>
          Pagina de Sitio Rick and Morty.
        </b-card-text>
        <b-button href="https://rickandmortyapi.com/" target="_black" variant="primary">Ver</b-button>
      </b-card>

      <b-card bg-variant="dark" text-variant="white" title="Documentacion Oficial" class="my-4">
        <b-card-text>
          Documentacion :
        </b-card-text>
        <b-button href="https://rickandmortyapi.com/documentation" target="_black" variant="primary">Ver</b-button>
      </b-card>

    </div>
  </div>
</template>