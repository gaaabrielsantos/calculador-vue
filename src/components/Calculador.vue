<script>
export default {
    data() {
        return {
            numero1: 0,
            numero2: 0,
            operacao: "+"
        };
    },
    computed: {
        resultado() {
        const num1 = parseFloat(this.numero1);
        const num2 = parseFloat(this.numero2);

            if (isNaN(num1) || isNaN(num2)) {
                return "Inválido";
            }
            
            switch (this.operacao) {
                case "+":
                return num1 + num2;
                case "-":
                return num1 - num2;
                case "*":
                return num1 * num2;
                case "/":
                return num2 !== 0 ? num1 / num2 : "Infinito";
                default:
                return "Inválido";
            }
        }
    }
};
</script>

<template>
    <div class="container mt-5">
        <h1 class="mb-4">Calculadora Aritmética</h1>

        <div class="row">
        <div class="col-md-3">
            <input v-model="numero1" type="number" class="form-control" placeholder="Número 1">
        </div>
        <div class="col-md-3">
            <select v-model="operacao" class="form-control">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
            </select>
        </div>
        <div class="col-md-3">
            <input v-model="numero2" type="number" class="form-control" placeholder="Número 2">
        </div>
        </div>

        <div class="row mt-5">
        <div class="col">
            <h2>Resultado: {{ resultado }}</h2>
        </div>
        </div>
        </div>
</template>