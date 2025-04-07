<script>
export default {
    data() {
        return {
            display: '',
            currentValue: 0,
        };
    },
    methods: {
        agregarNumero(numero) {
            this.display += numero;
        },
        agregarOperacion(operador) {
            if (this.display !== '' && !isNaN(this.display.slice(-1))) {
                this.display += operador;
            }
        },
        calculo() {
            try {
                this.currentValue = eval(this.display);
                this.display = this.currentValue.toString();
            } catch (error) {
                this.display = 'Error';
            }
        },
        limpiarDisplay() {
            this.display = '';
        },
        eliminarNumero() {
            this.display = this.display.slice(0, -1);
        },
        porcentaje() {
            if (this.display !== '' && !isNaN(this.display)) {
                this.display = (parseFloat(this.display) / 100).toString();
            }
        }
    }
};
</script>

<template>
    <div class="container d-flex justify-content-center mt-4" style="height: 400px;">
        <div class="card p-3" style="width: 300px; background-color: #F3B2DB;">
            <div class="card-body">
                <h6 class="text-center">Calculadora V2</h6>
                <div class="mb-3">
                    <input type="text" class="form-control text-end" v-model="display" disabled>
                </div>
                <div class="d-grid gap-3">
                    <div class="d-flex gap-2">
                        <button class="btn btn-secondary flex-fill" @click="porcentaje">%</button>
                        <button class="btn btn-secondary flex-fill" @click="limpiarDisplay">CE</button>
                        <button class="btn btn-secondary flex-fill" @click="limpiarDisplay">C</button>
                        <button class="btn btn-info flex-fill" @click="eliminarNumero">B</button>
                    </div>
                    <div class="d-flex gap-2">
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero(9)">9</button>
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero(8)">8</button>
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero(7)">7</button>
                        <button class="btn btn-info flex-fill" @click="agregarOperacion('/')">/</button>
                    </div>
                    <div class="d-flex gap-2">
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero(4)">4</button>
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero(5)">5</button>
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero(6)">6</button>
                        <button class="btn btn-info flex-fill" @click="agregarOperacion('*')">X</button>
                    </div>
                    <div class="d-flex gap-2">
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero(1)">1</button>
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero(2)">2</button>
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero(3)">3</button>
                        <button class="btn btn-info flex-fill" @click="agregarOperacion('-')">-</button>
                    </div>
                    <div class="d-flex gap-2">
                        <button class="btn btn-secondary flex-fill" @click="calculo">=</button>
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero(0)">0</button>
                        <button class="btn btn-secondary flex-fill" @click="agregarNumero('.')">.</button>
                        <button class="btn btn-info flex-fill" @click="agregarOperacion('+')">+</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>