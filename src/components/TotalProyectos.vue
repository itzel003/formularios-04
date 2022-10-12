<template>
    <hr>
    <div class="row my-3">
        <div class="col-6">
            <h3 class="text-center">Total de proyectos : {{numeroProyectos}}</h3>
        </div>  
        <div class="table-responsive">
            <table class="table table-dark">
                <thead>
                    <tr>
                        <th>#</th>
                        <th>Proyecto</th>
                        <th>Tipo</th>
                        <th>Urgente</th>
                        
                    </tr>
                </thead>
                <tbody v-for="(proyecto,index) in proyectos" :key="index">
                    <tr>
                        <td>{{index + 1}}</td>
                        <td>{{proyecto.proyecto}}</td>
                        <td>{{proyecto.tipo}}</td>
                        <td @click="cambiarEstado(proyecto,'urgente')"
                        class="font-weight-bold" 
                        :class="proyecto.urgente ? 'table-danger' : 'table-success'" role="alert">{{proyecto.urgente ? "Si" : "No"}}</td>
                       
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

    ],

}
</script>