<script>
export default{
    data() {
        return {
            display: '', 
            currentValue: 0,
            operator: null,
        }
    },
    methods: {
        agregarNumero(numero) {
            this.display += numero;
        },
        calcular() {
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
        limpiarUltimaEntrada() {
            this.display = this.display.slice(0, -1);
        },
        agregarOperador(operador) {
            if (this.display && !['+', '-', '*', '/'].includes(this.display[this.display.length - 1])) {
                this.display += operador;
            }
        },
        agregarPunto() {
            if (!this.display.includes('.')) {
                this.display += '.';
            }
        },
        igual() {
            this.calcular();
        }
    },
}
</script>

<template>
    <div class="container d-flex justify-content-center mt-4" style="height: 380px;">
        <div class="card p-3" style="width: 300px; background-color: blue;">
            <div class="card-body">
                <h3 class="text-center" style="color: white;">Calculadora V2</h3>
                <!-- Display de la calculadora -->
                <div class="mb-3">
                    <input type="text" class="form-control" v-model="display" disabled>
                </div>
                <!-- Botones de la calculadora -->
                <div class="d-flex flex-wrap justify-content-between">
                    <button class="btn btn-secondary w-25" @click="limpiarDisplay">C</button>
                    <button class="btn btn-secondary w-25" @click="limpiarUltimaEntrada">CE</button>
                    <button class="btn btn-secondary w-25" @click="agregarOperador('%')">%</button>
                    <button class="btn btn-danger w-25" @click="eliminarNumero">&#9003;</button>
                </div>
                <div class="d-flex flex-wrap justify-content-between mt-2">
                    <button class="btn btn-secondary w-25" @click="agregarNumero(7)">7</button>
                    <button class="btn btn-secondary w-25" @click="agregarNumero(8)">8</button>
                    <button class="btn btn-secondary w-25" @click="agregarNumero(9)">9</button>
                    <button class="btn btn-danger w-25" @click="agregarOperador('/')">/</button>
                </div>
                <div class="d-flex flex-wrap justify-content-between mt-2">
                    <button class="btn btn-secondary w-25" @click="agregarNumero(4)">4</button>
                    <button class="btn btn-secondary w-25" @click="agregarNumero(5)">5</button>
                    <button class="btn btn-secondary w-25" @click="agregarNumero(6)">6</button>
                    <button class="btn btn-danger w-25" @click="agregarOperador('*')">x</button>
                </div>
                <div class="d-flex flex-wrap justify-content-between mt-2">
                    <button class="btn btn-secondary w-25" @click="agregarNumero(1)">1</button>
                    <button class="btn btn-secondary w-25" @click="agregarNumero(2)">2</button>
                    <button class="btn btn-secondary w-25" @click="agregarNumero(3)">3</button>
                    <button class="btn btn-danger w-25" @click="agregarOperador('-')">-</button>
                </div>
                <div class="d-flex flex-wrap justify-content-between mt-2">
                    <button class="btn btn-secondary w-25" @click="agregarPunto">.</button>
                    <button class="btn btn-secondary w-25" @click="agregarNumero(0)">0</button>
                    <button class="btn btn-secondary w-25" @click="igual">=</button>
                    <button class="btn btn-danger w-25" @click="agregarOperador('+')">+</button>
                </div>
            </div>
        </div>
    </div>
</template>
