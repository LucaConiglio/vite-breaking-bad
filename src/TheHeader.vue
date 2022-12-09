<template>
  <section>
    <h2 class="pt-4 text-white text-center pb-4">My List</h2>
    <div class="row">
      <div class="col-8 m-auto">
      
        <form action="" class="mb-4" @submit.prevent="onSearchClick">
          <div class="row">
            <div class="col-sm-6">
              <div class="mb-3">
                <label class="text-white">Nome</label>
                <input type="text" class="form-control" name="name">
              </div>
            </div>
            <div class="col-sm-6">
              <div class="mb-3">
                <label class="text-white">Stato</label>
                <input type="text" class="form-control" name="status" >
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col-sm-4">
              <div class="mb-3">
                <label class="text-white">Specie</label>
                <input type="text" class="form-control" name="species" >
              </div>
            </div>
            <div class="col-sm-4">
              <div class="mb-3">
                <label class="text-white">Tipo</label>
                <input type="text" class="form-control" name="type" >
              </div>
            </div>
            <div class="col-sm-4">
              <div class="mb-3">
                <label class="text-white">Genere</label>
                <input type="text" class="form-control" name="gender">
              </div>
            </div>
            </div>
            <div class="d-flex gap-3 justify-content-center">
              <button class="btn btn-secondary" type="reset">Reset filtri</button>
              <button class="btn btn-info">Cerca</button>
            </div>
        </form>
      </div>
    </div>
    <div class="row">
      <div class="col-8 m-auto">
        <div class="alert alert-danger d-flex justify-content-around">
          <div>Trovati N.{{ store.infoList.count }} elementi.</div>
          <div>Stai visualizzando la pagina {{store.currentPage}} di {{ store.infoList.pages }}</div>
          <div>trovate specie {{speciesList}}</div>
        </div>
      </div>
    </div>
    
  </section>
</template>
<script>
import { store, fetchImage } from './store';
export default {
  data() {
    return {
      store

    }
  },
  computed : {
    speciesList () {
      const toReturn = [];

      this.store.characterList.forEach((character) => {

        if (!toReturn.includes(character.species)) {
          toReturn.push(character.species);
        }
      });

      return toReturn;
    }
  }
}
</script>
<style lang="scss">
  section{
    background-color: #2e3a46;
  }
</style>