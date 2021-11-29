/*
  al click del genere, e dunque del value, scelto 
  il ciclo stamperà soltanto i dischi a cui corrisponde il genere/value inserito
  Fino ad adesso ogni volta che chiamo il mio array Albums inizialmente vuoto viene riempito da tutti gli elementi,ora il mio array dovrà essere filtrato in modo tale da non stampare "album in albums" perche cosi facendo sto stampando tutti gli album(tutti gli oggetti dell'array),ma dovrò stampare solamente quelli indicati dal genere/value
 */

<template>
  <select
    v-model="genere"
    @change="$emit('selectCategory', genere)"
  >
    <option value="Rock">Rock</option>
    <option value="Metal">Metal</option>
    <option value="Pop">Pop</option>
    <option value="Jazz">Jazz</option>
  </select>
</template>

<script>
export default {
  name: 'Select',
  data(){
    return {
      genere: ''
    };
  }
};
</script>

<style lang="scss">
@import '../assets/style/vars.scss';
  select{
    padding: 0 15px;
    border: 2px solid #1E2D3B;
    color: $primary-color;
    border-radius: 5px;
  }
</style>