<script setup>
import Formik from '../components/Formik.vue';
import Field from '../components/Field.vue';

function validate(values) {
  const errors = {};
         if (!values.email) {
           errors.email = 'Required';
         } else if (
           !/^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}$/i.test(values.email)
         ) {
           errors.email = 'Invalid email address';
         }
         return errors;
}
</script>

<template>
  <main>
    <Formik  
      v-bind:initial-values="{password: 'test', email: ''}" 
      v-bind:validate="validate"
      #default="{ isSubmitting, handleSubmit, values, errors }"
    >        
      <form @submit="handleSubmit">           
        <h1>Values</h1>           
        {{ JSON.stringify(values) }}
           <h1>Errors</h1>           
           {{ JSON.stringify(errors) }}
           <Field type="email" name="email" />           
           <!--<Field type="password" name="password" />          
           <Field as="TextArea" name="textearea" />    
           <Field as="Select" name="select1" />     -->
           <button type="submit" disabled={isSubmitting}>             
              Submit
           </button>        
      </form>
    </Formik>
          
  </main>
</template>
