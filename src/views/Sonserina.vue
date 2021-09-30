<template>
  <v-container>
    <h2 class="text-a5 text-center mb-3 mt-1">Sonserina</h2>
    <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th colspan="2" class="text-left">
            clube
          </th>
          <th class="text-right">
            Pontos
          </th>
        </tr>
      </thead>
      <tbody>
          <tr v-for="(clube, Index) of Sonserina" :key="clube.id">
             <td>{{Index}}</td>
              <v-avatar size="24">
                <img
                  src="clube.escudo"
                  alt="clube.nome"
                >
              </v-avatar>
            <span class="pl-2"><td>{{clube.nome}}</td></span>
            <td>{{clube.pontos}}</td>
          </tr>
      </tbody>
    </template>
  </v-simple-table>
  </v-container>
</template>

<script>
export default {
  name: 'Sonserina',
  data(){
    return{
      Sonserina:[]
    }
  },

  computed: {
    listaOrdenada(){
      const listaOrdenada = this.listaOrdenada.slice(0)(
      (a, b) => a.pontos > b.pontos ? -1 : 1 );

      return listaOrdenada;

    }
  },

    created(){
      fetch('https://hackthon-decola.firebaseio.com/clubes-lista.json')
      .then(resposta => resposta.json())
      .then(json => {
        this.Sonserina = json;

        console.log(this.Sonserina)

      });
    }

}
</script>

<style scoped>

</style>