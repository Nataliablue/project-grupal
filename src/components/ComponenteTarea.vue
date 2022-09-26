<template lang="">
    <div>
    <div class="tareauno">
<h3>Nueva Tarea</h3>
<input type="text" class="nueva" v-model="tareaNueva"> <input type="button" v-on:click="btnAgregar" value="agregar">

    </div>
   
    <div class="tareados">
        <h3>Tarea Pendiente</h3>
<input type="text" id="tareaP" class="cajaTareaPendiente" :value="tareaPendiente"> <input type="button" v-on:click="btnListo" class="btnListo" value="listo"> <input type="button" class="btnEliminar" v-on:click="btnEliminar" value="Eliminar">

    </div>
    <div class="tareatres">
        <h3>Tarea Finalizada</h3>
<!--<input type="text" class="cajaTareaFinalizada" :value="tareaFinalizada"> -->
        <select name="seleccionar" id="slcTareaFinalizada" :value="tareaFinalizada">
            <option :value="null" disabled>Tareas Finalizadas</option>
        </select>
    </div>
    </div>
</template>
<script>
export default {
  // props: ['llamar'],
    data() {
        return {
            tareaNueva: "",
            tareaPendiente:"",
            tareaFinalizada:""
        }
    },
    methods: {
        btnAgregar(){
        const dateobj = new Date()
            let fecha = dateobj.toUTCString()
            this.tareaPendiente=(this.tareaNueva +"fecha["+ fecha +"]-")
            this.tareaNueva = ""
        },
        btnListo(){
            const $sele = document.getElementById('slcTareaFinalizada')
            const option = document.createElement('option');
            let tareaFinalizada=(this.tareaPendiente)
            option.value=tareaFinalizada;
            option.text=tareaFinalizada;
            $sele.appendChild(option);
            const opcionCambiar=()=>{
                console.log("Cambio");
            }
            $sele.addEventListener("change",opcionCambiar);
            this.tareaPendiente= ""
        },
        btnEliminar(){
            document.getElementById("tareaP").value=""
        },
    },
}
</script>
<style>
.tareados,
.tareatres,
.tareauno {
    margin-top: 20px;
    margin-bottom: 10px;
    width: 690px;

}

.nueva,
.cajaTareaPendiente,
.cajaTareaFinalizada {
    width: 80%;
}

#slcTareaFinalizada{
    width: 555px;
}
</style>