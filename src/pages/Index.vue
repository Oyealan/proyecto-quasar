<template>
<q-page padding>
  <h4>Formulario</h4>



  <q-form 
  class="row q-col-gutter-md"
  @submit.prevent="procesarFormulario">

    <div class="col-12 col-sm-3"> 
      <q-input 
      filled
       outlined
       label="Usuario"
       v-model="Usuario"
       :rules="[ val => val && val.length > 0 || 'Introduzca un Usuario']"
      />


    </div>
    <div class="col-12 col-sm-3"> 
      <q-input 
      
      filled
       outlined
       label="Contraseña"
       v-model="Contraseña"
       :rules="[ val => val && val.length > 0 || 'Mayuscula, minuscula numero, caracterer especial $%']"
       
      />
      
    </div>

    <div class="col-12">
      <q-btn 
         label="Entrar"
         color="secondary"
         type="Entrar"
          />
    </div>
</q-form>

<h4>Datos de pago</h4>

 <q-form class="row q-col-gutter-md">
  <div class="col-12 col-sm-3">

    <q-input
    filled
    outlined
    label="Nombre del Titular"
    v-model="Nombre"
    hint="Titular"
    />
   </div>

   <div class="col-12 col-sm-3">

    
      <q-input
        filled
        v-model="Numero"
       
        mask="#### - #### - #### - ####"
        fill-mask="#"
        unmasked-value
        hint="Numero de Tarjeta"
      />
  </div>

  <div class="q-gutter-md">
  <q-input 
  filled
  outlined
  v-model="Fecha"
  label="Fecha"
  mask="##/##"
  fill-mask
  hint="ExpIracion"
  
  
  />
    
</div>



<div class="q-gutter-md">
  <q-input 
  filled
  outlined
  v-model="ccv"
  label="CCV"
  mask="###"
  fill-mask
  hint="CCV"
  
  
  />
</div>

<div class="col-12">
  <q-btn 
  label="Entrar"
  color="secondary"
  type="text"
  />
</div>
</q-form>
</q-page>

</template>

<script>
import {ref} from 'vue'
export default {
  setup() {
    const Usuario = ref(null)
    const Contraseña = ref(null)
    const Nombre = ref(null)
    const Numero = ref(null)
    const Fecha = ref(null)
    const ccv = ref(null)
    const click = ref(false)
    
    const procesarDatos = () => {
      console.log('Ingresaste Datos')
    }
    const procesarFormulario = () => {
       console.log('Ingresaste al formulario')
       
    }

    return {
      Usuario,
      Contraseña,
      procesarFormulario,
      Nombre, 
      Numero,
      Fecha,
      ccv,
      procesarDatos,
      click
    }
    
  },
}
</script>
