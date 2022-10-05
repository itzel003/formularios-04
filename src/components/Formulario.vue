<template>
<!-- bootstrap form -->
<form @submit.prevent="registrarproyecto">
    <div class="mb-3">
      <label for="" class="form-label">Proyecto</label>
      <input type="text" class="form-control" required>
    </div>
    <div class="mb-3">
        <label for="" class="form-label">Actividad</label>
        <select class="form-select" required>
            <option disabled selected value="">Seleccione tipo de actividad</option>
            <option value="1">Aplicaciones Web con Vue.JS</option>
            <option value="2">Backend Service con Node.js</option>
            <option value="3">App Movil con React Native</option>
        </select>
    </div>
    <div class="mb-3">
        <label class="form-check-label m-1">Urgente</label>
        <input type="checkbox" class="form-check-input m-2">
    </div>
    <button type="submit" class="btn btn-primary">Guardar</button>
  </form>
</template>

<script>
    export default{
      data:()=>({
        
      }),
      methods:{
        registrarproyecto(){
          console.log("Proyecto registrado ...")
        }
      },
    };
  
  </script>