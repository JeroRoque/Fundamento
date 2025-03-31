<template>
    <div class="container">
        <div class="row mt-4">
            <div>
                <h4>Evento Click</h4>
                <button @click="clic" class="btn btn-danger" type="button">Dale clic</button>
                <button @click="soyButon" class="btn btn-warning mx-2" type="button">Dale clic 2</button>
            </div>
            <div>
                <h4>Evento Change</h4>
                <label class="input-group-text" for="nombre">Ingresa tu nombre</label>
                <input class="form-control mt-2" type="text" id="nombre" @change="nombreE">
                <p><strong>El nombre ingresado es: {{ nombre }}</strong></p>
            </div>
            <div>
                <h4>Evento Contador</h4>
                <label class="input-group-text" for="mensaje">Escribe un mensaje</label>
                <input class="form-control mt-2" type="text" id="mensaje" @input="contarCaracteres">
                <p><strong>Caracteres ingresados: {{ contador }}</strong></p>
            </div>
            
            <div>
                <h3>Evento de mouseenter y mouseleave </h3>
            <div class="text-center" 
                style="color: #ffff; width: 300px; height: 200px; background-color: black; text-align: center; padding: 15px; border-radius: 14px;"
                @mouseenter="mostrarMensaje" @mouseleave="ocultarMensaje">
                <p>pase el mouse</p>
                <p>{{ mensaje }}</p>
            </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            nombre: '',
            contador: 0,
            mensaje: '',
        };
    },
    methods: {
        clic() {
            alert("Gracias por darle clic");
        },
        soyButon() {
            alert("Soy un botón");
        },
        nombreE(event) {
            this.nombre = event.target.value;
        },
        contarCaracteres(event) {
            this.contador = event.target.value.length;
        },
        mostrarMensaje() {
            this.mensaje = "El mouse está dentro del rectángulo";
        },
        ocultarMensaje() {
            this.mensaje = "El mouse está fuera del rectángulo";
        }
    }
};
</script>

<style>

</style>
