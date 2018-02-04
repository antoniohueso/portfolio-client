<template>
  <div class="container">

    <div class="f-solicitud-width">

      <form>

        <fieldset>

          <legend>Solicitud de nuevo proyecto o evolutivo</legend>

          <!-- Mensage de error -->
          <div v-if="error" class="alert alert-info alert-dismissible fade show" role="alert">
            <button type="button" class="close" data-dismiss="alert" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
            <p>
              Los siguientes campos son obligatorios:
            </p>

            <p class="font-weight-bold">
              {{error}}
            </p>
          </div>

          <!-- Mensage de Ok -->
          <div v-if="okMessage" class="alert alert-success alert-dismissible fade show" role="alert">
            <button type="button" class="close" data-dismiss="alert" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>

            <p class="font-weight-bold">
              Su solicitud ha sido registrada (ID: <span>{{okMessage}}</span>)
            </p>
            <a href="/solicitudes">Ir al panel de solicitudes</a>
          </div>

          <!-- Campos del formulario -->
          <div class="form-group">
            <label>Nombre</label>
            <input v-model="solicitud.nombre" type="text" class="form-control" placeholder="Nombre del proyecto o evolutivo"
                   required>
          </div>

          <div class="form-group row">

            <div class="col-4">
              <label>Tipo</label>
              <select v-model="solicitud.tipo" class="form-control" required>
                <option value="0" selected>Evolutivo</option>
                <option value="1">Proyecto</option>
              </select>
            </div>

            <div class="col-4">
              <label>Importancia</label>
              <select v-model="solicitud.importancia" class="form-control" required>
                <option value="0">Baja</option>
                <option value="1" selected>Media</option>
                <option value="2">Alta</option>
                <option value="3">Urgente</option>
              </select>
            </div>

            <div class="col-4">
              <div class="form-group">
                <label>F. cambio normativo</label>
                <input v-model="solicitud.fechaCambioNormativo" type="date" class="form-control"
                       placeholder="Fecha de cambio normativo">
              </div>
            </div>

          </div>

          <div class="form-group">
            <label>Justificación de negocio</label>
            <textarea v-model="solicitud.justificacionNegocio" rows="10" class="form-control"
                      placeholder="Justificación de negocio" required></textarea>
          </div>

          <div class="form-group">
            <label>Áreas de desarrollo involucradas</label>
            <textarea v-model="solicitud.areasInvolucradas" class="form-control" placeholder="Áreas de desarrollo involucradas"
                      required></textarea>
          </div>

          <button v-on:click="onClick" class="btn btn-info">Enviar</button>

        </fieldset>

      </form>

    </div>

  </div>
</template>

<script>
  export default {
    name: "solicitud",
    data() {
      return {
        error: null,
        okMessage: null,
        solicitud: {
          nombre: null,
          tipo: 0,
          importancia: 1,
          fechaCambioNormativo: null,
          justificacionNegocio: null,
          areasInvolucradas: null
        }
      }
    },
    methods: {
      onClick(e) {
        e.preventDefault();
        console.log("Suuuuuu",this.solicitud);
      }
    }



  }
</script>

<style scoped>
  .f-solicitud-width {
    margin: auto;
    border: solid #f7f7f9;
    padding-top: 1rem;
    padding-right: 3rem;
    padding-left: 3rem;
    padding-bottom: 1rem;
  }
</style>
