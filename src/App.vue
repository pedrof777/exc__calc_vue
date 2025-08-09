<script setup>
import { reactive } from 'vue';
import Header from './components/Header.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
    numberOne: '',
    numberTwo: '',
    operacoes: 'soma',
    resultado: null
});

function getNumero(e,campo){
    estado[campo] = e.target.value;
    resultadoOperacoes()
}

function switchOperacoe(e){
    estado.operacoes = e.target.value;
    resultadoOperacoes();
}

function resultadoOperacoes(){
    const n1 = parseFloat(estado.numberOne);
    const n2 = parseFloat(estado.numberTwo);

    if(estado.operacoes === 'soma'){
        estado.resultado = n1 + n2;
    }else if(estado.operacoes === 'sub'){
        estado.resultado = n1 - n2;
    }else if(estado.operacoes === 'mult'){
        estado.resultado = n1 * n2;
    }else if(estado.operacoes === 'div'){
        estado.resultado = n1 / n2;
    }
    
}
</script>

<template>
    <div class="container text-center">
        <Header/>
        <div class="row">
            <Formulario
            :function-get-num-a="evento => getNumero(evento, 'numberOne')" 
            :function-get-num-b="evento => getNumero(evento, 'numberTwo')"
            :switch="evento => switchOperacoe(evento)"
            />
            <Resultado :resultado="estado.resultado"/>
        </div>
    </div>

</template>

<style scoped></style>
