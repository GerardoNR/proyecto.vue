<script>
export default {
    data() {
        return {
            numero1: 0,
            numero2: 0,
            resultado: 0
        }
    },
    methods: {
        sumar() {
            this.resultado = parseFloat(this.numero1) + parseFloat(this.numero2);
        },
        restar() {
            this.resultado = parseFloat(this.numero1) - parseFloat(this.numero2);
        },
        multiplicar() {
            this.resultado = parseFloat(this.numero1) * parseFloat(this.numero2);
        },
        dividir() {
            if (this.numero2 != 0) {
                this.resultado = parseFloat(this.numero1) / parseFloat(this.numero2);
            } else {
                this.resultado = "Error";
            }
        }
    }
}
</script>

<template>
    <div class="container mt-5">
        <div style="color:firebrick ;" class="card shadow-lg p-4 border-0 bg-secondary">
            <h4 class="text-center mt-4 text-dark">= 
                <span class="fw-bold text-dark">{{ resultado }}</span>
            </h4>
            <h3 class="text-center text-warning fw-bold">
                <i class="fas fa-calculator"></i> <i>CALCULADORA CASIO</i>
            </h3>
            <div class="mb-3">
                <label class="form-label fw-bold">Número 1:</label>
                <input type="number" class="form-control" v-model="numero1">
            </div>
            <div class="mb-3">
                <label class="form-label fw-bold">Número 2:</label>
                <input type="number" class="form-control" v-model="numero2">
            </div>

            <div class="d-flex justify-content-center gap-2 flex-wrap">
                <button @click="sumar" class="btn btn-info">
                    <i class="fas fa-plus"></i> +
                </button>
                <button @click="restar" class="btn btn-info">
                    <i class="fas fa-minus"></i> -
                </button>
                <button @click="multiplicar" class="btn btn-info">
                    <i class="fas fa-times"></i> *
                </button>
                <button @click="dividir" class="btn btn-info ">
                    <i class="fas fa-divide"></i> /
                </button>
           
            </div>

            
        </div>
    </div>
</template>

<style scoped>
.card {
    max-width: 400px;
    margin: auto;
    border-radius: 30px;
}
</style>