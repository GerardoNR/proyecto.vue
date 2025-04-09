<template>
    <div class="container text-center">
        <div class="row mt-4">
            <div>
                <h4><i>Evento Click</i></h4>
                <button @click="clic" class="btn btn-success" type="button" style="width: 150px; height: 50px;">
                     Dale clic</button>
                <button @click="soyboton" class="btn btn-danger mx-4" type="button" style="width: 150px; height: 50px;">
                     Dale clic 2</button>
            </div>
        <div>
        <h4><i>Evento change</i></h4>
        <label class="input-group-text" for="" style=" padding: 5px; width: 300px; margin: auto;" >Ingresa tu nombre:</label> 
        <input class="form-control mt-3" type="text" id="nombre" @change="nombreE" style=" width:300px; height:30px; margin:auto;">
        <p class="mt-2">El nombre ingresado es:<strong>{{ nombre }}</strong> </p>
        </div>
<div>
    <h3><i>Evento de mouseenter y mouseleave</i></h3>
    <div class="text-center"
    style="color:white; width: 400px; height: 150px; background-color: blue ;
    text-align:center; padding:15px; border:18px; border-radius:20px; margin: auto;" 
    @mouseenter="mostrarMensaje" @mouseleave="ocultarMensaje">
  <p>Pase el mouse</p>
  <p>{{ mensaje }}</p>
        </div>
    </div>
</div>
</div>
</template>
<script>
export default {
    data (){
        return {
            nombre: '',
            mensaje: ''
        }
    },
    methods: {
        clic (){
            alert("gracias por darle clic")
        },
        soyboton(){
            alert("soy un boton")
        },
        nombreE (event){
            this.nombre= event.target.value
        },
        mostrarMensaje(){
            this.mensaje="El mouse esta dentro del rectangulo"
        },
        ocultarMensaje(){
            this.mensaje="El mouse esta fuera del rectangulo"
        }
    }
}
</script>
<style></style>