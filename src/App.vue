<script setup>
  import { ref } from 'vue'
  import Presupuesto from './components/Presupuesto.vue';
  import ControlPresupuesto from './components/ControlPresupuesto.vue';

  const presupuesto = ref(0)

  const definirPresupuesto = (cantidad) => {
    presupuesto.value = cantidad
  }
</script>

<template>
  
  <div>
    <header>
      <h1>Planificador de Gastos</h1>
   

      <div class="contenedor-header contenedor sombra">
        <Presupuesto
        v-if="presupuesto === 0"
        @definir-presupuesto = "definirPresupuesto"
      />
       <ControlPresupuesto
        v-else
       />
       
      </div>
  </header>
  
</div>
</template>

<style>
   :root {
    --azul: #3b82f6;
    --blanco: #ffffff;
    --gris-claro: #F5F5F5;
    --gris-oscuro: #64748b;
    --negro: #000000;
   }

   html {
    font-size: 62.5%;
    box-sizing: border-box;
   }

   *,
   *::before,
   *::after {
    box-sizing: inherit;
   }

   body {
    font-size: 1.6rem;
    font-family: "Lato", sans-serif;
    background-color: var(--gris-claro);
   }
   h1{
    font-size: 4rem;
   }
   h2{
    font-size: 3rem;
   }
   header {
    background-color: var(--azul);
   }
   header h1{
    padding: 3rem 0;
    margin: 0;    
    color:var(--blanco);
    text-align: center;
   }
   .contenedor{
    width: 90%;
    max-width: 80rem;
    margin: 0 auto;
   }
   .contenedor-header{
    margin-top: -5rem;
    transform: translateY(5rem);
    padding: 5rem;
   }
   .sombra{
    box-shadow: 0px 10px 15px -3px rgba(0, 0, 0, 0.1);
    background-color: var(--blanco);
    border-radius: 1.2rem;
    padding: 5rem;
   }
</style>
