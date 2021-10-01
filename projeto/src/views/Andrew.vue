<template>
  <div>
      <h1>Vendas</h1>
      <v-simple-table
    fixed-header
    height="300px"
  >
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">
            Comprador
          </th>
          <th class="text-left">
            Produto
          </th>
          <th class="text-left">
            Data
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in lista"
          :key="item.id"
        >
          <td>{{ item.Nome_Cliente }}</td>
          <td>{{ item.Nome_Produto }}</td>
          <td>{{ item.Data }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
  </div>
</template>

<script>
export default {
    name: 'Andrew',
    data (){
        return{
            lista: []
        }
    },
    created(){
        fetch('https://jordanelizeu.github.io/Data/vendas.json')
        .then(resultado => resultado.json())
        .then(json => {
            this.lista = json
            console.log(this.lista)
        })
    }
}
</script>

<style>

</style>