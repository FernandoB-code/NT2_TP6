<template>

  <section class="src-components-usuarios">
    <div v-if="this.datosFormulario.length == 0" class="alert alert-danger">
      No hay usuarios para mostrar.
    </div>
    <div class="jumbotron">
      <table class="table table-dark table-striped table-hover">
        <thead>
          <tr>
            <th>Nombre</th>
            <th>Edad</th>
            <th>Email</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(usuario, index) in datosFormulario" :key="index">
            <td>{{ usuario.nombre }}</td>
            <td>{{ usuario.edad }}</td>
            <td>{{ usuario.email }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>

</template>

<script>

  export default  {
    name: 'src-components-usuarios',
    props: [],
    mounted () {
      this.getUsuarios()
    },
    data () {
      return {
        datosFormulario: [],
        url: 'https://61886832057b9b00177f9c5d.mockapi.io/FernandoBernasconi'
      }
    },
    methods: {
      async getUsuarios(){
        try {
          let respuesta = await this.axios.get(this.url )
          console.log('Datos recibidos', respuesta.data)
          this.datosFormulario = respuesta.data
        } catch (error) {
          console.error(error.message)
        }
      }
    },
    computed: {

    }
}


</script>

<style scoped lang="css">

</style>
