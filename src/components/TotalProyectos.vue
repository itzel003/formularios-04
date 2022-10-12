<template>
    <hr>
    <div class="row my-3">
        <div class="col-6">
            <h3 class="text-center">Total de proyectos : {{numeroProyectos}}</h3>
        </div>
        <div class="col-6 text-end">
            <button @click="limpiarData" class="btn btn-warning mb-3">Limpiar</button>
        </div>
        <div class="table-responsive">
            <table class="table table-light text-center">
                <thead>
                    <tr>
                        <th>#</th>
                        <th>Proyecto</th>
                        <th>Tipo</th>
                        <th>Urgente</th>
                        <th>Completado</th>
                    </tr>
                </thead>
                <tbody v-for="(proyecto,index) in proyectos" :key="index">
                    <tr>
                        <th>{{index + 1}}</th>
                        <td>{{proyecto.proyecto}}</td>
                        <td>{{proyecto.tipo}}</td>
                        <td @click="cambiarEstado(proyecto,'urgente')"
                        class="font-weight-bold" 
                        :class="proyecto.urgente ? 'table-danger text-danger' : 'table-success text-success'" role="alert">{{proyecto.urgente ? "Si" : "No"}}</td>
                        <td @click="cambiarEstado(proyecto,'completado')"
                        class="font-weight-bold" 
                        :class="proyecto.completado ? 'table-danger text-danger' : 'table-success text-success'" role="alert">{{proyecto.completado ? "Completado" : "Incompleto"}}</td>
                        
                    </tr>
                </tbody>
            </table>
          </div>
    </div>
    
</template>
<script>

export default{
    props:[
        'numeroProyectos',
        'proyectos',
        'cambiarEstado',
        'limpiarData'
    ],

}
</script>